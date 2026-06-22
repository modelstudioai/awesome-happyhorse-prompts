# Awesome HappyHorse Prompts

<div align="center">

<img src="assets/happyhorse-banner.png" width="100%" alt="HappyHorse 1.1 Banner">

A curated collection of high-quality prompts, creative workflows, and usage guides for HappyHorse 1.0 & 1.1 video generation models (Text-to-Video / Image-to-Video / Reference-to-Video / Video Edit).

🌐 **Language:** English · [🇨🇳 中文](README.md)

[![HappyHorse](https://img.shields.io/badge/HappyHorse-🐴%20Site-orange)](https://www.happyhorse.com/)
<a href="https://modelstudio.console.alibabacloud.com/ap-southeast-1?tab=dashboard&source_channel=HHpromptRe#/efm/model_experience_center/vision/videoGenerate"><img src="assets/bailian-logo.png" height="20" alt="Aliyun Model Studio"></a>
[![Last Commit](https://img.shields.io/github/last-commit/modelstudioai/awesome-happyhorse-prompts)](https://github.com/modelstudioai/awesome-happyhorse-prompts/commits/main)

</div>

> **Localization note**: The English edition is a structural mirror of the Chinese repo. **Prompt bodies are kept verbatim in their original language (Chinese / English / Japanese / Korean) on purpose** — they are the artefacts under test and re-translating them would change what the model receives. Each prompt is preceded by an English **"Prompt intent"** block describing scenario, control levers, and what to swap when adapting to your own brief.

## 🌟 Model Highlights

[HappyHorse 1.1](https://modelstudio.console.alibabacloud.com/ap-southeast-1?tab=model&source_channel=hhpromptrepo#/model-market/detail/happyhorse-1.1-t2v?serviceSite=asia-pacific-china) is the next-generation video generation model. Built on top of 1.0, it upgrades dynamic expressiveness, character consistency, instruction following, visual fidelity, and audio capabilities — purpose-built for short drama, e-commerce ads, brand campaigns, and game CGs.

- **Stronger motion modelling** — improved temporal consistency, smoother and more powerful action.
- **Multi-reference consistency (R2V)** — multi-character references no longer leak into each other; characters and scenes can be combined freely; 3×3 storyboards stay consistent panel-to-panel.
- **Long instructions & complex scheduling** — a single prompt can drive 6–8 sequential shots; multi-character spatial relationships are more accurate.
- **Visual fidelity uplift** — natural skin and facial detail, especially in close-ups.
- **Native audio-video synergy** — dialogue pacing, pauses and ambient SFX are jointly generated and can be steered (or disabled) from the prompt.

## 📖 Model Overview

| Model | Capability | I/O | Pricing |
|-------|-----------|-----|---------|
| [happyhorse-1.1-i2v](https://modelstudio.console.alibabacloud.com/ap-southeast-1?tab=model&source_channel=hhpromptrepo#/model-market/detail/happyhorse-1.1-i2v?serviceSite=asia-pacific-china) | Animates a first frame guided by a text description; physically plausible motion. | Image + Text → Video | 720P: ¥0.9/s · 1080P: ¥1.2/s · 10 s free quota · **40% off Jun 22 – Jul 6** (USD pricing TBC, see console) |
| [happyhorse-1.1-t2v](https://modelstudio.console.alibabacloud.com/ap-southeast-1?tab=model&source_channel=hhpromptrepo#/model-market/detail/happyhorse-1.1-t2v?serviceSite=asia-pacific-china) | Text-to-video with realistic physics and smooth motion. | Text → Video | 720P: ¥0.9/s · 1080P: ¥1.2/s · 10 s free quota · **40% off Jun 22 – Jul 6** |
| [happyhorse-1.1-r2v](https://modelstudio.console.alibabacloud.com/ap-southeast-1?tab=model&source_channel=hhpromptrepo#/model-market/detail/happyhorse-1.1-r2v?serviceSite=asia-pacific-china) | Multi-image / 3×3 storyboard guided generation; preserves character & scene identity. | Reference Images + Text → Video | 720P: ¥0.9/s · 1080P: ¥1.2/s · 10 s free quota · **40% off Jun 22 – Jul 6** |
| happyhorse-1.0-video-edit | Style transfer and local element replacement on existing video, optionally guided by a reference image. | Video + Text (+ Reference) → Video | 720P: ¥0.9/s · 1080P: ¥1.6/s · 10 s free quota |

> 💡 HappyHorse 1.0 family stays at **20% off** until 2026-07-06.
>
> ⚠️ HappyHorse natively supports Mandarin Chinese, English, and Japanese; more languages are rolling out.

## Contents

### HappyHorse 1.1

- [T2V Text-to-Video (1.1)](cases/t2v-1.1.en.md)
- [I2V Image-to-Video (1.1)](cases/i2v-1.1.en.md)
- [R2V Reference-to-Video (1.1)](cases/r2v-1.1.en.md)

### HappyHorse 1.0

- [T2V Text-to-Video](cases/t2v.en.md)
- [I2V Image-to-Video](cases/i2v.en.md)
- [R2V Reference-to-Video](cases/r2v.en.md)
- [Video Edit](cases/video-edit.en.md)
- [E-commerce Cases](cases/ecommerce.en.md)
- [API Reference](#api-reference)
- [Prompt Craft Skill (full spec)](happyhorse-prompt-craft-SKILL.en.md)

---

## 🎬 HappyHorse 1.1 Featured Demos

### R2V Reference-to-Video (1.1)

> [Explore all 1.1 R2V prompts →](cases/r2v-1.1.en.md)

**3×3 storyboard consistency:** upload a 3×3 panel sheet and the model generates a continuous sequence panel-by-panel.

#### Convenience Store Healing Night — K-drama 3×3 storyboard

**Reference:**

| Storyboard reference |
|:---:|
| <img src="videos/r2v-1.1/images/ref_storyboard_convenience.png" width="300" alt="Convenience store storyboard"> |

> **Prompt intent (EN annotation):** Drive a 9-shot K-drama-style sequence from a single 3×3 storyboard image. Control levers worth tuning when you adapt: (a) panel reading order (locked left-to-right, top-to-bottom), (b) tonal contrast — warm interior vs. cold rainy night, (c) global "no on-screen text" guard, (d) per-panel framing keywords (wide / medium / close-up / extreme close-up), (e) the embedded Korean line `오늘도 수고 많았어요.` (kept verbatim — translating it removes the cultural marker and the lip-sync test).

**Prompt (verbatim):**
```
按照故事板序列生成视频。[Image1] 是一张 3x3 的故事板拼图。请严格按照从左到右、从上到下的顺序（左上→中上→右上→左中→中中→右中→左下→中下→右下），将每个格子视为视频的一个独立镜头，依次生成连贯序列。
【风格与氛围】韩漫电影感，温暖店内灯光与冷色雨夜对比，治愈、安静、微孤独。画面严禁出现任何文字。
【角色设定】女主：穿长外套的年轻女生，发丝微湿，疲惫但温柔。店员：清爽短发的便利店夜班少年。
【分镜指令】
格子1（左上）：全景，雨夜街角的便利店亮着暖白灯光。
格子2（中上）：中景，女主推门进店，肩带夜雨湿气。
格子3（右上）：近景，女主站在热饮柜前微微发呆。
格子4（左中）：中景，店员从收银台抬头看向她。
格子5（中中）：特写，热饮柜橙色暖光映在她手边。
格子6（右中）：近景，女主拿起热饮，神情放松。
格子7（左下）：近景，店员露出温和克制的微笑，说："오늘도 수고 많았어요."
格子8（中下）：中景，女主回以浅笑，疲惫感被冲淡。
格子9（右下）：收束镜头，女主捧着热饮站在店门外，背影被灯光映得温柔。
【生成要求】保持每张格子的构图与镜头语言，镜头运动平滑，在镜头间创建自然转场。角色特征与光影氛围全程一致。
```

**Output:**

**HappyHorse 1.1**

https://github.com/user-attachments/assets/12e1284b-89df-40e2-b539-9f8dabc3274e

**HappyHorse 1.0**

https://github.com/user-attachments/assets/245378f7-1096-4b70-86a9-8ac37bfcd471

---

#### Girl & Cats — Japanese animated-film storyboard

**Reference:**

| Storyboard reference |
|:---:|
| <img src="videos/r2v-1.1/images/girlcats.png" width="300" alt="Girl & cats storyboard"> |

> **Prompt intent (EN annotation):** A 9-shot pastoral piece driven by a single 3×3 storyboard, styled as a Japanese animated short. Levers worth tuning: (a) anchor character + companion + hero prop (girl + tabby kitten + glass wind chime); (b) seasonal palette (summer countryside, warm sunlight, nostalgic); (c) panel-level beat list runs from discovery → curiosity → connection → wide establishing → golden-hour close; (d) global "no on-screen text or grid lines" guard so the 3×3 reference doesn't leak into the output.

**Prompt (verbatim):**
```
按照故事板序列生成视频。[Image 1] 是一张 3x3 的故事板拼图。请严格按从左到右、从上到下的顺序，将每个格子视为视频的一个独立镜头，依次生成连贯序列。
【风格与氛围】日系动画电影感，夏日乡村、温暖阳光、清新治愈、安静怀旧。画面严禁出现任何文字或拼图网格线。
【角色设定】主角：穿浅黄色连衣裙的小女孩，黑色短发。配角：灰色虎斑小猫，圆眼好奇。核心道具：挂在日本乡村老屋檐下的透明玻璃风铃。
【分镜指令】格子1：女孩在木质门廊边发现风铃；格子2：花丛后小猫探头观察；格子3：风铃在蓝天下随风摇晃；格子4：女孩蹲下身把风铃放低给小猫看；格子5：小猫伸爪轻触风铃纸签；格子6：女孩开心地抱起小猫；格子7：女孩和小猫并肩坐在门廊上；格子8：大全景展现宁静夏日乡村；格子9：夕阳金光中的风铃轻摇收束。
【生成要求】保持每格构图与镜头语言，角色外貌与光影氛围全程一致，镜头运动柔和自然，整体像一支温柔的动画电影片段。
```

**Output:**

**HappyHorse 1.1**

https://github.com/user-attachments/assets/43a583b3-5e9e-4411-90f9-66e094cb7b4c

**HappyHorse 1.0**

https://github.com/user-attachments/assets/db952559-1271-4f06-8d68-3a6028683715

---

#### Happy Run Citrus — Japanese youth sports-drink ad

**Reference:**

| Storyboard reference |
|:---:|
| <img src="videos/r2v-1.1/images/happyrunv3.png" width="300" alt="Happy Run citrus ad storyboard"> |

> **Prompt intent (EN annotation):** A 9-panel commercial-grade storyboard run for a fictional sports-drink brand. Levers worth tuning: (a) explicit aspect ratio reminder (`16:9`) baked into the prompt — keeps the model from cropping mid-panel; (b) brand color spec locked in two complementary hues (橙色外套 ↔ 蓝色饮料瓶); (c) panel beats follow a CM (Japanese commercial) arc — product reveal → drinking shot → action montage → group bonding → hero shot; (d) global "no extra text or watermark" guard protects the brand-clean look.

**Prompt (verbatim):**
```
按照故事板序列生成一支日系青春汽水广告视频。[Image 1] 是一张 16:9 的 3x3 故事板拼图。请严格按照左上→中上→右上→左中→中中→右中→左下→中下→右下的顺序，将每个格子视为一个独立镜头，依次生成连贯广告片段。
【整体风格】日本夏日运动饮料广告风格，青春、清爽、阳光、积极、带一点日剧 CM 的热血感。写实真人广告质感，蓝天、城市天台、篮球场、河岸 skyline、橙色运动外套与蓝色饮料瓶形成强烈品牌色对比。
【角色与产品】女主：年轻日本女生，短发或中短发，穿橙色轻薄运动外套、白色短上衣、深蓝运动裤，气质清爽自信。产品为蓝橙配色的 Happy Run Citrus 能量汽水瓶，瓶身有冷凝水珠，阳光下闪光。
【分镜指令】格子1：城市天台女主递出饮料瓶；格子2：女主仰头喝 Happy Run；格子3：女主在天台篮球场奔跑；格子4：女主坐在户外长椅上专注学习；格子5：三人击拳互动；格子6：夕阳下女主望向城市；格子7：女主自信望向远方；格子8：品牌主视觉镜头；格子9：三人碰瓶开心大笑收束。
【生成要求】保持每格构图与人物位置关系，镜头间自然转场，角色脸部、服装、产品、蓝橙品牌色全程一致。写实高清广告片质感，不要多余文字和水印。
```

**Output:**

**HappyHorse 1.1**

https://github.com/user-attachments/assets/368387bc-138d-4b58-91f3-03c4fb11e429

**HappyHorse 1.0**

https://github.com/user-attachments/assets/2bbc2dd9-47f5-4fb3-a563-d2b6e60fe75e

---

### T2V Text-to-Video (1.1)

> [Explore all 1.1 T2V prompts →](cases/t2v-1.1.en.md)

**Long-context scheduling:** describe 6–8 sequential beats in a single prompt; the model allocates shot durations automatically.

#### Classroom Pure Love — Japanese youth short film

> **Prompt intent (EN annotation):** A single-prompt 15-second cinematic piece — no reference images, no first frame — leaning entirely on T2V's long-context scheduler. Levers worth tuning: (a) duration ("15秒") and quality marker ("电影级…超写实") prefixed before any beat description, so the model allocates pacing globally; (b) loose narrative description rather than rigid timecodes (works better for emotional/performance scenes per the 1.1 craft guide); (c) atmosphere-first noun stacking (afternoon empty classroom · warm gold sunlight · venetian blinds · paired desks).

**Prompt (verbatim):**
```
15秒电影级日式纯爱暧昧短片，超写实画质。午后空教室暖金色阳光透过百叶窗洒在并排课桌上...
```

> Full prompt and shot-by-shot annotations: [cases/t2v-1.1.en.md](cases/t2v-1.1.en.md).

**Output:**

**HappyHorse 1.1**

https://github.com/user-attachments/assets/dfe29214-c823-446d-a732-58cc64af37b1

**HappyHorse 1.0**

https://github.com/user-attachments/assets/1bfdb3d3-6c08-466f-bdfb-1d980b4a4280

---

### I2V Image-to-Video (1.1)

> [Explore all 1.1 I2V prompts →](cases/i2v-1.1.en.md)

**Smoother motion + better fidelity:** use the first frame as the visual anchor and keep prompts focused on motion / camera / SFX.

#### Bamboo Forest Duel — ink-wash wuxia

**First-frame reference:**

| First-frame reference |
|:---:|
| <img src="videos/i2v-1.1/images/bamboo.png" width="300" alt="Bamboo first frame"> |

> **Prompt intent (EN annotation):** Demonstrates 1.1 I2V's English-prompt support and the "30–60 character minimalism" principle — the first frame already encodes character + setting + lighting, so the prompt only describes motion + camera + audio. Levers worth tuning: (a) wind/atmosphere verb ("surges") sets a global motion intensity; (b) explicit physical action ("leaps onto bamboo tips") gives the model a kinematic anchor; (c) camera language is implicit, letting the model auto-allocate movement.

**Prompt (verbatim):**
```
Wind surges through the bamboo forest. The white-robed swordswoman leaps onto bamboo tips...
```

> Full prompt: [cases/i2v-1.1.en.md](cases/i2v-1.1.en.md).

**Output:**

**HappyHorse 1.1**

https://github.com/user-attachments/assets/c93c9a2c-2228-44aa-91dd-37db35ff8d1e

**HappyHorse 1.0**

https://github.com/user-attachments/assets/9d467975-4663-458f-8668-e134b519b428

---

## 🎬 HappyHorse 1.0 Featured Demos

### T2V Text-to-Video

> **11 curated cases** — [Explore all T2V prompts →](cases/t2v.en.md)

**Prompt formula:** `prompt = scene + subject + motion + audio`

| scene | Where the action takes place — environment, lighting, mood. |
| subject | Who or what the camera is centred on (person, animal, object, imaginary entity). |
| motion | Both subject motion and ambient motion (still / subtle / large / partial / global). |
| audio | Dialogue, SFX, ambient or music cues that should track the visuals. |

### I2V Image-to-Video (first-frame seeded)

> **8 curated cases** — [Explore all I2V prompts →](cases/i2v.en.md)

**When to use:** you already have an artwork, product shot or portrait you want to bring to life; describe what happens *after* the first frame.

### R2V Reference-to-Video (multi-image)

> **5 curated cases** — [Explore all R2V prompts →](cases/r2v.en.md)

**When to use:** you need character or scene identity preserved across shots, or you want to combine multiple visual elements (character + scene + logo) in one clip. Refer to images in the prompt as `[Image 1]`, `[Image 2]`, … (the space between `Image` and the number is required by the API parser).

### Video Edit (style transfer / element swap)

> **6 curated cases** — [Explore all Video Edit prompts →](cases/video-edit.en.md)

**When to use:** you have a finished video and need a stylistic re-skin or a localised element swap, while keeping the original camera path and timing intact.

### 🐴 E-commerce Cases

> **2 curated cases** — [Explore all E-commerce prompts →](cases/ecommerce.en.md)

Period-drama short-form ads with product placement (perfume, skincare).

---

## 💻 API Reference

**Endpoints:**
- China (Beijing): `POST https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis`
- International (Singapore): `POST https://dashscope-intl.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis`

**Try it:**
- China: [Bailian Console — HappyHorse experience center](https://bailian.console.aliyun.com/cn-beijing?tab=demohouse&source_channel=hhpromptrepo#/experience/t2v)
- International: [ModelStudio Console](https://modelstudio.console.alibabacloud.com/ap-southeast-1?tab=dashboard&source_channel=HHpromptRe#/efm/model_experience_center/vision/videoGenerate)

**Prompt craft guide:**
- In-repo skill: [happyhorse-prompt-craft-SKILL.en.md](happyhorse-prompt-craft-SKILL.en.md) — practical prompt-engineering playbook for HappyHorse 1.0 / 1.1 R2V / I2V / T2V.

---

## 🤝 Contributing

Pull requests welcome. See [Contributing.en.md](Contributing.en.md). Please make sure prompts are original or properly licensed, include the model name and parameters, and add a short description of the generated output.

## 📄 License

[CC BY 4.0](LICENSE)
