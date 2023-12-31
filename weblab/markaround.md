---
title: MarkDown 实验室
---

# MarkAround 实验室: {#head}
*基于样式表的 Markdown (Kramdown) 语法扩展*{:.bigger.stroke.echorb.sparkle}

## 需要在自己网站上使用？
在网页 sass/scss 格式的样式表中添加以下代码即可：

    @import "https://raw.githubusercontent.com/Kirisoup/kirisoup.github.io/main/_sass/markaround.scss";



或者也可以通过将 [markaround.scss](https://raw.githubusercontent.com/Kirisoup/kirisoup.github.io/main/_sass/markaround.scss) 克隆至你的Jekyl仓库下的`_sass` 文件夹后，在 sass/scss 格式的样式表中添加`@import "markaround";`

### 如果你的网站不支持构建 sass/scss：
编译完成的css样式表可在 [此处](https://kirisoup.github.io/assets/css/markaround.css) 获取。

在页面html文件的`<head>`标签下添加以下代码，或者自行克隆到网页的仓库下使用。

    <link rel="stylesheet" href="https://raw.githubusercontent.com/Kirisoup/kirisoup.github.io/main/assets/css/markaround.css">

> 注：推荐使用 Kramdown 或类似拥有类似功能的 MD 处理器简化为文章元素添加属性的过程。
{:.info}


## 目录 {#index}
- 目录
{:toc}

---

## 常规分类: {#regular}

### 大小: {#size}
- 普通大小（作为对比）
- *.bigger*{:.bigger} [^how2attr]
- *.big*{:.big} 
- *.small*{:.small} 
- *.smaller*{:.smaller}
- *.size*{:.size style="--s:1.096"} [^how2var]
  - \-\-s: 1.096 *(自定义大小倍率)*

[^how2attr]: 
    > 提示：使用 kramdown 的 \{: } 语法为元素添加额外属性，以在文章内使用本文档罗列的特性：
    {:.info}
    
    - \{: } 冒号后支持添加的属性包括：类名称、ID值、HTML属性
      - 类名称： `{:.classname}`
      - ID:  `{:#id}`  
      *(本文档中罗列的特性都不会用到ID值)*
      - HTML 属性：
        - `{:attr="value"}`
        - 空属性： `{:attr=""}`
        - 使用例： `{:style="background:url(/assets/image.gif)"}`  
          为元素添加一个自定义的图片背景
      - 使用多种不同的属性：  
      `{:.bigger.rainbow#unique style:"transform:scaleX(200%)"}`
    
    ---
    {:.break}
    
    - 为行内元素添加属性：
      - 段落内容 *\*文字\*\{:.cfuchsia}*{:.cfuchsia} 段落内容。  
        [^how2attr-em]

    ---
    {:.break}
    
    - 为段落元素添加属性：<br>  
      *\{:.bfuchsia.cfuchsia}<br>段落内容段落内容段落内容。*{:.bfuchsia.cfuchsia style="padding:.5em"}
    
      > \{: } 也可置于段落下方
      {:.info}

    > 详见：https://kramdown.gettalong.org/syntax.html#attribute-list-definitions
    {:.info}

[^how2var]: 
    > 提示：在 kramdown 的 {:***} 语法中声明元素的 style 属性，来使用部分类所支持的额外属性！
    >
    > 例：上文的 .size 类使用了 `{:.size style="--s:1.096"}` 语句将文本字号设成 1.096 倍
    {:.info}

[^how2attr-em]: 
    > 注：为了分离inline元素的方便，默认情况下任何带有 Moardown 
    > - 扩充类（如 `*内容*{:.class}`），以及
    > - 特殊属性（如 `*内容*{:t="tip"}`）
    > 
    > 的斜体文字都不会拥有斜体效果。
    > 
    > 这种情况下，请使用 .i 类专门声明此文字为斜体。
    {:.info}

### 伪标题: {#fake-title}
- <h>.fake.h1</h>{:.fake.h1} 
- <h>.fake.h2</h>{:.fake.h2} 
- <h>.fake.h3</h>{:.fake.h3} 
- <h>.fake.h4</h>{:.fake.h4} 
- <h>.fake.h5</h>{:.fake.h5} 
- <h>.fake.h6</h>{:.fake.h6}

### 对齐: {#align} 
> *靠左：.l*{:.l} 
> *居中：.c*{:.c} 
> *靠右：.r*{:.r}

### 修饰线: {#line}
- | | 下划线 | 上划线 | 删除线 | 混合
  |---|---|---|---|---|---
  | 正常线 | *.u*{:.u}         | *.ovl*{:.ovl}         | *.dll*{:.dll}         | *.u.ovl.dll*{:.u.ovl.dll}
  | 段虚线 | *.u.-d*{:.u.-d}   | *.ovl.-d*{:.ovl.-d}   | *.dll.-d*{:.dll.-d}   | *.u.ovl.dll.-d*{:.u.ovl.dll.-d}
  | 点虚线 | *.u.-do*{:.u.-dd} | *.ovl.-do*{:.ovl.-dd} | *.dll.-do*{:.dll.-dd} | *.u.ovl.dll.-do*{:.u.ovl.dll.-dd}
  | 双层线 | *.u.-db*{:.u.-db} | *.ovl.-db*{:.ovl.-db} | *.dll.-db*{:.dll.-db} | *.u.ovl.dll.-db*{:.u.ovl.dll.-db}
  | 波浪线 | *.u.-w*{:.u.-w}   | *.ovl.-w*{:.ovl.-w}   | *.dll.-w*{:.dll.-w}   | *.u.ovl.dll.-w*{:.u.ovl.dll.-w}
  {:.t style="line-height:2em"}

- markdown原版语法的删除线: 
  - *~~txt~~*        : \~\~txt\~\~
  - *~~txt~~{:.-d}*  : \~\~txt\~\~{:.-d}
  - *~~txt~~{:.-dd}* : \~\~txt\~\~{:.-dd}
  - *~~txt~~{:.-db}* : \~\~txt\~\~{:.-db}
  - *~~txt~~{:.-w}*  : \~\~txt\~\~{:.-w}

### 颜色: {#color}

| - *.white*{:.white.hbc}   | *.wh*{:.wh.hbc}
| - *.silver*{:.silver}     | *.si*{:.si}
| - *.gray*{:.gray}         | *.gr*{:.gr}
| - *.black*{:.black.hw}    | *.bc*{:.bc.hwh}
| - *.red*{:.red}           | *.re*{:.re}
| - *.maroon*{:.maroon}     | *.ma*{:.ma}
| - *.yellow*{:.yellow.hbc} | *.ye*{:.ye.hbc}
| - *.olive*{:.olive}       | *.ol*{:.ol}
| - *.lime*{:.lime}         | *.li*{:.li}
| - *.green*{:.green}       | *.gr*{:.gr}
| - *.aqua*{:.aqua}         | *.aq*{:.aq}
| - *.teal*{:.teal}         | *.te*{:.te}
| - *.blue*{:.blue}         | *.bl*{:.bl}
| - *.navy*{:.navy}         | *.na*{:.na}
| - *.fuchsia*{:.fuchsia}   | *.fu*{:.fu}
| - *.purple*{:.purple}     | *.pu*{:.pu}

### 背景色: {#background}
- \-\-hd: 0.05em *(背景、边框距离)*
- *.h*{:.h}

| - *.hwhite*{:.hwhite}     | *.hwh*{:.hwh}
| - *.hsilver*{:.hsilver}   | *.hsi*{:.hsi}
| - *.hgray*{:.hgray}       | *.hgr*{:.hgr}
| - *.hblack*{:.hblack}     | *.hbc*{:.hbc}
| - *.hred*{:.hred}         | *.hre*{:.hre}
| - *.hmaroon*{:.hmaroon}   | *.hma*{:.hma}
| - *.hyellow*{:.hyellow}   | *.hye*{:.hye}
| - *.holive*{:.holive}     | *.hol*{:.hol}
| - *.hlime*{:.hlime}       | *.hli*{:.hli}
| - *.hgreen*{:.hgreen}     | *.hgr*{:.hgr}
| - *.haqua*{:.haqua}       | *.haq*{:.haq}
| - *.hteal*{:.hteal}       | *.hte*{:.hte}
| - *.hblue*{:.hblue}       | *.hbl*{:.hbl}
| - *.hnavy*{:.hnavy}       | *.hna*{:.hna}
| - *.hfuchsia*{:.hfuchsia} | *.hfu*{:.hfu}
| - *.hpurple*{:.hpurple}   | *.hpu*{:.hpu}

### 边框色: {#border}
- \-\-bw: 2px *(边框粗细)*
- \-\-bd: 0.05em *(背景、边框距离)*

| - *.bwhite*{:.bwhite}     | *.bwh*{:.bwh}
| - *.bsilver*{:.bsilver}   | *.bsi*{:.bsi}
| - *.bgray*{:.bgray}       | *.bgr*{:.bgr}
| - *.bblack*{:.bblack}     | *.bbc*{:.bbc}
| - *.bred*{:.bred}         | *.bre*{:.bre}
| - *.bmaroon*{:.bmaroon}   | *.bma*{:.bma}
| - *.byellow*{:.byellow}   | *.bye*{:.bye}
| - *.bolive*{:.bolive}     | *.bol*{:.bol}
| - *.blime*{:.blime}       | *.bli*{:.bli}
| - *.bgreen*{:.bgreen}     | *.bgr*{:.bgr}
| - *.baqua*{:.baqua}       | *.baq*{:.baq}
| - *.bteal*{:.bteal}       | *.bte*{:.bte}
| - *.bblue*{:.bblue}       | *.bbl*{:.bbl}
| - *.bnavy*{:.bnavy}       | *.bna*{:.bna}
| - *.bfuchsia*{:.bfuchsia} | *.bfu*{:.bfu}
| - *.bpurple*{:.bpurple}   | *.bpu*{:.bpu}

### 注音: {#ruby}
- *这是文字*{:r="这是注音"}

      *这是文字*{:r="这是注音"}

- *这*{:r="zhè"}*是*{:r="shì"}*文*{:r="zhù"}*字*{:r="yīn"}

      *这*{:r="zhè"}
      *是*{:r="shì"}
      *文*{:r="zhù"}
      *字*{:r="yīn"}

### 隐藏: {#del}
> 将鼠标悬浮到文本上
{:.info}

- *.del*{:.del}
- *.blur*{:.blur}
  - *.blurrier*{:.blurrier}
  - \-\-br: 0.1em *(模糊半径)*
- *这是一段普通的文字*{:reveal="{:reveal=\"替换内容\"}"}

### 悬浮提示: {#tip}
> html 也有自带悬浮提示，即 title="" 属性：*{:title="这是提示"}*{:.u title="这是提示"}
{:.info}

- *{:t="这是提示"}*{:t="这是提示"}

- *{:t="这是提示" .above}*{:t="这是提示" .above}

- *{:t="这是提示" style="--tc:#d44"}*{:t="这是提示" style="--tc:#d44"}
  - \-\-tc: #44d *(提示颜色)*

### 全宽链接: {#full-width-link}
> 用来制作舒适的链接列表效果
- [\[标题0\](地址0)\{:.ab}](#full-width-link){:.ab}
- [\[标题1\](地址1)\{:.ab}](#full-width-link){:.ab}
- [\[标题2\](地址2)\{:.ab}](#full-width-link){:.ab}
- [\[标题3\](地址3)\{:.ab}](#full-width-link){:.ab}
- [\[标题4\](地址4)\{:.ab}](#full-width-link){:.ab}

### 表格: {#table}
- 平表格
  - |1|a|b|c|
    |2|d|e|f|
    |3|g|h|i|
    |4|j|k|l|

        |1|a|b|c|
        |2|d|e|f|
        |3|g|h|i|
        |4|j|k|l|

- 普通表格
  - |1|a|b|c|
    |2|d|e|f|
    |3|g|h|i|
    |4|j|k|l|
    {:.t}

        |1|a|b|c|
        |2|d|e|f|
        |3|g|h|i|
        |4|j|k|l|
        {:.t}`|

  - | |一|二|三|
    |---
    | 1|a|b|c|
    | 2|d|e|f|
    |---
    |1|a|b|c|
    |2|d|e|f|
    |3|g|h|i|
    |4|j|k|l|
    |===
    |0|z|z|z|
    {:.t h="这是表格"}

        | |一|二|三|
        |----------|
        |1|a |b |c |
        |2|d |e |f |
        |----------|
        |1|a |b |c |
        |2|d |e |f |
        |3|g |h |i |
        |4|j |k |l |
        |==========|
        |0|z |z |z |
        {:.t h="这是表格"}`|


- 简单表格
  - |1|a|b|c|
    |2|d|e|f|
    |3|g|h|i|
    |4|j|k|l|
    {:.ts}

        |1|a|b|c|
        |2|d|e|f|
        |3|g|h|i|
        |4|j|k|l|
        {:.ts}

  - | |一|二|三|
    |---
    |1|a|b|c|
    |2|d|e|f|
    |---
    |1|a|b|c|
    |2|d|e|f|
    |3|g|h|i|
    |4|j|k|l|
    |===
    |0|z|z|z|
    {:.ts h="这是表格"}

        | |一|二|三|
        |----------|
        |1|a |b |c |
        |2|d |e |f |
        |----------|
        |1|a |b |c |
        |2|d |e |f |
        |3|g |h |i |
        |4|j |k |l |
        |==========|
        |0|z |z |z |
        {:.ts h="这是表格"}

- --tbc: 调整空表格**以外**的表格颜色
- --tbtc: 调整表格文字颜色
  - | |一|二|三|
    |---
    |1|a|b|c|
    |2|d|e|f|
    |---
    |1|a|b|c|
    |2|d|e|f|
    |3|g|h|i|
    |4|j|k|l|
    |===
    |0|z|z|z|
    {:.t h="这是品红色表格" style="--tbc: #d4d; --tbtc: #d4d"}

        | |一|二|三|
        |----------|
        |1|a |b |c |
        |2|d |e |f |
        |----------|
        |1|a |b |c |
        |2|d |e |f |
        |3|g |h |i |
        |4|j |k |l |
        |==========|
        |0|z |z |z |
        {:.t.i h="这是品红色表格" style="--tbc: #d4d; --tbtc: #d4d"}

### 文本块: {#block}
- 平文本块：
    > \> 文本
- 提示块：
    > \> 文本
    > 
    > \{:.info}
    {:.info}
- 警告块：
    > \> 文本
    > 
    > \{:.warn}
    {:.warn}
- 嵌套结构块：<br>
    > \> 文本
    > 
    > \>
    > 
    > \> 文本
    > 
    > \>
    > 
    > > \> \> 文本
    > >
    > > \> \> 
    > >
    > > > \> \> \> 文本
    > 
    > \>
    > 
    > > > > > \> \> \> \> \> 
    > 
    > \{:.layer}
    {:.layer}

### 脚注: {#footnote}

- 普通（序号）脚注：\[^title] [^title]

      [^title]: 
          示例：普通脚注。这是一段文字

          另一段文字

          > 提示文字块
          {:.info}

- 文字脚注：\*\[^title2]\*\{:foot="我是脚注"} *[^title2]*{:foot="我是脚注"}

[^title]:
    示例：普通（序号）脚注。这是一段文字

    另一段文字

    > 提示文字块
    {:.info}

[^title2]:
    示例：文字脚注。一段文字

    另一段文字

    > 提示文字块
    {:.info}

## 华丽装饰类！: {#fancy}

### 彩虹: {#rainbow}
{:.warn}
> 不兼容阴影 .shadow 与描边 .stroke

- *.rainbow*{:.rainbow .bigger}
  - \-\-rspd: 1s *(滚动速度)*
  - \-\-rbgsz: 4em *(背景大小)*


- *.rainbow.fancy*{:.rainbow.fancy .bigger}
- *.rainbow.fancy2*{:.rainbow.fancy2 .bigger}
  
  - \-\-rspd: 10s *(滚动速度)*
  - \-\-rsc: #00f *(阴影描边颜色)*

- *.rainbow.cmy*{:.rainbow.cmy .bigger}  
  *.rainbow.fancy.cmy*{:.rainbow.fancy.cmy .bigger}  
  *.rainbow.fancy2.cmy*{:.rainbow.fancy2.cmy .bigger} &nbsp; 彩虹但是青品黄

### 阴影: {#shadow}
- *.shadow*{:.shadow .bigger}
  - \-\-sdd: 4px *(阴影距离)*
  - \-\-sdc: #000 *(阴影颜色)*
- *.echo*{:.echo .bigger} 
- *.echorb*{:.echorb .bigger} 

### 描边: {#stroke}
- *.stroke*{:.stroke .bigger}
  - \-\-std: 2px *(描边距离)*
  - \-\-stc: #440 *(描边颜色)*

### 动画！: {#animate}
- *.pulse*{:.pulse .bigger}
  - \-\-pspd: .25s *(跳动速度)*
  - \-\-pscl: 1.2 *(跳动大小倍率)*7
  - \-\-pphs: 0 *(跳动动画相位偏移)*
    - 与 \-\-rphs 同理：
      - 最好使用 0 至 1 之间的值（偏移 0 至 1 周期）
      - 使用负数值将导致动画延迟出现

- *.rotate*{:.rotate .bigger}
  - *.rotate.rev*{:.rotate.rev .bigger}
  - *\-\-rpsd: 1s*{:.rotate style="--rpsd:1s" .bigger} *(旋转速度(周期) -- 默认 3s)*
  - *\-\-ofst-x: 50%*{:.rotate style="--ofst-x:50%" .bigger} *(水平偏移旋转中心 -- 默认 0%)*
  - *\-\-ofst-y: 300%*{:.rotate style="--ofst-y:300%" .bigger} *(垂直偏移旋转中心 -- 默认 0%)*
  - *\-\-rphs: 0*{:.rotate .bigger}
    *\-\-rphs: .25*{:.rotate style="--rphs:0.25" .bigger} *(旋转相位偏移 -- 默认 0)*
    - 最好使用 0 至 1 之间的值（偏移 0 至 1 周期）
    - 使用负数值将导致动画延迟出现

- 嵌套使用段落类（block-level class）和内容类（inline class），以同时使用旋转文字（.rotate）和跳动文字（.pulse） *（在同一元素中无法同时使用两者——无法直接 `{:.rotate.pulse}`）*：
  - \{:.rotate\}  
    \*文字内容\*{:.pulse}
  - {:.rotate} *{:.rotate}  
    \*文字内容\*{:.pulse}*{:.pulse}

---

## 文字排版测试用
午后之时，那银白色的幻想乡。

白雪静静地飘落于尚未开发的自然之中，显现出充满幻想的壮观景象。只能听见妖怪惨叫般的鸣啼声远远传来。

道路被没有足迹的新雪覆盖着。这附近基本上没有什么人类来访。

沿着这条没有道路的路前进，终究能够依稀望见一座不可思议的商店建筑。而店主人肯定是正坐在源于外面世界的暖炉旁侧一边取暖，一边阅读着难以理解的书。他无论何时都是这样悠闲度日啊。

店里面有很多外面世界的物品。虽然幻想乡是在外面世界被称做明治时代的那时候被隔离开的，但那之后时代的物品却也有很多。基本上都是些用途不明的东西。

商店的招牌上写着香霖堂这三个字。古道具屋“香霖堂”就是这里了。
“霖之助先生？”

好像店里来了久违的客人。我虽还想接着读书，不过顾客就是神明，总不能说店家不在就放着不管吧。
“你在的吧？”

穿着一身红色衣服的神明还没等我装作不在家，就已经站到我背后了。
“怎么，是灵梦啊。我不是一直说，不要随便就到我的起居室里来的吗？”
“比起那种事先听我说呀。我可倒了大霉啦——……”

又来了。我眼前这位红色的少女从不好好听别人说话。少女名叫博丽灵梦。虽说是幻想乡唯一的巫女1，不过她那行为也经常让人怀疑这一点的真实性。说得晚了，我的名字是森近霖之助，经营着这家古道具屋。灵梦边弹去肩头的雪片便一边开始喋喋不休地说起话来。
“今天，我到人类村落买东西去了。问我买些什么？我的茶叶剩得不多了，就寻思着在身心煎熬得要死的程度之前先买点……虽然也死不了就是了……喂，你有在听人家说话吗？”

我本想回答说“既然你不听我说我也就没在听你说”，不过还是回应说“啊啊，在听”。
“然后呢，虽说没有好的茶叶……啊，虽然跟这个没什么关系，不过村落的道祖神被雪掩埋了哟，这次该轮到谁给它打伞了呢。我还迷了路。说起来，那边那个道祖神的神体是什么来着？”

看来，要是我不稍微诱导她一下的话，在她说出正题之前话题就要一直飞到神武天皇那里去了。
“障之神，是保护村落不受灾祸的神啊。你说你倒了大霉了，究竟发生了什么？”
“啊，到买完东西时倒是什么都没发生。”

什么都没发生啊。
“回来的时候啊，我看见有妖怪正悠闲地坐在那里，而且还好像很高兴似的读着书！”

那不也没什么吗？我试着问她，却被无视了。
“我就想着出其不意地把她击退，可她却反击了啊。那家伙真是桀骜不驯还很强劲。没想到她竟然会从我身后发射妖弹。我也是一时大意了……”

我只能觉得是那妖怪遭了横祸。不过说是想出其不意又一时大意了，在她身上应该发生了什么吧。
“霖之助先生，你在听人家说吗？”
“啊啊，我没在听啊。”
“……然后呢，那家伙倒是被我打得落花流水的了。”

看来我怎么回应结果都一样。而灵梦，喊着“你看！”把身子转过去让我看她的后背，还鼓起腮帮子看向我。
“这条裙子，可是前不久新做好的啊……”
“撕开了很大一块啊。明白你的企图了，想厚着脸皮要我来修补啊。”
“现在马上吧。”

好，好。我看灵梦似乎很冷，就在暖炉边上多让出一个人的空间来。
“你说是现在马上，也不可能那么快就补完啊。你就暂且先坐这……”

啪哒啪哒啪哒……
“这衣服我借喽—。稍等一会儿我去换衣服。”

她不见了。似乎又是随随便便地跑到店的里屋去了。真是个很随便的家伙啊。

没办法。我坐回到座位上，伸手去够那本正看着一半的书——结果，伸出的手却只抓到了空气。那本书正在稍高的半空中漂浮着。
“看什么书呐？香霖。”

黑色的身影说道。今早看到茶杯有了缺口时，我就有种不祥的预感。
“我说你啊。我不是一直说——”
“不要随随便便进来。对吧？”

真受不了你们……眼前这位黑色少女名叫雾雨魔理沙，是个措辞稍微有点独特的魔法使，和灵梦关系很要好。虽然经常到店里来，我却弄不清她是有事还是没事。
“今天有什么事啊？魔理沙。”
“这书的内容我根本看不懂耶。哦呀，虽然没什么事情不过我可不会回去啊。”

没什么事情啊。“灰尘你总得擦干净吧”魔理沙边这么说着，边坐到了我要出售的壶的上面去。
“……那是系列刊物的第十二册，是堆在这里的这些书的续刊。你光看那一本怎么能看明白啊？”
“啊—？《非冯诺依曼结构计算机的未来》？看了这题目也想不出它究竟要说的是什么耶。”
“那是外面世界的魔术书。和你可能沾不上什么缘分，我可是很有兴趣的。”
“呜—嗯，外面的魔法……那是什么样的魔法呀？香霖。”
“我还没读完呢……不过似乎是一种叫电脑的东西，能使用计算公式按人的命令办事。这不用说就是指式神啊。啊，不过我是不知道它那个式符是利用什么力量的。”
“嗯——式神吗？……咦？这些行李不是灵梦的东西吗？灵梦她在吗？”

看来魔理沙对式神没兴趣就想要转移话题了，我就跟她说了刚才灵梦来时的经过。魔理沙边随声附和地说着“还真像灵梦的作风啊”，边翻弄着灵梦的行李。她从那堆行李中拿出了三册书，而我则受了一点轻微的冲击，因为那些书和这十二册是同一系列的。为什么灵梦会拿着那些书呢……
“嗯？对这些书感兴趣？灵梦的话肯定会说‘因为妖怪把它们看得很重要的样子所以我就给拿来了’啦。”

这三册书和我手头上的十二册加起来共十五册。恐怕这书全套十五册，没错的。外面世界的式神果然还是和幻想乡里是一样的。在电脑方面，Ｆ就代表着十五，Ｆ似乎是一切都充满着的状态。一切都成为Ｆ时则具有最大值，我曾经读过的书中也写过这样的话。

我就想，十五具有力量这一点不是理所当然的吗？十五在这个国家自古以来就意味着完全。阴历十五晚上的月亮被称做满月也是同理。所谓电脑，就是结合东洋的思想、利用了月之魔力的式神吧？

“到底在想些什么啊？”魔理沙一边问我，一边排列起三册书。

魔理沙无意识的举动更让我注意到了这式神的组成结构。书上印有的编号“13”“14”“15”，把这编号排列起来就成了131415。若把开头的1去掉的话……就变成了表示使直线成为圆的数：3.1415，这也意味着满月。外面世界的式符是利用月之力量的，我的这一说法得到了确认。

我想要进一步调查外界式神的信息，而为此我就有必要完全得到这套书。
“……香霖。你打算和灵梦做交易？我说还是算啦，那家伙可不具备普通的价值观哟。”

确实，灵梦的思维有些太过于远离尘世了，普通的交换条件是行不通的。不过我却可以和灵梦做交易，我也大体上清楚灵梦的价值观。

这时，传来了持有者回来的脚步声。


