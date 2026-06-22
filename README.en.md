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

### T2V Text-to-Video (1.1)

> [Explore all 1.1 T2V prompts →](cases/t2v-1.1.en.md)

**Long-context scheduling:** describe 6–8 sequential beats in a single prompt; the model allocates shot durations automatically.

See full case `Classroom Pure Love — Japanese youth short film` in [cases/t2v-1.1.en.md](cases/t2v-1.1.en.md).

### I2V Image-to-Video (1.1)

> [Explore all 1.1 I2V prompts →](cases/i2v-1.1.en.md)

**Smoother motion + better fidelity:** use the first frame as the visual anchor and keep prompts focused on motion / camera / SFX.

See `Bamboo Forest Duel — ink-wash wuxia` in [cases/i2v-1.1.en.md](cases/i2v-1.1.en.md).

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
