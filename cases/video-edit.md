# Video Edit 视频编辑（风格转换/元素替换）案例

> 对已有视频进行 AI 智能编辑，无需从零生成，在原片基础上实现精准修改。你可以通过文字提示词描述修改意图，也可以同时上传参考图片提供视觉引导，两种方式可灵活搭配使用。

**适用场景：**
- 对视频整体风格不满意，想转换画面氛围（如写实转动漫、白天转黄昏）
- 需要修改画面中的局部元素（如替换背景、改变服装颜色、添加天气特效）
- 有一张目标风格的参考图，希望视频整体视觉效果向其靠拢
- 需要将视频中的某个元素替换为参考图中的特定对象
- 对AI生成的视频做二次修正，微调动作或画面细节

**书写建议：** 提示词中明确指出"改什么"和"保留什么"。描述越具体，模型越能精准执行编辑，避免误改不需要调整的部分。

---

### Case 1: 古风服装替换 — 雾霾蓝明制汉服

**模型:** `happyhorse-1.0-video-edit`

**Prompt:**
```
参考 Image 1，将视频中女主的衣服替换为图中所示的雾霾蓝明制汉服。汉服必须完全贴合女主的身形轮廓和动作姿态，宽大的袖子需跟随她的手臂运动自然摆动，立领和衣襟的层次感要随身体转动合理呈现。仙鹤与花卉刺绣的图案位置、比例和细节必须严格参照 Image 1，刺绣表面的光泽、阴影和材质质感必须与原视频环境的光源保持一致。在此过程中，女主的面部表情、发型、肤色、背景环境以及镜头的运镜轨迹必须保持 100% 不变。
```
**输入素材：**

| 参考图 |
|:---:|
| <img src="../videos/video-edit/images/videoeditcase1input.jpeg" width="300" alt="参考图"> |

**输入视频：**

https://github.com/user-attachments/assets/a43226c7-9592-4943-911d-8f88ae0f39cb

**输出效果：**

https://github.com/user-attachments/assets/630e2fdf-e069-4e2c-9392-d0217d8b0ade

---

### Case 2: 元素替换 — 白色邮轮变太空飞船

**模型:** `happyhorse-1.0-video-edit`

**Prompt:**
```
参考 Image 1，将视频中正在行驶的白色邮轮替换为图中所示的太空飞船。飞船必须完全遵循原邮轮的行驶轨迹、速度和朝向，严丝合缝地嵌入场景中。确保飞船表面的光照、反射和阴影与原视频环境的光源保持一致。在替换过程中，周围的背景、水面、天空以及镜头的运镜轨迹必须保持 100% 不变。
```
**输入素材：**

| 参考图 |
|:---:|
| <img src="../videos/video-edit/images/videoeditcase2input.png" width="300" alt="参考图"> |

**输入视频：**

https://github.com/user-attachments/assets/125d1f81-c654-490c-aeec-97b986ba7b5b

**输出效果：**

https://github.com/user-attachments/assets/ee135e9b-31c7-4821-9e8d-fd790f6c260d

---

### Case 3: 水墨画风格转换

**模型:** `happyhorse-1.0-video-edit`

**Prompt:**
```
参考Image 1中的视觉特征，将视频整体风格转化为传统黑白水墨画风格，把画面中的山脉、雾气、建筑等所有元素全部重塑为具有墨色浓淡变化的写意笔触，在保留原视频运镜轨迹与场景结构完全不变的同时，呈现出一种黑白分明、意境深远的中国水墨视觉效果。
```
**输入素材：**

| 参考图 |
|:---:|
| <img src="../videos/video-edit/images/videoeditcase3input.png" width="300" alt="参考图"> |

**输入视频：**

https://github.com/user-attachments/assets/2d2bd61f-bf6e-486e-ab52-a87b8f413d80

**输出效果：**

https://github.com/user-attachments/assets/c883624e-dd80-4326-bffa-dbeeab30341b

---

### Case 4: 赛博朋克风格转换

**模型:** `happyhorse-1.0-video-edit`

**Prompt:**
```
Transform the city into a cyberpunk style.
```
**输入视频：**

https://github.com/user-attachments/assets/ee2e4292-a85c-4c68-8950-23cf2780c297

**输出效果：**

https://github.com/user-attachments/assets/30ea0ef0-b2ac-462e-ac59-adcfbf5244c1

---

### Case 5: Minecraft 体素风格转换

**模型:** `happyhorse-1.0-video-edit`

**Prompt:**
```
Transform the entire video into the Minecraft voxel style based on the visual aesthetic of Image 1. Convert all subjects, characters, and the environment into 3D blocks with low-resolution pixelated textures. Ensure the lighting and colors match the blocky world shown in Image 1. Throughout this transformation, the original movements, character actions, and camera tracking path must remain 100% unchanged. The final result should look like the original scene has been completely rebuilt inside the Minecraft game world.
```
**输入素材：**

| 参考图 |
|:---:|
| <img src="../videos/video-edit/images/videoeditcase5input.png" width="300" alt="参考图"> |

**输入视频：**

https://github.com/user-attachments/assets/eb03e303-ec49-4bfe-ae79-7b65111f4119

**输出效果：**

https://github.com/user-attachments/assets/b1e7e3a0-1f8f-45c1-8422-492ae684633c

---

### Case 6: 猫咪换眼镜 + 音乐舞蹈

**模型:** `happyhorse-1.0-video-edit`

**Prompt:**
```
将视频中猫戴的黑框眼镜替换为参考图中的金丝框眼镜。同时修改猫的动态，让它随着动感的音乐节奏有节奏地左右摇摆头部和身体，呈现出一种在听音乐跳舞的视觉效果。摇摆动作应丝滑、富有活力且富有韵律感。在此过程中，必须保持猫的品种外观、背景环境以及镜头的运镜轨迹100%不变。确保金丝眼镜在猫摇摆时始终精准地贴合在它的脸上，并随其头部动作自然移动。
```
**输入素材：**

| 参考图 |
|:---:|
| <img src="../videos/video-edit/images/videoeditcase6input.png" width="300" alt="参考图"> |

**输入视频：**

https://github.com/user-attachments/assets/cc472bfa-9f0a-4aff-a334-c79d1c5d935e

**输出效果：**

https://github.com/user-attachments/assets/9b57f2de-7e1c-47ae-afa3-0c2bdd639b40

