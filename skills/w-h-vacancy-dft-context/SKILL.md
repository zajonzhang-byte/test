---
name: w-h-vacancy-dft-context
description: Use this skill as persistent research context when the user asks about VASP, CI-NEB, Material Studio modeling, W-H-vacancy systems, vacancy formation energy, H trapping or binding energy, Frenkel defects, SIA formation, NEB paths, KPOINTS, supercell size, or first-principles calculations of H effects on vacancy formation and evolution in tungsten. Treat it only as background context; do not modify files, generate POSCAR/CONTCAR, change VASP inputs, or give concrete operation commands unless the user explicitly asks.
---

# 研究背景：W 中空位与 H 的相互作用

使用本 Skill 时，默认参考用户的第一性原理计算研究背景，帮助回答 W-H-空位体系、VASP、CI-NEB、Material Studio 建模、空位形成能、H 捕获能、Frenkel 缺陷、SIA、NEB 路径、K 点和超胞尺寸等问题。

用户建议名为 `w_h_vacancy_dft_context`；实际安装名为 `w-h-vacancy-dft-context`，因为 Codex Skill 名称只能使用小写字母、数字和连字符。

这个skills我可能会频繁更新。

## 核心背景

用户的主要研究领域是核聚变材料中的钨基材料，使用第一性原理计算研究氢对钨中空位形成与演化的影响。主要计算软件是 VASP，结构建模常用 Material Studio 2020，动态过程主要使用 CI-NEB 方法。

只使用本 Skill 处理第一个研究方向：W 中空位与 H 的相互作用。不要把第二个研究方向，也就是 W 中间隙 H-He 相互作用，混入本 Skill，除非用户明确要求。

## 研究目标

默认按以下目标理解相关问题：

- 研究纯 W 或含 H 的 W 中生成第一个空位的过程。
- 研究单空位向双空位演化。
- 研究双空位继续长大为多空位。
- 进一步研究 6 空位生成 7 空位的过程。
- 分析不同 H 原子数量、不同 H 分布位置对空位形成能、H 捕获能、Frenkel 缺陷形成能垒和缺陷演化路径的影响。

## 静态计算模型

静态计算主要使用接近正方形或立方形的 BCC W 超胞。

常用模型和用途：

- 纯 W 的 BCC 晶格常数约为 3.172 Å。
- 对于单空位、双空位等较小空位团簇，常用 4×4×4 的 BCC W 超胞。
- 4×4×4 纯 W 超胞包含 128 个 W 原子。
- 常用 K 点为 3×3×3。
- 静态计算主要用于挖掉一个 W 计算空位形成能，在空位附近放置不同数量的 H 计算 H 捕获能，比较 H 在不同空位团簇中的稳定构型，并研究 H 对空位团簇稳定性的影响。

这些参数只是背景和常用习惯，不代表所有体系中的最终正确设置。

## 动态计算模型：CI-NEB

动态计算主要使用一个长方形超胞，其中 [111] 方向作为 z 轴。这个晶胞是通过 Material Studio 2020 中的矩阵变换，把 BCC W 晶胞转换成适合研究 <111> 方向链式位移的长方形晶胞。

常用扩胞包括：

- 2×1×5 扩胞，对应 120 个 W 原子。
- 2×1×7 扩胞，对应 168 个 W 原子。

这些长方形 [111] 取向超胞主要用于：

- 纯 W 生成第一个单空位的 CI-NEB。
- 已有单空位时，单空位附近 W 原子脱离原格点，形成第二个空位的 CI-NEB。
- 比较不同 H 原子数量对 Frenkel 缺陷形成能垒的影响。
- 研究 H 辅助的空位动态生成机制。

## NEB 路径的物理图像

在用户体系中，NEB 的初末态需要保持原子一一对应。

如果单空位周围占据 n 个 H，且 1NN 的某个 W 原子想脱离原本晶格位置形成 SIA，那么它通常不是简单地单个原子移动，而是沿 <111> 方向发生链式位移：

- 1 号 W 原子离开原格点。
- 它沿 [111] 方向顶开 2 号 W。
- 2 号 W 顶开 3 号 W。
- 3 号 W 顶开 4 号 W。
- 这个过程继续传递，直到第 5 号或第 6 号附近。
- 最后可能由第 5 号或第 6 号 W 与下一个 W 原子共同占据一个晶格位点，形成 SIA。
- 原来 1 号 W 的位置形成新的空位。

这里的“1 号、2 号、3 号……”只是为了描述链式位移过程，实际上 W 原子本身是等价的。

回答 NEB 相关问题时，要强调这不是单个 W 原子的简单跳跃，而是多个 W 原子的协同位移，同时 H 原子也可能发生明显移动。因此 NEB 路径构造、初末态对应关系、H 原子跟随方式和中间 image 的合理性都非常重要。

## K 点设置习惯

动态 NEB 计算中，由于超胞是长方形且 z 方向较长，K 点经常使用非等比例组合，例如：

- 5×5×1。
- 3×3×1。
- 4×5×2。
- 其他根据超胞尺寸调整的组合。

回答 K 点相关问题时，需要结合实际晶胞边长、体系大小、是否是静态弛豫、NEB 还是高精度能量比较来判断。应根据具体超胞尺寸和收敛性测试结果选择合适的 K 点方案，而不是采用固定的经验设置。

## 回答偏好

回答用户时，尽量按照以下方式组织：

- 先用通俗语言解释物理图像。
- 再给出严谨的第一性原理或 VASP 计算判断。
- 如果涉及建模，指出初态、末态、原子对应关系和周期性边界条件是否合理。
- 如果涉及 NEB，重点检查初末态是否物理合理、是否存在原子编号错配、是否需要 IDPP、image 数量是否足够、是否可能出现不合理的原子穿越或跳跃、H 原子是否应该跟随弛豫、末态是否需要充分弛豫。
- 如果涉及能量，区分空位形成能、H 捕获能、H 结合能、Frenkel 缺陷形成能、NEB 迁移能垒和末态相对能量。
- 如果用户的说法可能有问题，直接指出，不要顺着错误假设继续回答。
- 语言风格采用“大白话 + 学术审查”：既要让用户听懂，也要保证计算逻辑严谨。

## 重要限制

这个 Skill 只是背景信息，不代表所有参数都是最终正确设置。

除非用户明确要求，否则不要：

- 自动修改 VASP 输入文件。
- 自动生成 POSCAR 或 CONTCAR。
- 自动改变 KPOINTS、INCAR 或 POTCAR。
- 自动判断某个结构已经收敛。
- 捏造文献数据。
- 把 W 中间隙 H-He 相互作用混入本 Skill。
- 在用户只问概念、判断或方案时，主动给出会改动文件或参数的具体操作命令。
