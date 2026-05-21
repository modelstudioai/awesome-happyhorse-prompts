# I2V 图生视频（首帧）案例

> 以一张图片作视频的起始画面（首帧），模型基于该图片内容生成后续的动态视频。上传的图片即为视频第一帧，确保画面起点与你的预期完全一致。

**适用场景：**
- 有一张满意的设计稿或插画，想让它"动起来"
- 需要精确控制视频的开场画面
- 基于产品图、人像照等现有素材快速生成动态展示

**书写建议：** 提示词中重点描述"动起来之后发生什么"——动作、运动轨迹、镜头变化等。无需重复描述图片中已有的静态内容，模型会自动识别首帧画面信息。

---

### Case 1: 古风对话分镜 — 王爷与丫头

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase1image1.png)

![输入图片](images/i2v/i2vcase1image2.png)

**输出效果：**

_i2v_case1_video_url_placeholder_
分镜 1 (生成 4s)
王爷端坐执卷，丫头从旁侧凑近歪头看他。一个清脆俏皮的女声问：王爷不近女色？一个低沉冷淡的男声回：嗯。暖光透过窗棂，书房雅致。固定机位。

分镜 2 (生成 4s)
丫头指尖轻点王爷脸颊，歪头笑。王爷睫毛微颤，执卷手指收紧，仍垂眸看书。俏皮女声：那我呢？男声停顿后：……你也不行。镜头微推。
```

---

### Case 2: 直播间猫咪脱口秀

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase2image.png)

**输出效果：**

_i2v_case2_video_url_placeholder_
直播间里，两只猫咪以拟人化形象做搞笑对话，要求写实，使用台湾中年男腔调。银色猫先说话：台词"他说他要当网红"。【1-5秒】画面：银色猫扭头面向金色猫，身子站立，伸着一只前爪，尾巴摇动，动作自然。金色猫说话：台词"靠什么火？"。【5-10秒】画面：金色猫扭头看向银色猫后身子站立，伸着一只爪子，满脸不屑的表情，动作自然。银色猫说话：台词"拍我们"金色猫说话：台词"那火的是我们，关他什么事"银色猫说话：台词"他说他负责帅"金色猫说话：台词"帅在哪？"银色猫说话：台词"帅在不出镜"要求语速适中，不要抢话，最后2只猫一起哈哈哈哈哈大笑起来，笑声洪亮，动作表情跟对话内容要严丝合缝。
```

---

### Case 3: 宇航员太空舱多镜头叙事

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase3image.png)

**输出效果：**

_i2v_case3_video_url_placeholder_
【镜头一 · 0–4秒】 画面从头盔玻璃面罩内侧的水雾与光斑缓缓对焦——那些光点像是遥远星系的残影，或是某种正在消逝的记忆。红色警报光在她脸上有节律地扫过，将她的皮肤染成深红与暗影交替的律动。她的眼睛紧闭，睫毛轻轻颤动，像是在黑暗中接收某种只有她能听见的频率。镜头以极慢速度贴近面罩玻璃，试图穿透那层透明的屏障。
【镜头二 · 4–8秒】 她缓缓睁开眼睛。但眼神不是向外看的——而是向内，像是在看自己内心某个正在坍塌或重建的宇宙。镜头切入面罩玻璃表面的反射：在那层玻璃的倒影里，出现了一片星空——不是这个舱室，而是某个遥远的、她曾经见过或梦见过的地方。红色光芒突然增强，她的手抬起，指尖触碰面罩——从外侧，像是有另一只手在回应。
【镜头三 · 8–12秒】 快切至极近景：她的眼睛里，星空的倒影在瞳孔中燃烧。镜头缓慢旋转，像一颗卫星在她的轨道上运行。面罩玻璃上的水雾开始在红光中蒸发，露出她脸上细微的表情变化——不是恐惧，是某种比恐惧更深的东西：认命，或者，领悟。
【镜头四 · 12–15秒】 镜头骤然拉远，穿越面罩玻璃向外——她的整个头盔变成画面中一个渺小的球体，背景中红色警报光渐渐熄灭，取而代之的是一片深邃的、无边的蓝黑色静默。她的手慢慢放下。画面在这片静默中切黑——只留下一声极其微弱的、像心跳又像信号的电子脉冲声。
色调：深红预警 × 冷蓝深空 × 琥珀肤光。镜头如呼吸般起伏，克制而充满张力。
```

---

### Case 4: 跑车乡间公路动态镜头

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase4image.png)

**输出效果：**

_i2v_case4_video_url_placeholder_
镜头1：高空垂直俯视镜头，银色跑车在S形乡间道路匀速前进，车身线条反射环境光形成流动光带，轮胎与路面接触处扬起薄雾状尘埃，道路两侧树木形成绿色隧道效果
镜头2：镜头和跑车保持同步移动，车头占据画面中心位置，前灯光线在运动中形成光轨，进气格栅细节清晰可见，轮胎转动时轮毂保持稳定旋转，两侧景物形成运动模糊
```

---

### Case 5: 宇航员月球漫步

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase5image.png)

**输出效果：**

_i2v_case5_video_url_placeholder_
The camera slowly pushes into the astronaut's reflective gold visor, where a miniature world is revealed — the lunar surface and the distant lunar module reflected in breathtaking clarity, like a universe trapped within glass. The camera then eases back as the astronaut takes a single slow, weighted step forward, lunar dust rising in ultra-slow motion under low gravity, each particle catching sunlight like scattered golden sparks. The camera dives low to capture the deep bootprint pressed into the regolith — a mark of history carved into silence. Finally, the shot pulls back and upward to reveal the astronaut's full silhouette against the infinite black cosmos, with a faint blue glow of Earth hovering in the far distance. The entire sequence carries a cinematic film-grain aesthetic, cold and sacred in tone, with subtle handheld camera tremors evoking the rawness of authentic documentary footage.
```

---

### Case 6: 抽象卡通动画律动

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase6image.png)

**输出效果：**

_i2v_case6_video_url_placeholder_
The black and white wavy lines and checkered patterns in the background slowly ripple and distort rhythmically, the blue cartoon character sways slightly along with the motion, slowly inserting the card into the yellow and black striped box, electric sparks flicker at the slot of the box, the single eye rotates and looks around, the whole scene pulses with a psychedelic rhythmic energy, camera gently sways left and right.
```

---

### Case 7: 泰迪熊火车站赶路

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase7image.jpeg)

**输出效果：**

_i2v_case7_video_url_placeholder_
The cute teddy bear as it briskly walks forward across the train station platform, pulling its brown suitcase behind it with a sense of urgency. The bear's mouth moves in perfect lip-sync as it hurriedly says: 'There's no time left, I'm going to be late!' Its expression should appear anxious and determined. In the background, other passengers and the trains should have subtle, natural movements to reflect a busy station atmosphere. The camera follows the bear with a smooth forward tracking shot, maintaining its soft, fuzzy texture and the realistic cinematic lighting from the original image.
```

---

### Case 8: 卡通转真人变身视频

**模型:** `happyhorse-1.0-i2v`

**Prompt:**
```

**输入图片：**

![输入图片](images/i2v/i2vcase8image.png)

**输出效果：**

_i2v_case8_video_url_placeholder_
A girl is dancing gracefully. As she spins around in a full turn, the entire scene seamlessly transforms from a cartoon style into a realistic live-action setting.
```
