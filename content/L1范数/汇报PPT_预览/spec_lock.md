---
title: "Execution Lock"
category: "研究专题"
tags:
  - L1范数
  - 组会汇报
created: 2026-10-12
---

<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 导师与课题组同门，方向为强震动观测与地震工程；了解加速度记录与 PGV/PGD，但不熟悉凸优化，汇报人本人正在学习凸函数与 L1 范数。
- objective: 按研究内容、研究背景、方法、结论四段讲清 L1 范数正则化用于强震动基线校正这项研究，并把凸函数与 L1 范数的相关概念一并讲明白，使听众能说清研究问题、方法原理与结论边界。
- core_message: 这项研究把“漂移分几段、从哪一刻开始”从人工判断变成由 L1 范数正则化的凸优化自动求解；数学基础是 L1 与 L2 惩罚形状的差别，物理边界是事前部分必须足够长。
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: pyramid
- mode_behavior: 以 pyramid 为基底：每页先用一句话给出可判断的结论，再用一条证据链（概念、公式、插图、数据）支撑；四段结构逐段推进，末页收束回一句话小结与讨论问题。

## visual_style
- visual_style: custom
- visual_style_references: swiss-minimal
- visual_style_behavior: 锁定统一左边线与 12 栏栅格；页标题用大字号无衬线加一条 2px 主色规则线锚定，正文左对齐、行距 1.5 倍；不使用卡片、圆角、色块背景与投影，层次只靠发丝线与留白建立；插图与图表以满栏宽度呈现，四周留 32px 呼吸区。

## colors
- background: #FFFFFF
- secondary_bg: #F3F5F8
- primary: #123A5E
- accent: #C64B32
- secondary_accent: #4B7EA8
- body_text: #1B2530
- secondary_text: #5A6672
- divider: #D8DEE5

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: Microsoft YaHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- display_family: Microsoft YaHei, Arial, sans-serif
- footnote_family: Microsoft YaHei, Arial, sans-serif
- body: 24
- title: 42
- subtitle: 32
- annotation: 18
- display: 96
- footnote: 16

## icons
- library: tabler-outline
- inventory: tabler-outline/file-text, tabler-outline/trending-up, tabler-outline/wave-sine, tabler-outline/target, tabler-outline/route, tabler-outline/flag
- stroke_width: 2

## images
- p03: images/zhang_fig01_record.png | source=user | crop=no-crop
- p07: images/zhang_fig02_iwan.png | source=user | crop=no-crop
- p12: images/xiong_fig01_noise.png | source=user | crop=no-crop
- p14: images/xiong_fig07_velocity.png | source=user | crop=no-crop
- p17: images/xie_fig07_disp_gps.png | source=user | crop=no-crop

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: dense
- P16: breathing
- P17: breathing
- P18: anchor

## pptx_structure
- mode: flat

## page_visualizations
- P10: chart/line_chart
- P15: table/metric_table

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 要求画面简约 (user)
- 尽量不要参考英文文献，特别是计算机视觉识别这一块 (user)
