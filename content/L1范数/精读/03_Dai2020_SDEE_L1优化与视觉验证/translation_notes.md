---
title: "translation_notes — Dai et al. (2020)"
category: "研究专题"
tags:
  - L1范数
  - 文献精读
created: 2026-10-12
---

# translation_notes — Dai et al. (2020)

## 阅读模式

- 源语言：英文；输出：段落级中英对照（`**Original:**` / `**中文:**`），公式单独成块（E001、E002），图件按"首次实质提及"就近放置。
- 覆盖范围：正文第 1—5 节与 Data and resources 全部覆盖（S001—S048）。参考文献列表（第 9—10 页）未逐条翻译，属有意跳过。

## 术语决定

| 决策 | 说明 |
|---|---|
| baseline drift / baseline offset | 统一译"基线漂移 / 基线偏移"；"jump"统一译"跳变" |
| prior part | 统一译"事前部分"，与中文姊妹篇保持一致 |
| piecewise linear fitting | "分段线性拟合" |
| step function | "阶梯函数"（原文把漂移定义为分段恒定的阶梯） |
| gal | 保留 gal，等价于 $\mathrm{cm/s^2}$ |

## 公式处理

- E001、E002 均从 PDF 文本层提取并人工核对，判定为高置信度；已写入 `source_map.json` 的 `blocks`（`type: "equation"`）。
- 原文式 (2) 的第一项在版面上未显示平方符号，本精读按原文保留为 $\|Ax-b\|_2$，未擅自补平方；读者若按标准 LASSO 复现，请注意这一差异并做敏感性检验。

## 图件与不确定性

- 全部 11 张图（Fig. 1—11）已切图至 `assets/figures/`，另附每页整页渲染于 `assets/pages/`。
- 所有紧裁框由"图注位置 + 同栏文本行间隙"自动推算，属**近似裁切**（`assets/figure_manifest.json` 中标注 `confidence: approximate`）。若某图边框不完整，请以同页 `assets/pages/pNN.png` 为准。
- 未做人工视觉复核（本环境无法查看图像），因此裁切精度存在不确定性，已在每张图卡下方给出对应整页渲染路径。

## 待补内容

- 参考文献列表未翻译。
- 图 5(b)、图 10 的 B-A 图具体散点数值未逐点提取，只保留了正文给出的相关系数。
