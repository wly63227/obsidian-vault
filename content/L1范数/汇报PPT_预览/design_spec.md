---
title: "L1 Norm Baseline Correction Report - Design Spec"
category: "研究专题"
tags:
  - L1范数
  - 组会汇报
created: 2026-10-12
---

<!-- ppt-master-schema: design-spec/v1 -->
# L1 Norm Baseline Correction Report - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | L1 Norm Baseline Correction Report（L1 范数基线校正组会汇报） |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 18 |
| Primary Language | zh-CN |
| Target Audience | 导师与课题组同门，方向为强震动观测与地震工程；了解加速度记录与 PGV/PGD 等基本概念，但不熟悉凸优化，汇报人本人正在学习凸函数与 L1 范数。 |
| Communication Intent | 按“研究内容 → 研究背景 → 方法 → 结论”四段汇报：先讲清研究问题与核心概念，再交代为什么要研究，然后讲透 L1 范数方法本身并顺带把凸函数与 L1 范数的相关概念讲明白，最后给出结论。 |
| Desired Audience Outcome | 听众能说清这项研究要解决什么问题、用什么方法解决，并理解三个关键判断：L1 惩罚为什么产生稀疏跳变、凸性为什么保证全局最优、位移恢复为什么依赖事前部分长度。 |
| Core Message / Ask / Action | 这项研究把“漂移分几段、从哪一刻开始”从人工判断变成由 L1 范数正则化的凸优化自动求解；它的数学基础是 L1 与 L2 惩罚形状的差别，它的物理边界是事前部分必须足够长。 |
| Delivery Context | 课题组组会汇报，约 15 分钟、16:9 投影，逐页讲述；次要为会后自阅。 |
| Artifact Afterlife | 作为组会汇报存档，并作为本人继续学习凸函数与 L1 范数、开展复现实验时的参考材料。 |
| Reading Mode | balanced |
| Content Strategy | 未指定，按默认：只使用中文文献（熊政辉等 2019、张斌与俞言祥 2022、谢俊举等 2013）与其中的数据、结论；不引用英文文献，不涉及计算机视觉验证。 |
| Design Style | 精确网格 — pyramid 结论先行的叙事骨架 + swiss-minimal 栅格化视觉，零装饰、零卡片、零阴影 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy（用户确认开启） |
| Custom Animations | disabled — final Stage-2 proactive policy |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-09-28 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | top 64 / right 72 / bottom 56 / left 72 |
| Content Area | x 72–1208, y 64–664（标题带 y 64–140，正文带 y 156–628，页脚带 y 656–692） |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: pyramid
- **Mode Behavior**: 以 pyramid 为基底：每页先用一句话给出可判断的结论，再用一条证据链（数据、插图、对比）支撑；章节页承担一次结论闸门，末章收束到方法边界与可继续做的方向。
- **Visual style**: custom
- **Visual Style References**: swiss-minimal
- **Visual Style Behavior**: 锁定统一左边线与 12 栏栅格；页标题用大字号无衬线加一条 2px 主色规则线锚定，正文左对齐、行距 1.5 倍；不使用卡片、圆角、色块背景与投影，层次只靠发丝线与留白建立；插图与图表以满栏宽度呈现，四周留 32px 呼吸区。
- **Theme**: 工程报告的精确网格。跨页母题是一条从页标题延伸出的 2px 主色规则线，页脚只保留“章号 + 页码”一个最小标记；母题只承担位置连续性与阅读节奏，不做装饰。
- **Tone**: 冷静、克制、可核对；像一份写给同行看的技术报告，兼顾“我正好在学凸函数与 L1 范数”的教学口吻。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 页面底色；中文期刊插图（白底曲线）直接落在上面 |
| Secondary background | #F3F5F8 | 唯一允许的浅底区，用于结论句窄条与表格表头 |
| Primary | #123A5E | 标题、规则线、正文强调与图表主色 |
| Accent | #C64B32 | 全篇唯一强调色：关键数字、警示性限定条件、L1 曲线 |
| Secondary accent | #4B7EA8 | 次级信息：图注编号、对比项、L2 曲线与次级说明 |
| Body text | #1B2530 | 正文与列表文字 |
| Secondary text | #5A6672 | 图注、注脚、来源与页码 |
| Divider | #D8DEE5 | 发丝分隔线与表格边框 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 中性无衬线，字重加粗，靠字号与对齐建立层级 | Microsoft YaHei | Arial | sans-serif |
| Body | 与标题同族保持和谐，读长句不累 | Microsoft YaHei | Arial | sans-serif |
| Display | 与正文同族，仅靠字号与颜色承担量级冲击 | Microsoft YaHei | Arial | sans-serif |
| Footnote | 与正文同族，小字深灰 | Microsoft YaHei | Arial | sans-serif |

- **Title stack**: Microsoft YaHei, Arial, sans-serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Display stack**: Microsoft YaHei, Arial, sans-serif
- **Footnote stack**: Microsoft YaHei, Arial, sans-serif

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Display | 96 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 视线先落在页标题下的结论句（或封面/方法页的大数字与公式），再沿规则线向下进入一条证据链：左对齐短句 → 插图、图表或数字 → 图注与来源。
- **Composition tendency**: 单栏主导、满栏宽插图与图表；需要并列时才分两栏，且两栏高度由内容决定而非拉平。
- **Cross-page continuity**: 页标题位置、规则线起点、页脚“章号 + 页码”三者全篇不变；变化只出现在插图占位与图表区域。
- **Spacing posture**: 偏开放；靠 32px 级块间距与留白分区，绝不靠容器分隔。
- **Spacing anchors**: page margin 72px / block gap 32px / column gutter 40px / corner radius 0px / body leading 36px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/file-text | 研究内容与提纲类页面的最小标记 |
| tabler-outline/trending-up | 误差被积分放大的量级页 |
| tabler-outline/wave-sine | 信号、滤波与波形相关页面 |
| tabler-outline/target | 优化目标函数与凸优化页面 |
| tabler-outline/route | 方法流程与实验方案页面 |
| tabler-outline/flag | 结论与限定条件页面 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P10 | chart | line_chart | 在同一个自变量上对比 L1 与 L2 惩罚函数的形状，说明折点与稀疏解的关系 |
| P15 | table | metric_table | 三条记录的事前部分长度与基线识别误差、峰值速度恢复结果对照 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| zhang_fig01_record.png | 1620×920 | 1.76 | 芦山地震 51YAM 台 NS 向原始加速度、速度、位移时程 | Photo | 右侧 3/5 栏宽，左侧放结论与量级说明 | no-crop | user | Existing | 张斌、俞言祥（2022）图 1 | | |
| zhang_fig02_iwan.png | 1016×1060 | 0.96 | Iwan 两段式校正方法原理 | Photo | 左侧 2/5 栏宽，右侧放判据与困境说明 | no-crop | user | Existing | 张斌、俞言祥（2022）图 2 | | |
| xiong_fig01_noise.png | 1624×312 | 5.21 | 单段式、两段式、多段式三种加速度基线漂移噪声模型 | Photo | 满栏宽横向铺陈，紧接三条假设的文字 | no-crop | user | Existing | 熊政辉等（2019）图 1 | | |
| xiong_fig07_velocity.png | 1656×728 | 2.27 | 加入不同噪声模型后 El Centro 台 NS 向记录的速度恢复结果 | Photo | 满栏宽横向铺陈，下图注紧跟 | no-crop | user | Existing | 熊政辉等（2019）图 7 | | |
| xie_fig07_disp_gps.png | 1644×736 | 2.23 | 汶川近断层水平永久位移与 GPS 观测对比 | Photo | 满栏宽横向铺陈，作为方向应用前景的证据 | no-crop | user | Existing | 谢俊举等（2013）图 7 | | |

## IX. Content Outline

### Part 1: 研究内容（问题与核心概念）

#### Slide 01 - 封面

- **Cover impact**: hook 绑定为量级冲击 “0.01 gal → 18 cm”；composition Reference：左对齐大字号结论句占据上半页，文献出处与汇报信息压在下方，一条 2px 主色规则线横贯页面下三分之一。
- **Audience move**: 从“今天要听一篇 L1 范数的文献汇报” → “先被一个量级结论抓住，并知道讲的是哪一篇、讲哪四件事”。
- **Relationships**: 结论句 → 支撑量级 → 文献出处（order）。
- **Composition**: 左对齐大字结论占据上半页，文献信息压在规则线下方，页码位留空。
- **Title**: L1 范数正则化用于强震动基线校正
- **Core message**: 一次看不见的 0.01 gal 偏移，会在 60 s 里长成 18 cm 的位移误差；本文用 L1 范数正则化的凸优化自动确定基线漂移的分段与时刻。
- **Content**:
  - 主标题：L1 范数正则化用于强震动基线校正
  - 副标题：研究内容 · 研究背景 · 方法（凸函数与 L1 范数）· 结论
  - 量级句：0.01 gal 偏移持续 60 s → 速度误差 0.6 cm/s → 位移误差 18 cm
  - 文献出处：熊政辉，李小军，戴志军，陈苏. 2019. 基于 L1 范数正则化的强震动加速度记录基线漂移识别方法. 地震学报，41(1)：111–123
  - 汇报信息：组会汇报 · 汇报人 / 日期

#### Slide 02 - 汇报提纲

- **Audience move**: 从“不知道今天讲什么” → “知道四段结构，并明白重点在方法那一节，而且会把凸函数与 L1 范数讲清楚”。
- **Relationships**: 四个部分按汇报顺序排列（order）。
- **Title**: 汇报提纲
- **Core message**: 汇报按“研究内容 → 研究背景 → 方法 → 结论”四段推进，方法一节会先把凸函数与 L1 范数的基础概念补齐。
- **Content**:
  - 一 · 研究内容：要解决什么问题，涉及哪些核心概念
  - 二 · 研究背景：这个问题为什么至今没有标准答案
  - 三 · 方法：L1 范数正则化，以及凸函数、范数与稀疏性的基本概念
  - 四 · 结论：三条结论，以及它对我们后续工作的意义
  - 页脚注：文献来源 熊政辉等，2019，地震学报 41(1)：111–123

#### Slide 03 - 研究问题：小漂移如何被两次积分放大

- **Audience move**: 从“漂移只是点小噪声” → “明白它是位移误差的主要来源，且误差按时间平方增长”。
- **Relationships**: 同一偏移在加速度 / 速度 / 位移三域的形态变化（link）；常数偏移与真实地震信号叠加（overlap）。
- **Composition**: 左侧三条域内形态逐行排列，右侧放真实记录的三域时程图作为证据。
- **Title**: 研究问题：小漂移如何被两次积分放大
- **Core message**: 取位移只能两次积分，常数偏移积分一次成斜线、再积分成抛物线，所以微小加速度误差在位移上按时间平方放大。
- **Content**:
  - 加速度域：一个常数偏移叠加在真实信号上，肉眼几乎无感
  - 速度域：积分一次，偏移变成一条持续上爬的斜线
  - 位移域：再积分一次，变成越走越陡的抛物线
  - 量级：0.01 gal 持续 60 s = 速度误差 0.6 cm/s、位移误差 18 cm
  - 研究问题：怎样在不依赖人工判断的前提下，把这个漂移识别出来并扣除
- **Images**: zhang_fig01_record.png 为真实记录中“加速度几乎无感、位移已被漂移主导”的证据。

#### Slide 04 - 核心概念：从加速度到位移的四个词

- **Audience move**: 从“听过这些词” → “能用自己的话把加速度记录、两次积分、PGV/PGD、事前部分串起来”。
- **Relationships**: 四个概念按数据流程串联（order）。
- **Composition**: 四个概念等宽横排，各配一句定义与一句“为什么重要”。
- **Title**: 核心概念：从加速度到位移的四个词
- **Core message**: 强震仪记录的是加速度；两次积分才得到速度与位移；峰值速度与峰值位移是评价校正效果的两个指标；事前部分长度决定校正是否可信。
- **Content**:
  - 加速度记录：强震仪输出的是地面运动的加速度，单位 gal，1 gal = 1 cm/s²
  - 两次积分：加速度 → 速度 → 位移；每一次积分都会把低频误差放大一次
  - PGV 与 PGD：峰值速度与峰值位移，是判断校正后时程是否可用的两个指标
  - 事前部分：P 波到达之前那段本应是零线的记录，它越长，越容易判断基线在哪里
  - 一句话：位移的可靠性，取决于事前部分与校正方法的配合

#### Slide 05 - 核心概念：漂移从哪来，怎样算合格

- **Audience move**: 从“漂移就是仪器噪声” → “能分清两类来源，并记住两条判据允许永久位移存在”。
- **Relationships**: 两类来源并列对比（contrast）；两条判据并列（contrast）。
- **Composition**: 上半页两类来源左右并列，下半页两条判据逐行排列。
- **Title**: 核心概念：漂移从哪来，怎样算合格
- **Core message**: 漂移来自低频误差与地面倾斜两类原因；校正合格的标准是速度终了归零、位移末段平行于时间轴，后者允许非零。
- **Content**:
  - 来源一 · 低频误差：仪器噪声、恒定偏移、背景噪声、初始值和操作误差
  - 来源二 · 地面倾斜或旋转：仪器被歪，重力漏进水平分量，水平两轴同源
  - 判据一：地震动结束后速度应趋于零
  - 判据二：位移时程末段应平行于时间轴；平行不是归零，末端那个非零值就是永久位移
  - 提醒：垂直向的真实沉降是信号不是漂移，不能一并拉回零线

### Part 2: 研究背景

#### Slide 06 - 研究背景：为什么近场大震不能靠滤波

- **Audience move**: 从“校正就是高通滤波” → “理解滤波与永久位移处在同一频段，因此必须走分段校正路线”。
- **Relationships**: 两条技术路线分叉并各自导向一个后果（link）。
- **Composition**: 上下两段对照：上半讲滤波，下半讲分段校正，各配一条结论。
- **Title**: 研究背景：为什么近场大震不能靠滤波
- **Core message**: 高通滤波省事且客观，但漂移与永久位移同处低频段，会一起被滤掉；要保住永久位移，只能走分段校正。
- **Content**:
  - 路线一 · 高通滤波：把低频成分滤掉，流程客观，PEER 数据库的标准处理就是它
  - 代价：漂移与永久位移处在同一个低频段，滤掉漂移的同时也把永久位移滤掉
  - 路线二 · 分段校正：在速度时程上分段拟合直线，用直线斜率反推加速度的漂移量
  - 代价：需要回答“分几段、从哪一刻开始漂”，而这两个参数目前靠人工判断
  - 结论：小震可以用滤波，近场大震必须用分段校正

#### Slide 07 - 研究背景：分段校正的方法谱系与共同缺口

- **Audience move**: 从“只知道一两种方法” → “看清这条链的演化方向，并抓住所有方法的共同缺口”。
- **Relationships**: 方法按年代顺序演化成一条链（order）；各方法的共同缺口（membership）。
- **Composition**: 左侧放 Iwan 两段式原理图，右侧按年代列出三代方法并收束到缺口。
- **Title**: 研究背景：分段校正的方法谱系与共同缺口
- **Core message**: 从 Iwan 的固定两段式，到 Boore 用速度末尾拟合直线定时刻，再到能量比、位移平坦度等改进，所有方法都卡在同一处：分段数与分段位置需要人工判断。
- **Content**:
  - Iwan（1985）：以加速度首次与末次超过 50 gal 的两个时刻作为分段点，固定为两段式
  - Boore 等：在速度时程末尾拟合直线，用直线与时间轴的交点确定漂移起始时刻
  - 改进方法：能量比、位移平坦度、时移斜率比等，用来更客观地定关键时刻
  - 共同缺口：分段数与分段位置仍依赖专家经验，处理同一条记录的不同人可能给出不同结果，流程难以自动化与标准化
  - 这正是本文要填补的空白
- **Images**: zhang_fig02_iwan.png 说明加速度域是阶梯、速度域是折线、位移域是抛物线。

### Part 3: 方法（L1 范数、凸函数与稀疏性）

#### Slide 08 - 方法准备一：范数是什么

- **Audience move**: 从“听过 L1、L2 但说不清区别” → “能写出三种范数的定义，并知道它们惩罚的是什么”。
- **Relationships**: 三种范数并列对比（contrast）。
- **Composition**: 三个定义逐行排列，各行右侧给出该范数偏好什么样的解。
- **Title**: 方法准备一：范数是什么
- **Core message**: 范数是衡量向量“大小”的方式；选 L0 得到“数非零个数”，选 L1 得到“绝对值之和”，选 L2 得到“平方和开根号”，三者的解性格完全不同。
- **Content**:
  - 记号：向量 x 的范数记作 ‖x‖，可以理解成这个向量的“长度”或“代价”
  - L0 范数：非零元素的个数，最符合“稀疏”的本意，但求解是 NP 难问题
  - L1 范数：各元素绝对值之和，是 L0 的凸替代，因此可以高效求解
  - L2 范数：各元素平方和开根号，就是通常的欧氏长度
  - 关键差别：L2 偏好每个元素都小一点、雨露均沾；L1 偏好绝大多数元素正好为零
- **Mathematical content**: \|x\|_1 = \sum_i |x_i|

#### Slide 09 - 方法准备二：凸函数与凸优化

- **Audience move**: 从“凸函数只是课本里的一个定义” → “明白凸性为什么能保证解是唯一的、可靠的”。
- **Relationships**: 定义 → 性质 → 对本研究的意义，构成一条推导链（link）。
- **Composition**: 上方一行定义与判别式，下方三行性质与意义。
- **Title**: 方法准备二：凸函数与凸优化
- **Core message**: 凸函数是指函数图像上任意两点连线都不低于图像本身；凸优化问题的局部最优就是全局最优，因此解唯一且可验证。
- **Content**:
  - 定义：对任意两点与任意权重，都有 f(λx + (1−λ)y) ≤ λf(x) + (1−λ)f(y)，图像像一个碗
  - 判别：一元函数看二阶导数是否非负；多元函数看海森矩阵是否半正定
  - 性质一：局部最小值就是全局最小值，不会掉进“假的”低谷
  - 性质二：凸优化问题可以高效求解，主流工具箱都支持
  - 对本研究的意义：只要把目标函数写成凸形式，就不必再担心“解是不是唯一、是不是最好”
- **Mathematical content**: f(\lambda x + (1-\lambda) y) \le \lambda f(x) + (1-\lambda) f(y)

#### Slide 10 - 方法准备三：L1 为什么会产生稀疏解

- **Audience move**: 从“记住 L1 稀疏” → “能从惩罚函数的形状说出稀疏是怎么来的”。
- **Relationships**: 两条曲线形状的对比（contrast）；折点与稀疏解之间的因果关系（link）。
- **Composition**: 左侧放 L1 与 L2 惩罚函数的对比折线图，右侧放三点解释。
- **Title**: 方法准备三：L1 为什么会产生稀疏解
- **Core message**: |x| 在原点有一个尖折点，x² 在原点平缓；优化时最容易落在折点上，于是大量分量正好取零，这就是稀疏的来源。
- **Content**:
  - 曲线形状：L2 的 x² 在原点光滑、越远涨得越快；L1 的 |x| 是一条折线，原点处出现折点
  - 折点效应：约束或正则项在原点有折点时，最优解往往正好落在折点上，对应分量取零
  - 几何直觉：L1 的等值线是菱形、L2 是圆；菱形有尖角，等高线通常先切到尖角而不是边
  - 结果：L1 让解变得稀疏，L2 只让解变小
  - 对应到本研究：稀疏的就是基线的差分，也就是“跳变”
- **Visualization**: penalty-shapes – 同一自变量下 L1 与 L2 惩罚函数的形状对比。
- **Native-ready**: penalty-shapes=yes

#### Slide 11 - 本文方法：目标函数与它的物理含义

- **Audience move**: 从“看到一条公式” → “能逐项说出它管什么，并知道为什么解是阶梯状基线”。
- **Relationships**: 拟合残差项与稀疏正则项之间的权衡（contrast）。
- **Composition**: 中部一条目标函数公式，上方一行说明两个目标，下方两行说明参数与解的形状。
- **Title**: 本文方法：目标函数与它的物理含义
- **Core message**: 目标函数由“速度拟合残差”和“基线跳变的稀疏度”两项构成，正则项作用在基线的差分量上，所以解天然是阶梯状的分段恒定基线。
- **Content**:
  - 第一项：用最小二乘拟合速度时程，让校正后的速度尽量平；b 是待拟合的速度，A 把基线映射到速度
  - 第二项：对基线的跳变取 L1 范数，让跳变尽可能少
  - 物理含义：解出来的基线是阶梯状的分段线性函数，分几段、在哪跳、跳多少，全部由优化自动决定
  - 正则化参数 λ：平衡两项的权重，本文取 1；作者在结论中也指出如何取合适的 λ 仍是一个难题
  - 与既有方法的联系：它相当于把 Boore 方法里“人工定分段”的那一步换成优化求解
- **Mathematical content**: \min_x f(x) = \|Ax-b\|_2 + \lambda \|x\|_1

#### Slide 12 - 本文方法：三条假设与对应的噪声模型

- **Audience move**: 从“只知道有公式” → “知道公式背后的三条假设，并能对应到具体的漂移形态”。
- **Relationships**: 三条假设与图中三种噪声模型一一对应（membership）。
- **Composition**: 上方三条假设横排，下方满栏宽放三种噪声模型示意图。
- **Title**: 本文方法：三条假设与对应的噪声模型
- **Core message**: 三条假设是漂移次数未知、漂移分段恒定、震后速度归零；图中单段式、两段式、多段式就是它们的典型形态。
- **Content**:
  - 假设一：加速度基线的漂移是随机的，漂移次数无法事先确定
  - 假设二：某一时刻漂移发生突变，随后一段时间保持不变，即分段恒定的阶梯函数
  - 假设三：地震动结束后，速度应趋于零
  - 图注要点：单段式在强震动时段保持一个常量漂移，两段式在一次跳变后改变幅值，多段式出现多次跳变
  - 单位提示：文中把漂移幅值写作 m/s² 量级，按该领域惯例应为 gal（1 gal = 1 cm/s²）
- **Images**: xiong_fig01_noise.png 为论文给出的三种基线漂移噪声模型。

### Part 4: 结论

#### Slide 13 - 验证思路：一份有标准答案的考卷

- **Audience move**: 从“不知道怎么判断方法准不准” → “看懂这套带标准答案的受控实验，以及三条记录为什么是关键对照”。
- **Relationships**: 三条记录按事前部分长度构成单因素对照（contrast）。
- **Composition**: 上部三条记录逐行排列，下部一行说明噪声与比对方式。
- **Title**: 验证思路：一份有标准答案的考卷
- **Core message**: 真实记录没有标准答案，所以作者在干净记录上人为加入已知漂移，再让算法把它找回来；三条记录的唯一变量是事前部分长度。
- **Content**:
  - 数据：El Centro Array #9（1940 帝王谷，事前 0.04 s）、Bolu（1999 迪兹杰，事前 5.39 s）、TCU129（1999 集集，事前 20.65 s）
  - 噪声：分别加入单段式、两段式和多段式人工漂移，幅值已知
  - 比对：比较算法识别出的基线与已知噪声，再比较校正后的速度与位移
  - 设计意图：三条记录的事前部分被刻意拉开，用来单独考察“事前部分长度”这一个变量
- **Mathematical content**: \Delta g = g\theta

#### Slide 14 - 结论一：速度恢复稳健，不受事前部分长度影响

- **Audience move**: 从“以为漂移会同时毁掉速度和位移” → “记住速度稳、位移敏感这条分离结论”。
- **Relationships**: 不同噪声模型下速度恢复结果的一致性（membership）；速度与位移对同一变量的不同敏感性（contrast）。
- **Composition**: 上方满栏宽速度恢复图，下方三行结论与数字。
- **Title**: 结论一：速度恢复稳健，不受事前部分长度影响
- **Core message**: 即使在事前部分只有 0.04 s 的 El Centro 记录上，加入三类噪声后峰值速度都能恢复到约 3% 的误差以内。
- **Content**:
  - 原始记录 PGV 为 −29.66 cm/s
  - 加入单段式、两段式、多段式噪声后，恢复值分别为 −30.66、−30.66、−30.53 cm/s
  - 误差约 1 cm/s，折算约 3%
  - 结论：无论事前部分是否充足，该方法都能很好地恢复峰值速度和整体速度时程
- **Images**: xiong_fig07_velocity.png 为 El Centro 台 NS 向记录在三种噪声模型下的速度恢复结果。

#### Slide 15 - 结论二：位移恢复取决于事前部分长度

- **Audience move**: 从“以为方法精度是个固定值” → “明白精度由事前部分长度决定，并记住三档误差”。
- **Relationships**: 三条记录的识别误差按事前部分长度递增排列（order）；误差与事前部分长度呈反向对应（contrast）。
- **Composition**: 上部一行结论句，下部三行数据表。
- **Title**: 结论二：位移恢复取决于事前部分长度
- **Core message**: 事前部分 20.65 s 时识别误差小于 0.1 gal，事前部分 0.04 s 时升到约 1.39 gal，并且会在初始段把记录拉向零线。
- **Content**:
  - TCU129（事前 20.65 s）：识别出的漂移与真值几乎完全重合，误差小于 0.1 gal
  - Bolu（事前 5.39 s）：误差约 1.17 gal
  - El Centro（事前 0.04 s）：误差约 1.39 gal，且算法会把初始段拉向零线，连带带走一部分真实信号
  - 机理：事前部分越短，前期累积的积分误差越容易混进拟合速度，把结果拉偏
  - 提醒：事前部分过短时，“拉向零线”是系统性的副作用，垂直分量尤其要小心
- **Visualization**: result-summary – 三条记录的事前部分长度与识别误差、峰值速度恢复结果对照表。
- **Native-ready**: result-summary=yes

#### Slide 16 - 结论三：参数与代价

- **Audience move**: 从“记住了方法和数字” → “带走两条限定：λ 如何取值尚未解决，且任何校正都会压低位移幅值”。
- **Relationships**: 一条开放问题与一条固有代价并列（membership）。
- **Composition**: 上半页讲参数问题，下半页讲固有代价，中间用发丝线分隔。
- **Title**: 结论三：参数与代价
- **Core message**: 作者明确指出正则化参数 λ 的取值仍是一个难题；同时，基线校正本身会压制地震信号，使校正得到的位移幅值小于真值。
- **Content**:
  - 开放问题：λ 是模型相关的超参数，不同取值会直接改变结果，如何获取合适的值一直是个难题
  - 复现提示：两项量纲并不统一，换数据或改采样间隔后等效的 λ 会漂移，需要做敏感性检查
  - 固有代价：任何基线校正方法都不可避免地会压制地震信号，使校正得到的位移幅值小于真值
  - 用法：把校正后的位移当作系统性偏小的下限，而不是绝对真值
  - 对三分量的提醒：垂直分量存在真实沉降，不能套用“把初始段拉回零线”的策略

#### Slide 17 - 我的理解与下一步

- **Closing impact**: 绑定结论“先把凸函数与 L1 范数学扎实，再动手复现，最后处理三分量”；composition Reference：左侧三步计划纵向排列，右下放工程应用前景图与讨论问题。
- **Audience move**: 从“听完一项研究” → “看到一条可以动手的学习路径，并愿意就其中一步讨论”。
- **Relationships**: 三步计划按时间先后排列（order）；与工程应用前景之间是目的关系（link）。
- **Composition**: 左栏三步计划，右下放永久位移场应用图，底部一行讨论问题。
- **Title**: 我的理解与下一步
- **Core message**: 顺着这项研究往下走，最短的一条路是“先补凸函数与 L1 范数的数学，再复现单分量，最后处理三分量”。
- **Content**:
  - 第一步 · 补数学：掌握凸集与凸函数、范数与稀疏性、LASSO 与凸优化求解器的基本用法
  - 第二步 · 复现：用 CVXPY 实现目标函数，在 TCU129 上复现“误差小于 0.1 gal”，并测试 λ 变化对结果的影响
  - 第三步 · 扩展：把 EW/NS/UD 三分量差分堆叠，用组稀疏让水平两轴的跳变时刻尽量共享，并设计公平的合成实验对比两种方案
  - 评价指标：同时报告 PGD 误差、永久位移误差与位移矢量末端的三维距离，不再只看相关系数
  - 讨论问题：水平两轴的跳变时刻应该共享还是各自独立？垂直分量是否必须区别对待？
- **Images**: xie_fig07_disp_gps.png 展示汶川近断层水平永久位移场与 GPS 对比，说明这类方法的用武之地。

#### Slide 18 - 小结与讨论

- **Audience move**: 从“听完四个部分” → “能用一句话复述这项研究的内容、背景、方法与结论，并带着问题离场”。
- **Relationships**: 四个部分回溯成一句话（order）。
- **Composition**: 四行结构居中偏左，底部留讨论问题。
- **Title**: 小结与讨论
- **Core message**: 这项研究要解决的是“基线漂移无人为判断地自动识别”；它靠 L1 范数正则化把问题变成凸优化；代价是结果依赖事前部分长度，且位移幅值会被系统性压低。
- **Content**:
  - 研究内容：近断层强震记录的基线漂移识别，核心概念是两次积分、PGV/PGD 与事前部分
  - 研究背景：滤波保不住永久位移，分段校正又卡在人工定分段
  - 方法：以 L1 范数正则化构造凸优化目标函数，用 L1 的稀疏性自动定出漂移的分段与时刻
  - 结论：速度恢复稳健；位移恢复随事前部分长度改善；λ 的取值与幅值压制是两点限定
  - 讨论：三分量联合处理是否值得？垂直分量应如何处理？

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注给出该页的口头讲解要点、被页面省略的推导与数值细节、以及向下一页的过渡句；只引用中文文献（熊政辉等 2019、张斌与俞言祥 2022、谢俊举等 2013）与其中的数据，不引入英文文献，不涉及计算机视觉验证。涉及凸函数与 L1 范数的页面按“我正好在学”的口吻做简要科普。
- **Total duration**: 约 15 分钟，18 页平均每页 45–55 秒
- **Notes style**: 正式但口语化，按页讲述，关键数字明确读出
- **Presentation purpose**: 按“研究内容 → 研究背景 → 方法 → 结论”讲清这项研究，并把凸函数与 L1 范数的相关概念一并讲明白。
