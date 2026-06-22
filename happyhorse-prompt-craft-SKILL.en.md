---
name: happyhorse-prompt-craft
description: Prompt authoring & optimization guide for HappyHorse 1.0/1.1 R2V/I2V/T2V. Distilled from 100+ A/B tests across 47+ scenarios. Use when writing, tuning, or diagnosing HappyHorse video-generation prompts, or comparing 1.0 vs 1.1 behaviour.
version: 1.0.0
---

# HappyHorse Prompt Craft

🌐 **Language:** English · [🇨🇳 中文](happyhorse-prompt-craft-SKILL.md)

A hands-on guide to writing and optimising R2V / I2V / T2V prompts for both HappyHorse 1.0 and 1.1.

- Authoring handbook (CN): https://alidocs.dingtalk.com/i/nodes/R1zknDm0WR6XzZ4Lt0GdojnzWBQEx5rG?utm_scene=team_space
- Try the models: https://bailian.console.aliyun.com/cn-beijing?tab=demohouse&source_channel=hhpromptrepo#/experience/t2v

> **Verbatim prompts:** every Chinese prompt block below is preserved exactly as it is sent to the model — these are tested artefacts, not source text to re-translate. Surrounding prose is in English; the prompts themselves stay in their original language.

---

## Module 1: The R2V four-block structure

R2V prompts follow a strict four-block layout (extensible to five):

```
① [Image N] declaration & character mapping
② Style / mood + character cards
③ Storyboard / performance body (timecoded or loose narrative)
④ Global constraint FOOTER (text suppression + consistency + lip-sync)
```

### Declaration rules

- The first line MUST declare what each reference image is for, e.g. `[Image 1]为书房场景参考，[Image 2]为男人参考，[Image 3]为女人参考。`
- `[Image 1]` **must have a space** — hard requirement. `[Image1]` without the space breaks API parsing.
- R2V accepts 1–9 reference images, addressed by `[Image 1]`…`[Image 9]`.
- Recommended convention for multi-character scenes: `[Image 1]` = scene, `[Image 2]` = character A, `[Image 3]` = character B.

### Style / mood block

One sentence immediately after the declaration, covering visual style + light direction + colour grading + texture quality.

```
写实古装情感短剧，宋代夜晚书房。电影级浅景深，低饱和宋代美学，微胶片颗粒，真实皮肤纹理。
```

### Character cards

One line per character, format: `[Image N]role: silhouette + costume + emotional state`.

```
[Image 2]男人：宋代文官，深色圆领袍，束发，神色疲惫克制。
[Image 3]女人：宋代已婚女子，浅色褙子，发髻简洁，气质冷静压着情绪。
```

### Global constraint FOOTER

Lives at the very end. Three classes of constraints:

```
人物口型与台词自然同步，每句台词必须完整念出不省略。
严格保持[Image 2]男人和[Image 3]女人面容服饰一致。
画面严禁出现任何字幕、简体字、印刷体、现代字符、印章、logo、水印。
```

---

## Module 2: I2V minimalism

The first frame already carries the visual information. An I2V prompt must NOT repeat what is already visible.

### Core principles

- **30–60 characters** is the sweet spot (complex martial-arts sequences may reach 720 characters as an exception).
- Focus on three things: **action + camera + audio**.
- Do NOT describe appearance / clothing / background — the first frame already has them.
- Optional trailing audio description.

### Template

```
[action description, 2–3 concrete verbs] + [camera instruction] + [SFX / ambient]
```

### Example

```
女子缓缓转头望向窗外，发丝被微风轻拂。固定机位中近景。环境音：窗外蝉鸣、微风声。
```

---

## Module 3: Timecodes vs. loose narrative

**Key finding: 1.1 executes timecodes and quantitative directives too literally — performance and emotional scenes often feel less natural than 1.0.**

### When to use timecodes (1.1's strength)

- Spatial constraints (character positions, prop placements).
- Multi-shot orchestration (8-cell storyboards generated in order).
- Narrative with explicit action-switch beats.
- Precise rhythm control for brand spots.

```
[00:00-00:04] [中景] 女人走向书案，目光落在文书上。
[00:04-00:08] [近景] 男人抬头，手中毛笔停住。
[00:08-00:12] [双人中景] 两人对视，烛光摇曳。
```

### When to drop timecodes (performance / emotion)

- Micro-expression shifts (restrained, tearful, hesitant).
- Long pauses / choked-up speech rhythms.
- Monologue / dialogue that needs to feel "natural".

**Loosened writing**: delete all `[00:00-00:03]` timecodes and second-level constraints ("pause two seconds" / "half-second between each character"), replacing them with natural-order emotional-intent descriptions:

```
❌ [00:05-00:13] 先吐出"我"字，停顿足足两秒...每个字之间留出半秒以上停顿
✅ 她极轻极慢地开口说出这句话，每个字都带着克制的气声和哽咽，像从胸腔里压出来
```

### Decision matrix

| Scene type | 1.1 recommendation | 1.0 recommendation |
|------------|---------------------|---------------------|
| Spatial / prop consistency | Timecode + coordinate constraint | Same |
| Multi-shot storyboard | Timecode + cell numbering | Same |
| Single-character emotional micro-acting | **Loose narrative** | Loose narrative |
| Multi-character dialogue (heavy lines) | Timecode segments (≤ 2 lines per segment) | Same |
| High-density action stream | No timecodes, continuous narration | Same |

---

## Module 4: Dialogue & speech triggers

### Format options

| Format | Best for | Example |
|--------|----------|---------|
| `[role/tone/"line"]` tag style | Inside timecoded shots | `[女人/低声/克制/"你写了一夜。"]` |
| `「line」` embedded in narration | Loosened performance segments | `她开口：「我……终究是错付了。」` |
| `"says: xxx"` | Simple triggers | `男人低声说："走吧。"` |

### Key rules

1. **Match the language to the culture**: Japanese-school scenes use Japanese 「」, Korean webtoons use Korean, Chinese period drama uses Chinese.
2. **Line-duration math**: 4 chars/sec × 1.2 emotion multiplier. Example: 17 chars ≈ 5.1s, so the time window must be at least 5s.
3. **Dialogue density per time window ≤ 2 lines** — highest lip-sync hit rate.
4. **Silence placeholders**: for line-free segments use `[role/沉默/emotion/无台词]` to stop the model from improvising filler.
5. **1.1 has higher dialogue-execution rates than 1.0**, but over-quantifying pause rhythms makes delivery mechanical.

### Loose-mode dialogue writing

No tags — fold dialogue into performance narration:

```
她极轻极慢地开口说出这句话，每个字都带着克制的气声和哽咽，像从胸腔里压出来：「我……终究是错付了。」说话时眼眶逐渐泛起水光。
```

---

## Module 5: Camera movement

Camera movement must live in its **own paragraph**, never folded into performance description (to avoid cross-interference).

### Three modes

**Fixed camera**:
```
单一连续镜头，无剪切，无镜头移动。近景构图（胸像以上）。
```

**Slow dolly-in** (for emotional climax focus):
```
【镜头运动】镜头从胸像中近景开始，全程极其缓慢、平稳、匀速地向前推进（dolly in），最终落在女子面部脸庞特写（眼眶、泪痕、抿唇全部清晰可见）。推进速度极慢，不晃动不变焦不切镜，整体推近幅度大约 1.3 倍。
```

**Camera combo** (commercial / narrative):
```
Cell 1: Medium shot push in, girl on wooden porch discovers a glass wind chime.
Cell 5: Low angle track, kitten plays gently with the paper strip.
Cell 8: Extreme wide slow pull out, golden sunset fills the sky.
```

### Constraint keywords

- Always say **what NOT to do**: no shake, no zoom, no cut.
- Specify push-in ratio (1.3× / 1.5×).
- For fixed cameras, the rest of the prompt MUST contain zero push-in implications.

---

## Module 6: Rendered text control

**Problem**: 1.1 is extremely faithful to reference images and will render any storyboard annotations / cell numbers from the reference into the output video.

### Three layers of defence (weakest → strongest)

**Layer 1: inside the storyboard description**
```
文书上有宋代竖排行书背景质感（柔焦虚化、不可辨读）
```

**Layer 2: local constraint at the segment tail**
```
所有纸面文字必须是宋代竖排毛笔行书风格的模糊背景质感，浅景深柔焦处理，不出现可清晰辨读的整段汉字。
```

**Layer 3: global FOOTER**
```
画面严禁出现任何字幕、简体字、印刷体、现代字符、印章、logo、水印。
```

### "Control, don't ban" strategy

When the scene logically contains text (calligraphy, documents), you can't ban it outright. **Allow**: blurred Song-style vertical brushwork as background texture. **Forbid**: legible blocks of characters, simplified Chinese, modern typography.

### Best practice

- Source treatment: scrub annotation text off the reference image before submission (the root cause fix).
- Prompt fallback: append "画面严禁出现任何文字" at the end.
- Combine both (recommended).

---

## Module 7: Content safety notes

### Common trigger scenarios

- Realistic depictions of national / ethnic confrontation.
- Intense violence or gore.
- Politically or terror-adjacent sensitive subject matter.

### Mitigation

- Replace real country / organization names with fictional ones.
- Soften violence wording ("激烈冲突" → "激烈竞争").
- Avoid direct re-enactment of real political events.
- On generation failure, scan the prompt for sensitive terms and substitute.

### Model sensitivity differences

- **1.0 trips safety filters more easily than 1.1** — the same prompt passing on 1.1 but failing on 1.0 has been verified repeatedly.
- 1.1 is more tolerant of fictional substitutions.

---

## Module 8: Multi-segment continuous narrative

### Templating HEADER / FOOTER

Multiple segments share the same HEADER (character mapping + style + character cards) and FOOTER (lip-sync + consistency + text defence). Only the middle storyboard body differs per segment.

### Continuity bridge text

Open each segment with a "延续上段" description:

```
延续上段：男人笔尖停住，文书上有未干墨晕；女人位于书案左后方。
```

### Chain vs. Spatial strategy

| Strategy | Reference images | Bridge quality | Cost |
|----------|------------------|----------------|------|
| Spatial (text anchor) | Static Image1+2+3 only | ⭐⭐ Text description guess, visible breaks | Low |
| Chain (frame anchor) | Image1+2+3 + previous-segment mid + previous-segment last | ⭐⭐⭐⭐ Visual alignment | Medium (frame extraction) |

Chain frame-extraction pattern:
- CLIP1 → CLIP2A: use mid3s + last frame (avoid a macro close-up last frame with no character).
- CLIP2A → 2B / 2B → 2C: use mid4s + last frame.
- Last-frame command: `ffmpeg -sseof -0.1 -i input.mp4 -vframes 1 out.png`
- Mid-frame: `ffmpeg -ss 4 -i input.mp4 -vframes 1 out.png`

### Fadeout fallback

When inter-segment visual breaks are unavoidable, soft-join with ffmpeg xfade:

```bash
ffmpeg -y -i clip1.mp4 -i clip2.mp4 \
  -filter_complex "[0:v][1:v]xfade=transition=fade:duration=0.4:offset=11.72[vout];[0:a][1:a]acrossfade=d=0.4[aout]" \
  -map "[vout]" -map "[aout]" -c:v libx264 -crf 18 output.mp4
```

- Normal break: 0.4s fade.
- Severe break: 1.0s fade.
- offset = cumulative duration of the first segment − fade duration.

---

## Module 9: 1.0 vs 1.1 capability matrix

| Dimension | 1.0 | 1.1 |
|-----------|-----|-----|
| Instruction following | Medium (soft-hint understanding) | Strong (literal execution, prone to over-compliance) |
| Performance freedom | High (natural, improvisational feel) | Low (needs loose mode to feel natural) |
| Reference-image fidelity | Medium | High (will render image text) |
| Dialogue execution rate | Medium-low | High |
| Content safety threshold | Strict (easier to trip) | Permissive |
| Chinese-prompt quality | Weaker than English | Near parity with English |
| Encoding efficiency | Average | High (20–30% smaller file size at same quality) |
| Timecode response | Soft hint | Hard switch (can feel rigid in emotion scenes) |
| Generation time (15s 1080P) | ~14 min | ~12 min |
| API model name | `happyhorse-1.0-r2v` | `happyhorse-1.1-r2v` |

### Selection guidance

- **Spatial / prop / character consistency + multi-shot orchestration + dialogue-heavy**: pick 1.1.
- **Single-character micro-acting + restrained emotion + "soul" performance**: pick 1.0, or 1.1 + loose mode.
- **Content close to the safety boundary**: pick 1.1 (more permissive).
- **Chinese-first prompts**: pick 1.1 (the CN/EN gap has closed).

---

## Module 10: Case library

### Case 1 — Period-drama woman, restrained tears (single-character expression + loose mode + dolly)

**Type**: R2V / 1 reference / 9:16 / 15s
**Model**: 1.1 loose mode best; 1.0 raw-instruction also good
**File**: `guzhuangnv_15s_combo_v15_3.mp4`

```
[Image 1]为古风女子参考。

古风写实情感戏，单一连续镜头 15 秒一镜到底，无剪切。

【人物】[Image 1]女子：黑发束高髻配金步摇，浅米色绣花交领襦裙，柔暖光从画面右上斜入，皮肤纹理真实，电影级浅景深。严格保持[Image 1]女子面容、发饰、服饰一致。

【表演】女子从安静平静慢慢转入克制难过，全程视线低垂，不抬头不甩头不大幅转脸。开场她神情平静，呼吸平缓；接着嘴唇轻抿，嘴角微微下压，眉头轻皱，喉头一动像在咽下情绪，眼神变得失落委屈。她极轻极慢地开口说出这句话，每个字都带着克制的气声和哽咽，像从胸腔里压出来：「我……终究是错付了。」说话时眼眶逐渐泛起水光。话说完后她抿住嘴，左侧脸颊缓缓滑下一两滴细小自然的泪滴或泪痕，努力忍住不让自己哭出声。

【镜头运动】镜头从胸像中近景开始，全程极其缓慢、平稳、匀速地向前推进（dolly in），最终落在女子面部脸庞特写（眼眶、泪痕、抿唇全部清晰可见）。推进速度极慢，不晃动不变焦不切镜，整体推近幅度大约 1.3 倍。

【表情禁区】全程表情自然细腻，情绪安稳隐忍，不大哭，不张嘴哭喊，不夸张抽泣，不撇嘴，不挑眉，不甩头，不抬眼盯镜头。

【音频】只保留人物极轻微的真实声音：轻微鼻息、压抑呼吸、短促吸气、低声哽咽和克制哭腔混在台词里，台词整体音量很轻贴近面部，环境音几乎为零，无背景音乐。

【画面】背景采用浅景深虚化处理，隐约可见深色木制家具和屏风，柔暖光从画面右上斜入。无字幕，无文字，无水印。
```

**Lessons**:
- Loose mode (drop timecodes + drop second-level pauses) restores natural performance on 1.1.
- Putting 【镜头运动】 in its own block stops it from contaminating the performance block.
- A "禁区" (forbidden actions) list controls over-acting better than positive prescriptions.
- Multiple resamples of the same prompt vary noticeably (8.1–8.5 MB) — picking the best take is a necessary step.

---

### Case 2 — Song-dynasty study, two-character dialogue (multi-segment, Plan C three-way split)

**Type**: R2V / 3 references / 16:9 / 8+8+5s (Plan C)
**Model**: 1.1
**File**: `song_clip2_methodC_v15.mp4` (21.3s stitched)

**CLIP2A (8s) example prompt**:

```
[Image 1]为书房场景参考，[Image 2]为男人参考，[Image 3]为女人参考。

写实古装情感短剧，宋代夜晚书房。电影级浅景深，低饱和宋代美学，微胶片颗粒。
空间布局（必须严格遵守）：书案横置中央，男坐右前方正中，女站左后方约0.5米；烛台右侧/砚台左前/窗左后。
[Image 2]男人：宋代文官，深色圆领袍，束发，神色疲惫克制。
[Image 3]女人：宋代已婚女子，浅色褙子，发髻简洁，气质冷静压着情绪。

延续上段：男人执笔疲惫悬停，文书上有宋代竖排行书（柔焦模糊）与未干墨晕。

[00:00-00:04] [中景] 女人从画面左后方缓步走近书案...
[女人/低声/平静关切/"你写了一夜。"]
[00:04-00:08] [近景] 男人手指微微收紧笔杆...
[男人/沉默/疲惫迟疑/无台词]

人物口型与台词自然同步，每句台词必须完整念出不省略。
严格保持面容服饰一致，光线方向与人物站位必须与空间布局完全一致。
所有纸面文字必须是宋代竖排毛笔行书风格的模糊背景质感。
```

**Lessons**:
- Plan C (8+8+5) three-way split keeps dialogue density ≤ 2 lines per segment → highest lip-sync rate.
- Line-duration formula: 4 chars/sec × 1.2 emotion factor; 17 characters needs a minimum of 5.1s.
- HEADER / FOOTER templating: all three segments share the declaration, style, character cards, and constraint footer.
- "延续上段" + spatial constraints give baseline continuity.

---

### Case 3 — Korean-webtoon convenience store, 9-cell storyboard (cell-numbering method)

**Type**: R2V / 1 reference (3×3 grid) / 16:9 / 15s
**Model**: 1.0 and 1.1 both SUCCEEDED

```
按照故事板序列生成视频。参考图片是一张 3x3 的故事板拼图。请严格按照从左到右、从上到下的顺序...
【风格与氛围】韩漫电影感，温暖店内灯光与冷色雨夜对比...
【角色设定】女主：穿长外套的年轻女生...
【分镜指令】
格子1（左上）：全景，雨夜街角的便利店亮着暖白灯光。
...
格子9（右下）：收束镜头，女主捧着热饮站在店门外。
【生成要求】保持角色特征与光影氛围全程一致。
```

**Lessons**:
- "Cell N (position)" numbering + explicit reading-order declaration.
- Dialogue uses Korean to match the webtoon culture.
- A 9-cell storyboard at 15s R2V can be generated in a single pass.

---

### Case 4 — Cyberpunk chase (no timecodes, continuous action stream)

**Type**: T2V / 16:9 / 15s
**Model**: 1.1 SUCCEEDED

**Characteristics**: 1814 English characters, no timecodes anywhere, pure continuous narration.

**Lessons**:
- High-density action sequences don't need timecodes — continuous flow narration reads more naturally.
- Without timecodes the model schedules pacing freely; action transitions are smoother.
- A long English prompt (1800+ chars) is completely workable on 1.1.

---

### Case 5 — Happy Run v5 (text-residue mitigation + API parameter gotcha)

**Type**: R2V / 1 reference / 16:9 / 15s
**Model**: 1.1

**Iteration path**: v1 (text residue) → v2 (add text-ban constraint) → v3 (narration-style) → v4 (stronger camera) → v5 (fully tuned).

**Lessons**:
- The `size` parameter value `1080P` is deprecated — use `1920*1080`.
- A bare "No text on screen" is not enough to fight 1.1's reference-image fidelity — escalate to the full three-layer defence.
- Narration-style dialogue (`旁白：「xxx」`) is less likely to trip lip-sync conflicts than direct quotation.

---

### Case 6 — Athletic competition T2V (content-safety case study)

**Type**: T2V / 16:9 / 15s
**Model**: v1 (real country names) failed on both 1.0 and 1.1 → v2 (fictional team names) passed on 1.1 / still failed on 1.0.

**Lessons**:
- Realistic national-confrontation imagery is a safety red line — substitute fictional names.
- 1.0's safety review is stricter than 1.1's.
- Failed jobs do not return the original prompt — keep a local copy.

---

## Appendix A: API parameter cheatsheet

| Parameter | Value |
|-----------|-------|
| 1.1 model | `happyhorse-1.1-r2v` / `happyhorse-1.1-i2v` / `happyhorse-1.1-t2v` |
| 1.0 model | `happyhorse-1.0-r2v` / `happyhorse-1.0-i2v` / `happyhorse-1.0-t2v` |
| media type | `reference_image` (R2V) / `first_frame` (I2V) |
| size | `1920*1080` / `1080*1920` (portrait) — `1080P` is deprecated |
| ratio | 16:9 / 9:16 / 3:4 / 4:3 / 1:1 etc. |
| duration | 3–15 seconds |
| Image format | URL or `data:image/png;base64,...` |
| Reference image count | 1–9 |

## Appendix B: Diagnostic checklist

### Model won't speak the line (lip-sync failure)

1. Reduce dialogue density (≤ 2 lines per segment).
2. Drop entry-action descriptions (don't write "walks in" if the character is already on screen).
3. Add a mouth-trigger verb just before the line ("张口" / "嘴唇微动").
4. Verify the time window is long enough (4 chars/sec × 1.2).

### Model "adds drama" (improvises outside prompt)

1. Shorten duration (15s → 12s/10s).
2. Pad with silence placeholders: `[role/沉默/emotion/无台词]`.
3. Check whether the prompt content actually covers the target duration.

### Severe inter-segment breaks

1. Verify the `reference_image` list includes frames from the previous segment (chain vs spatial).
2. Add an ffmpeg xfade 0.4–1.0s fallback.
3. Make the "延续上段" description more specific (positions / hands / light / prop state).

### Text bleeding into the picture

1. Scrub annotations from the reference image at the source.
2. Fill in all three defence layers.
3. Switch to the "control, don't ban" strategy (allow blurred brushwork texture).

## Appendix C: Dialogue duration math

```
Net duration = char count ÷ 4 × 1.2 (emotion scenes)
Buffer = +0.5s short line / +1.0s long line
```

Example: `「我……终究是错付了。」` = 8 characters (ellipsis counted as one) ÷ 4 × 1.2 = 2.4s + ~1.5s pause buffer ≈ allocate 4–5s.

A single 12s segment fits ~32 characters of dialogue, 15s fits ~40. Beyond that, split.
