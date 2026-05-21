# T2V 文生视频案例

> 文生视频模型，只需要用户输入一段提示词即可生成。prompt 即正向提示词，用来描述视频中所包含的画面内容和运动过程，描述越准确、越丰富，生成视频的质量越高。

**提示词公式：** 提示词 = 场景 + 主体 + 运动 + 音频

---

### Case 1: 古风玄幻 — 白发少女与龙

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
动漫风格，国风2d风格，类似玄机科技的画风白发少女，扎发，冷白皮肤，兼具冷艳系长相，画面有颗粒感。 丹凤眼，闭眼姿态，表情慵懒平静，举止端庄，极致细节，极致厚涂，琉璃质感，流线笔刷。白色披着的头发，身着藏蓝色绒翎长袍，衣服的元素带有少数民族元素，整体有柔光、质感，氛围梦幻朦胧，低饱和度，富有反差故事感。头上簪着一支蓝色翡翠或者水晶垂吊簪，既显温婉又不失贵气，契合角色气质形象。 正脸示人，轻笑一声，语气轻柔又不屑说完＂哦？要抓我？＂ 之后，缓缓抬眼，眼中闪炸开一丝微乎其微的光，瞬间镜头从她脸前拉远，身后瞬间乌云密布电闪雷鸣，一条水龙从天而降咆哮龙吟一声，极速飞至她头顶，霸气盘立上空，眼中红光乍现，震耳的嗡鸣声滚滚响起。
```

**输出效果：**

https://github.com/user-attachments/assets/14e66750-7f22-4990-9d40-5f833caac0f9

---

### Case 2: 新海诚风格星空少女

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
全景，新海诚风格，时间为盛夏的夜晚，地点是远离尘嚣的宁静小镇边缘山坡。晴朗无云，繁星密布如同璀璨宝石镶嵌于天幕，银河横跨天际，散发着幽蓝深邃的光晕。月光如银纱般轻柔地洒在翠绿的山坡草坪上，使其染上一层淡淡的冷白色。一位身着淡蓝色连衣裙的少女静立于此，微风吹拂着及肩的棕色长发，发丝在月光下泛着柔和的暖棕色光泽。她双手交叠放在身前，抬头仰望着星空，眼中满是对浩瀚宇宙的憧憬和淡淡的孤独。周围萤火虫提着绿幽幽的光在草丛中飞舞，像是在安慰少女的寂寞。山坡上五颜六色的野花在星月光辉与萤火虫光亮交织的光影中轻轻摇曳，画面主色调为蓝紫冷色调，点缀着暖黄的萤火虫光与少女裙装的淡蓝。镜头从夜空缓缓向下移动至少女，带着一种静谧又略带忧伤的氛围。
```

**输出效果：**

https://github.com/user-attachments/assets/20b4d5f7-e0ef-452e-99d5-b16693016f26

---

### Case 3: Minecraft 风格武术对决

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
主题与动作：一场电影般的武术对决，一方是身穿绿色束腰外衣、背着棕色大皮背包的健壮拟人化野猪，另一方是身着白色武术服、系着蓝色腰带的沉着拟人化公鸡。场景以恭敬的鞠躬开始，随后迅速转入一场快节奏的打斗，包括高踢腿、拳击和空中跳跃。
环境与风格：场景是一个充满活力、阳光明媚的Minecraft 风格方块景观，拥有连绵起伏的绿色山丘、风格化的方块树木和湛蓝的天空，点缀着蓬松的白云。动画风格是高质量的3D，具有流畅的动作和动态的摄像机角度（低角度镜头、特写和广角平移）。
氛围与技术细节：
- 灯光：明亮、自然的日光，带有微妙的镜头光晕。
- 视觉特效：打斗时，尘土小云从土路上扬起；当他们的攻击命中时，会出现明亮的"火花"或冲击闪光。
- 摄像机：冲击时快速剪切和"抖动镜头"，以强调打击的力量。

要复制的关键元素：
角色对比：笨重有力的野猪与敏捷自律的公鸡。
"Yapper"美学：此视频采用了一种特定的 AI 动画风格，将"可爱"的角色设计与激烈、高风险的动作编排融为一体。
背景：使用"体素艺术"、"方块地形"或"低多边形山丘"等关键词来获得那种特定的游戏世界外观。
```

**输出效果：**

https://github.com/user-attachments/assets/27931159-7c22-4a92-8bfa-8fc85b81ec7a

---

### Case 4: 私人飞机商务对话

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
【场景】奢华的私人飞机机舱内，窗外是壮丽的金红色的云海落日，阳光将机舱渲染成琥珀色。
【主体】左侧满头银发的 [ 年长男性 ] 身穿高定西装，手持威士忌酒杯，目光如鹰般锐利；右侧的 [ 年轻男性 ] 身体微微前倾，眉头微皱，神情既紧张又充满野心。
【运动】年长男性轻轻晃动着手中的酒杯，液体挂壁，他身体逼近对方；年轻男性深吸一口气，眼神坚定地回视。镜头缓慢侧推，聚焦两人之间紧绷的张力。
【音频】[ 年长男性, 低沉沙哑, 充满威严 ] 说道："In this world, you either hunt or you become the prey. Which one are you?"  [ 年轻男性, 嗓音紧绷但坚定 ] 回答："I am the one who pulls the trigger." 背景伴随着飞机引擎深沉的轰鸣声和冰块撞击玻璃杯的清脆声。
```

**输出效果：**

https://github.com/user-attachments/assets/749f1717-648b-4642-a433-5f27f03fd0d0

---

### Case 5: 东方古装女子黑化

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
东方古装写实风格，中近景正面视角。一位身着华丽红色绣花礼服的东方古代女子端坐于富丽典雅的宫廷室内，头戴精致繁复的凤冠，珠宝与垂链在灯火下散发高贵威仪；背景朦胧的宫殿装饰营造出庄重的皇家氛围，整体色调以富丽的红金暖色为主。随着镜头环绕，女子神情由端庄肃穆逐渐转为冷厉：眼神微眯透出狠戾寒光，眉尾下压，嘴角单侧上扬呈冷笑状。就在背景纱幔被无形气流掀起、头饰红珠随动作轻晃的瞬间，她阴鸷冷笑："既然你不识抬举，就休怪本宫心狠。"整个画面在注重服饰绣纹与金属质感刻画的同时，展现出极强的皇家仪式感与暗流涌动的戏剧张力。
```

**输出效果：**

https://github.com/user-attachments/assets/ea18a21b-2404-422e-a8bd-7be786039137

---

### Case 6: 巴黎咖啡馆对话

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
A cinematic script scene set in a sun-drenched Parisian café, golden afternoon light spilling through arched windows. A sharp-dressed man in a tailored navy suit sits across from an elegant woman in a flowing crimson dress, half-empty coffee cups between them. The air is thick with unspoken tension. He leans forward, voice low and steady: "You knew from the beginning, didn't you? That none of this was real." She holds his gaze without flinching, a ghost of a smile on her lips, slowly stirring her coffee: "Everything was real. That's exactly what makes it so dangerous." Cinematic wide-angle composition, warm golden hour lighting, shallow depth of field, film grain texture, muted vintage color palette with deep crimson accents, highly detailed wardrobe and facial expressions, noir romantic aesthetic, emotionally charged atmosphere, European street photography style, dramatic storytelling, 35mm film look.
```

**输出效果：**

https://github.com/user-attachments/assets/1938cc2d-4b16-4ae1-9d06-14e499690890

---

### Case 7: 韩国男女咖啡馆恋爱

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
生成一段10s韩国男女在咖啡馆谈恋爱对话的片段，恋爱细节丰富，带有分镜
```

**输出效果：**

https://github.com/user-attachments/assets/f30417a5-cf84-41ce-8f89-aea535213ad2

---

### Case 8: Pizza 店员工递餐

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
一镜到底，电影质感画面。昏暗的镜头从玻璃外远景缓慢推向近景，一个pizza店里，一个大胡子的白人店员正在烤制披萨。他用铁盘将披萨从烤炉里取出，放在红色的包装盒子里，盖好盒子。最后笑容满面并热情地递给顾客，过肩镜头。音频：烤炉持续的低频嗡鸣声，铁盘轻微碰撞的金属声。店员用爽朗热情的美国口音说："Here you go！"，声音洪亮带笑。
```

**输出效果：**

https://github.com/user-attachments/assets/03625e9c-1234-4739-aba4-e1b59bde48f8

---

### Case 9: 微型料理延时摄影

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
纯黑背景，一束戏剧性的顶光照亮操作台。一双干净的手将一个微型砧板和一把迷你厨刀摆好。音频：庄严优雅的古典音乐响起。
镜头1：用镊子夹起一瓣小小的蒜粒放在微型砧板上，迷你厨刀精准地将其切成薄片，刀刃接触砧板发出清脆微小的"哒、哒、哒"声。
镜头2：一个微型平底锅放在点燃的茶蜡上，用微型滴管滴入一滴橄榄油，油在锅中发出细微的"滋滋"声。
镜头3：将一小块鹌鹑蛋打入锅中，蛋清迅速凝固，用微型锅铲小心翻动。
摆盘：一份由迷你太阳蛋和蒜香蘑菇组成的精致餐点被盛放在一枚硬币上，镊子小心摆上最后一根葱作为装饰。古典音乐在摆盘完成时达到高潮然后缓缓收尾。
```

**输出效果：**

https://github.com/user-attachments/assets/391a0ef1-bf63-487b-be1e-aa6548b47092

---

### Case 10: 海滩空镜头延时摄影

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
人群与遮阳伞渐渐散去。海滩回归宁静，一尘不染。碧波轻漾，海鸥啼鸣，和风送暖。沙滩上的一切都消失了。只剩下金沙、碧海与蓝天。海浪温柔地拍打着岸边，微风徐徐，远处鸟鸣阵阵。
```

**输出效果：**

https://github.com/user-attachments/assets/16fe405f-c007-41d6-9e50-efed676bb8d2

---

### Case 11: 柠檬树生命周期延时摄影

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
生成一个连续的延时摄影风格视频，展示一颗柠檬树从种子发芽到果实成熟的完整生命周期。要求写实主义自然光照，画面细腻。
```

**输出效果：**

https://github.com/user-attachments/assets/3566296c-455f-41e6-8292-4f2c91a501e0

---

### Case 12: 极限滑雪者与雪崩

**模型:** `happyhorse-1.0-t2v`

**Prompt:**
```
高山雪原，阳光明媚的极寒色调，陡峭岩壁，漫天雪雾。身穿橙色冲锋衣的 [ 极限滑雪者 ] 正在极速俯冲，激起飞扬的雪粉，身后是如海啸般倾泻而下的巨大雪崩气浪。雪崩爆发的沉闷轰鸣巨响，背景有滑雪板剧烈切割积雪的摩擦声与急促的风啸声，镜头跟拍高速运动特写，营造生死时速的紧张压迫感。
```

**输出效果：**

https://github.com/user-attachments/assets/84e69e9a-747b-4655-8ec2-ec642105f574
