# E-Commerce Application Cases

🌐 **Language:** English · [🇨🇳 中文](ecommerce.md)
>
> HappyHorse 1.0 applied to e-commerce marketing — selling products through period-drama storytelling. The original Chinese prompts are preserved verbatim; the English annotations explain intent and the levers worth tuning.

---

### Case 1: Period-drama product placement — QWEN perfume bottle

**Model:** `happyhorse-1.0-r2v`
**Spec:** 4s 1080P × 3 segments stitched together

**Reference images:**
- Image 1: prince character
- Image 2: maid character
- Image 3: QWEN perfume bottle (amber glass body, red domed cap)

**Storyboard 1 — prompt intent (EN annotation):**
- Three-character reference setup: two characters (prince + maid) plus a hero product shot.
- Light flirtation framing — the maid's question about scent gives the perfume diegetic justification for being in frame.
- Locks: fixed camera, photoreal period-portrait look, cinematic lighting, sharp facial detail.

**Storyboard 1 prompt:**
```
4s 1080P R2V
参考「图片1」中的王爷形象与「图片2」中的丫头形象，两人在古风书房暖光场景中互动。王爷端坐案前执卷看书，神情清冷疏离。丫头身着浅绿纱衣从旁侧凑近，歪头凝视王爷侧脸，指尖轻点自己颈侧，眼神试探又带俏皮。丫头清脆问：王爷不近女色？王爷冷淡回：嗯。丫头笑：那这香气呢？案几一角放着「图片3」中的精致琥珀色香水瓶，红色圆顶瓶盖，瓶身隐约可见 QWEN 字样，在暖光下微微反光。固定机位，真人古风写真风格，电影级光影质感，面部细节清晰。
```

**Storyboard 2 — prompt intent (EN annotation):**
- Micro-expression beat — the prince's gaze drifts from book to maid's neck to the perfume bottle, signaling that the scent has registered.
- Shot scale change (slow push-in) emphasizes the subtlety; the prompt asks for fine facial micro-expressions.

**Storyboard 2 prompt:**
```
4s 1080P R2V
参考「图片1」中的王爷形象与「图片2」中的丫头形象。丫头歪头笑，眼波流转，指尖仍轻点颈侧。王爷睫毛微颤，目光不自觉落在丫头颈侧，又扫过案上香瓶。王爷执卷的手指收紧了一瞬，神情仍是清冷，但眼神已有一丝动摇。丫头俏皮追问：嗯？镜头微推，真人古风写真风格，电影级光影，面部微表情细腻。
```

**Storyboard 3 — prompt intent (EN annotation):**
- Resolution beat with a tactile action (wrist grab) and a pull-back camera move that reveals the product hero shot.
- Final frame is essentially a perfume commercial money-shot — amber liquid catching warm light, red cap as a vermilion accent.

**Storyboard 3 prompt:**
```
4s 1080P R2V
参考「图片1」中的王爷形象与「图片2」中的丫头形象。王爷忽然抬眸，眸色从清冷转为深邃。合上书卷，一把扣住丫头手腕拉近，鼻尖几乎贴上她颈侧，耳尖微红，气息低沉克制。王爷沙哑道：对你……从未。镜头缓缓从两人拉远，案上「图片3」中的 QWEN 香水瓶优雅入镜，琥珀色液体在暖光下流转，红色瓶盖如朱砂点缀。真人古风写真风格，电影级光影质感，画面温馨甜宠。
```

---

### Case 2: Palace-intrigue drama — Blue Caviar Essence

**Model:** `happyhorse-1.0-r2v`
**Spec:** 20s 1080P 16:9 / 10s 1080P 9:16

**Reference images:**
- Image 1: empress character
- Image 2: consort character
- Image 3: consort gaze close-up composition
- Image 4: two-shot composition

**Shots 1-3 — prompt intent (EN annotation):**
- Multi-shot beat (10s) inside a single prompt. Reference compositions are explicitly cited (`参考[图 3]构图`) so the model knows which framing to recreate at each beat.
- Dialogue triggers: every line is wrapped in quotes with the speaker tagged, including a mid-line tone shift ("傲慢轻蔑" → "震惊迟疑").
- Continuity guard at the end: "保持角色人物一致性" — important across multiple shots.

**Shots 1-3 prompt (10 seconds):**
```
参考[图 2]贵妃形象、[图 1]皇后形象、[图 3]贵妃抬眸特写双人构图。
宋代宫廷内景，华丽但幽暗的宫室，烛光摇曳。[图 1]带两名侍女踏入正厅，抬袖掩鼻，轻蔑打量。
[图 1]，傲慢轻蔑语气："被关了这么多日，本宫还以为你早该憔悴得见不得人了。"
[图 2]抬头特写，参考[图 3]构图，眼神清冷从容。
[图 1]，震惊迟疑语气："你……怎么一点没垮？"皇后表情从嘲讽变震惊，掩鼻的手停在半空。
运镜自然，多镜头切换，保持角色人物一致性。
```

**Shots 4-5 — prompt intent (EN annotation):**
- Product reveal moment — the essence bottle comes out of the consort's sleeve as a power move.
- Two emotional beats stacked: consort's serene confidence ("从容轻柔但带锋芒") and empress's break ("破防").
- Tone tag injected mid-dialogue (`【温柔带刺语气】`) to bend delivery without splitting the line.

**Shots 4-5 prompt (10 seconds):**
```
参考[图 2]贵妃形象、[图 1]皇后形象、[图 4]双人构图。
[图 2]从袖中取出蓝色精华液瓶，姿态从容举到脸侧，蓝色瓶身在烛光中泛幽蓝光泽，微微侧脸展示紧致轮廓，笑意温柔但带锋芒。
[图 1]站在后方，神情震惊又不甘，手指无意识摸自己眼角。
[图 4]场景下，[图 2]手持蓝色精华液瓶，[图 1]在后方破防。宋代宫廷内景，烛光摇曳。
[图 2]，从容轻柔但带锋芒："有蓝鱼子精华，当然不怕。轻轻一抹，肌肤像被提起来一样。"【温柔带刺语气】："姐姐的眼袋，该唤太医瞧瞧了。"
运镜自然，多镜头切换，保持角色人物一致性。
```

---

## E-commerce authoring tips

- Use a multi-image reference set: characters + product, with the product shot as a separate image so the model can place it as a hero element rather than treating it as a costume detail.
- Place product reveals at a "money beat" near the end of a clip — pull-back camera moves give the bottle natural framing without breaking story flow.
- Tone tags inside dialogue (`【温柔带刺语气】`) are a low-cost way to shift VO delivery without splitting the line into two prompts.
- For multi-shot single-prompt sequences, include `保持角色人物一致性` as a global lock — it materially reduces face/outfit drift across cuts.
- When several composition references exist (e.g., a wide and a close-up), cite them by index inside the dialogue beats so each cut knows which framing to recreate.
