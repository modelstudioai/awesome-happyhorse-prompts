# R2V 参考生视频（支持多图片输入）案例

> HappyHorse 1.0 R2V 支持通过多张图片引导视频生成，包括主体多视角参考、场景图参考、分镜图参考等多种用法。上传图片时，如对图片顺序有要求，请按顺序上传。在提示词中可通过@「Image 1」「Image 2」⋯「Image n」进行准确指代。

**适用场景：**
- 需要保持角色在不同镜头中外观一致，提供同一角色的多角度照片作为参考
- 有明确的场景设定或美术风格板，希望视频还原特定的视觉风格
- 按照分镜脚本制作视频，将各分镜图依次上传引导生成
- 需要将多个元素（如角色＋场景+Logo）组合到同一段视频中

**提示词参考示例：**
- 参考「Image 1」中的角色形象，她走进「Image 2」中的场景，推开门后回头微笑，镜头跟随，电影质感
- 提取「Image 1」和「Image 2」中的猫咪特征，生成它在窗台上打盹后被惊醒的画面，保持毛色和花纹一致
- 结合「Image 1」的正面照和「Image 2」的侧面照，生成该角色转身回眸的动态画面，保持五官和发型一致
- 以「Image 1」为画面风格参考，「Image 2」中的人物在樱花树下漫步，最后出现「图片3」中的Logo，整体色调统一

---

### Case 1: 宠物主播脱口秀 — 猫狗吐槽搭子

**模型:** `happyhorse-1.0-r2v`

**Prompt:**
```
一张超逼真的4K摄影级画面，场景设定为潮流感满满的播客录音间。背景为蓝灰色几何拼接声学泡沫墙，两侧专业补光灯从侧前方柔和打亮主体，阴影过渡自然无塑料感。构图采用对称式双人中景，视觉重心稳定于深色实木直播桌后方。桌面摆放两只印有宠物爪印图案的陶瓷咖啡杯，整体氛围拟人化、网感十足，毛发纹理根根分明，材质反射符合物理光学规律。画面左侧是一只戴着潮酷黑框墨镜、挂着金色项链的橘白英短猫，端坐在复古做旧皮质主播椅上，面前摆着黑色专业麦克风，前爪自然交叠搭在桌沿，表情拽酷又带点傲娇。画面右侧是一只戴着街头风棒球帽、耳朵上别着银色耳钉的棕色柴犬，同样坐于同款主播椅，正对着麦克风咧嘴笑，露出治愈系犬齿。双宠手肘均轻搭桌面，形成稳定的双人主播站位，镜头焦点锐利锁定面部与麦克风区域。
基于此高精度底图进行动态口型驱动与表演设计：身份定位为宠物界"吐槽搭子"，对话主题围绕《铲屎官那些"自我感动"的迷惑行为》展开。角色人设与情绪分配明确：猫（橘白英短）担任毒舌吐槽役，语速稍快，情绪带着不屑与嘲讽；狗（柴犬）担任呆萌提问役，语速适中，情绪充满疑惑与好奇。对话片段示例如下——狗："主人天天给我买新玩具，转头又说我拆家费钱，这啥逻辑啊？"猫："傻狗，这叫'既要展示爱心，又要卖惨博同情'，人类的套路罢了～"合："哈哈哈哈哈哈！"。动作与交互细节需严格同步：狗说话时会配合轻微歪头与快速眨眼，猫吐槽时会伴随尾巴轻甩、偶尔翻个白眼；两宠对话期间保持高频眼神交汇与头部微转，肢体节奏高度同步。口型驱动时需确保唇部开合幅度与台词重音精准匹配，结尾大笑段面部肌肉运动自然流畅不穿模，整体呈现高同步率的拟真搭档感。
```
**参考图片：**

![参考图 1](../videos/r2v/images/r2vcase1image1.png)
![参考图 2](../videos/r2v/images/r2vcase1image2.png)
![参考图 3](../videos/r2v/images/r2vcase1image3.png)

**输出效果：**

https://github.com/user-attachments/assets/a20adca0-bf45-4cae-b933-c98b86eac8d0

---

### Case 2: Pixar 风格 — 女孩灵感时刻

**模型:** `happyhorse-1.0-r2v`

**Prompt:**
```
Generate a Pixar-style video. The camera orbits around a girl sitting at her desk. She is seated in front of her computer, deep in thought [Image 1]. Mid-orbit, the camera cuts to a close-up of her face [Image 2], her expression conveying utter puzzlement. Suddenly, her eyes light up and her face instantly relaxes into a delighted smile [Image 3], showing that she has just struck upon a brilliant idea. The camera then continues its orbiting movement as, having found her answer, the girl cheerfully kicks her feet up onto the desk and leans back with her hands clasped behind her head [Image 4], radiating a state of pure joy and relaxation.
```
**参考图片：**

![参考图 1](../videos/r2v/images/r2vcase2image1.png)
![参考图 2](../videos/r2v/images/r2vcase2image2.png)
![参考图 3](../videos/r2v/images/r2vcase2image3.png)
![参考图 4](../videos/r2v/images/r2vcase2image4.png)

**输出效果：**

https://github.com/user-attachments/assets/0406df65-6330-43f4-9e1d-7bb82acffda2

---

### Case 3: 古风双人互动 — 王爷与丫头

**模型:** `happyhorse-1.0-r2v`

**Prompt:**
```
参考「image 1」中的王爷形象与「image 2」中的丫头形象，两人在古风书房场景中互动。「image 1」端坐案前执卷看书，神情清冷专注。「image 2」身着浅绿纱衣从旁侧悄悄凑近，歪头凝视「image 1」侧脸，眼神试探又带俏皮。一个清脆俏皮的女声问："王爷不近女色？"一个低沉冷淡的男声回："嗯"。暖光透过窗棂洒落，固定机位，真人古风写真风格，电影级光影质感，面部细节清晰。
```
**参考图片：**

![参考图 1](../videos/r2v/images/r2vcase3image1.png)
![参考图 2](../videos/r2v/images/r2vcase3image2.png)

**输出效果：**

https://github.com/user-attachments/assets/a476afe6-43fa-4ead-ab8a-37a90fd50ab4

---

### Case 4: 古风少年少女对话 — 四格分镜

**模型:** `happyhorse-1.0-r2v`

**Prompt:**
```
电影质感，智能分镜，动作流畅自然，画面无崩坏。分镜1（近景3秒）侧面跟拍「image 3」。两人起身行走，少女「image 2」突然停下脚步翻了个白眼，无情拆台说："就我们？别人早都跑没了影。"分镜2（中景4秒）平视。少年「image 1」凑近半步，压低声音提议说到："要不咱直接撂挑子跑路归隐？"分镜3（近景3秒）平视。少女抬手戳了戳他的胳膊，一脸无语回怼说："跑？哪能这么便宜了他们？"分镜4（中景5秒）正面平视。少年瞬间蔫了，少女绷着脸补刀回应说："收收你的垮脸，组织监控正对着咱呢"
```
**参考图片：**

![参考图 1](../videos/r2v/images/r2vcase4image1.png)
![参考图 2](../videos/r2v/images/r2vcase4image2.png)
![参考图 3](../videos/r2v/images/r2vcase4image3.png)

**输出效果：**

https://github.com/user-attachments/assets/a2869803-6a41-48a4-8995-6795a19ebd9a

---

### Case 5: 韩漫风格便利店治愈夜

**模型:** `happyhorse-1.0-r2v`

**Prompt:**
```
生成一段韩漫风格、电影感的短视频。夜晚，雨夜便利店，灯光柔和，情绪安静、治愈、微孤独、温柔。开场镜头展示深夜街角的便利店外景，暖白灯光从玻璃窗透出，外面下着细雨，地面有潮湿反光，街灯和夜色安静而柔和「image 1」。然后镜头切入店内，年轻女生推门进入便利店，她穿着长外套，头发和肩头带着些许雨水，神情疲惫但温柔。她慢慢走到热饮柜前停下，在暖橙色灯光映照下轻轻发呆，呼吸放缓，侧脸显得安静而落寞「image 2」。接着镜头转向收银台，夜班店员少年注意到她，视线在她湿润的发梢和疲惫的神情上短暂停留，眼神里浮现一丝关心。他抬起头，对她露出温和而克制的微笑，轻声说："오늘도 수고 많았어요." 女生听见后微微一怔，缓慢转头看向他，眼神从空茫变得柔软。两人短暂对视，空气安静却温暖。她轻轻弯起嘴角，露出一个很浅、很克制的笑，随后拿起一罐热饮，手指握住饮料罐时像是终于放松下来。店员保持温柔的神情看着她，她则带着一点腼腆与被安慰到的情绪，轻轻点头回应「image 3」。最后镜头缓慢收束到便利店门口，女生双手捧着热饮站在门边，看向外面的雨夜街道，便利店暖光勾勒她的背影，雨丝和街灯在背景中柔和闪烁。她的神情平静下来，眼底带着若有若无的笑意，画面停留在安静、温柔、细腻治愈的情绪中结束「image 4」。
```
**参考图片：**

![参考图 1](../videos/r2v/images/r2vcase5image1.png)
![参考图 2](../videos/r2v/images/r2vcase5image2.png)
![参考图 3](../videos/r2v/images/r2vcase5image3.png)
![参考图 4](../videos/r2v/images/r2vcase5image4.png)

**输出效果：**

https://github.com/user-attachments/assets/3669f31b-8c82-482b-9781-1852a260ffd2

