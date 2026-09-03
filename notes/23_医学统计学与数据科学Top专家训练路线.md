# 医学统计学与数据科学 Top 专家训练路线

## 0. 文件定位

本路线面向已经具备医学统计学、R 语言、科研设计和论文审阅基础的高阶研究者。目标不是重复本科知识，也不是以“学完多少本书”为完成标准，而是形成可持续输出原创方法、可靠软件、规范证据和高质量人才培养体系的能力。

“Top 专家”不由掌握的函数数量定义，而由以下可验证产出定义：

\[
\text{理论判断}
+
\text{研究设计}
+
\text{计算实现}
+
\text{验证治理}
+
\text{原创贡献}
+
\text{学术领导}.
\]

本文件属于整合性训练方案，不是任何单一教材的学习要求。

---

## 1. Top 专家的九维能力

| 维度 | 熟练层 | Top 层 |
|---|---|---|
| 问题形式化 | 会选择方法 | 能将模糊医学问题转为 estimand、决策与识别条件 |
| 概率与推断 | 会使用检验和区间 | 能推导、比较有限样本、渐近、贝叶斯与重抽样程序 |
| 因果推断 | 会调整混杂 | 能设计目标试验、处理时间依赖、选择偏倚和可迁移性 |
| 预测建模 | 会训练模型 | 能组织无泄漏开发、外部验证、校准、效用和部署监测 |
| 数据工程 | 会清理数据 | 能建立可审计的数据谱系、时间语义、版本和质量契约 |
| 计算统计 | 会调用软件 | 能实现估计器、模拟操作特征、诊断数值失败并优化计算 |
| 软件工程 | 有分析脚本 | 能维护包、测试、CI、环境锁定和可复现研究产品 |
| 方法研究 | 会应用文献方法 | 能识别理论缺口、提出估计目标、证明性质并做基准研究 |
| 学术领导 | 能完成个人研究 | 能制定标准、培养团队、组织多中心合作和提升领域质量 |

---

## 2. 训练原则

### 2.1 以产出而非阅读量计量

每个知识模块必须形成至少一种可复核产出：

- 定理推导；
- 模拟实验；
- 方法复现；
- R 包函数；
- 分析计划；
- 审稿清单；
- 课程单元；
- benchmark；
- 方法论文；
- 临床转化报告。

### 2.2 任何方法都做四次学习

1. **定义**：估计什么；
2. **推导**：为何成立；
3. **模拟**：何时失效；
4. **实证**：如何改变医学结论。

### 2.3 同一问题至少用三种视角

- 设计/因果视角；
- 统计推断视角；
- 预测/决策视角。

这能防止把拟合、解释、预测和因果混为一谈。

### 2.4 先透明基线，后复杂模型

每个复杂方法都必须与：

- 简单统计基线；
- 标准领域方法；
- 理论最优或模拟真值；

进行比较。

---

## 3. 总体路线：24 个月六阶段

| 阶段 | 月份 | 主任务 | 核心产出 |
|---|---:|---|---|
| I | 1–3 | 概率、统计推断与线性模型重构 | 定理笔记、模拟库、统一线性模型讲义 |
| II | 4–7 | 渐近统计、经验过程与半参数效率 | EIF 推导集、one-step 包、覆盖率 benchmark |
| III | 8–10 | 贝叶斯建模与计算 | 先验库、SBC/PPC 工作流、贝叶斯试验模拟 |
| IV | 11–14 | 因果推断、纵向与生存 | 目标试验模板、时间依赖分析、敏感性工具 |
| V | 15–18 | 预测、机器学习与医学 AI | 无泄漏 pipeline、外部验证、模型卡与部署规范 |
| VI | 19–24 | 原创方法、软件、论文和团队体系 | R 包、方法论文、开放 benchmark、课程与标准 |

每个阶段都同时保留医学应用和 R 工程线，不允许理论与计算分离。

---

## 4. 阶段 I：概率与经典统计推断重构（第 1–3 月）

### 4.1 理论主题

- 概率空间、条件概率、独立性；
- 随机变量变换与 Jacobian；
- 条件期望与投影；
- 常用分布与指数族；
- 充分、最小充分、完备与辅助统计量；
- Rao–Blackwell、Lehmann–Scheffé、Basu；
- MLE、矩估计、Bayes 规则；
- Neyman–Pearson、UMP、LRT；
- 枢轴量、检验反演和精确区间；
- 正态线性模型、ANOVA、ANCOVA 和线性对比。

### 4.2 必做推导

1. 正态样本中 \(\bar X\) 与 \(S^2\) 的结构；
2. 指数族的充分统计量；
3. Beta–Binomial 和 Gamma–Poisson 后验；
4. 单参数指数族的单调似然比；
5. t 检验、ANOVA 与线性模型的统一；
6. LRT、Wald 与 score 的构造；
7. logistic 和 Poisson score 方程。

### 4.3 模拟实验

- 二项比例 Wald/score/exact 区间覆盖；
- 稀有事件下 Wald、LRT、score；
- 方差不齐下 pooled t 与 Welch；
- 非正态和重尾下均数、截尾均数和秩检验；
- 多重比较方法的错误率与功效；
- 模型错设下普通与稳健标准误。

### 4.4 阶段产出

```text
inference-foundations/
├── theorem-notes/
├── derivations/
├── simulations/
├── figures/
├── teaching-module/
└── review-checklist.md
```

通过标准：能从概率模型独立推导常用检验，而不是记忆软件输出。

---

## 5. 阶段 II：渐近、经验过程与半参数效率（第 4–7 月）

### 5.1 理论主题

- 依概率/分布/几乎处处收敛；
- \(o_p\)、\(O_p\)、紧性；
- Delta 与泛函 Delta；
- M/Z 估计；
- Argmax 定理；
- 渐近线性与影响函数；
- 相邻性、Le Cam 引理与 LAN；
- 卷积和局部渐近极小极大；
- U 统计量和 Hájek 投影；
- 经验过程、GC/Donsker 类；
- Bootstrap 一致性与失败；
- 半参数切空间、有效 score 与 EIF。

### 5.2 必做推导

1. 一般 Z 估计的 sandwich 方差；
2. 样本分位数影响函数；
3. AUC 的 U 统计量表示和一阶投影；
4. Kaplan–Meier 或生存函数的影响函数；
5. ATE 的 EIF；
6. 缺失结局均值的 EIF；
7. AIPW 二阶余项与双重稳健性；
8. one-step 与 MLE 一阶等价的示例。

### 5.3 计算项目

开发一个小型 R 包，例如 `medIF`：

```text
R/
├── if_mean.R
├── if_quantile.R
├── if_auc.R
├── aipw_ate.R
├── crossfit.R
└── variance.R
```

要求：

- roxygen2 文档；
- 单元测试；
- 与已知软件结果比较；
- 仿真覆盖；
- vignette；
- CI。

### 5.4 深化问题

- nuisance 估计速率何时足够；
- Donsker 条件为何出现；
- cross-fitting 解决什么、不解决什么；
- 边界和非光滑参数为何非正则；
- Bootstrap 为何对最大值失败；
- 选择后推断为何不再常规正态。

通过标准：能够从目标泛函推导 EIF，识别余项，并用模拟验证一阶理论。

---

## 6. 阶段 III：贝叶斯建模与计算（第 8–10 月）

### 6.1 理论主题

- 先验、似然、后验与预测；
- 共轭模型；
- 决策理论与损失；
- 层级模型与交换性；
- 混合模型和收缩；
- Bayes factor 与预测比较；
- Bernstein–von Mises 及其边界；
- 先验—数据冲突；
- 鲁棒先验和历史借力。

### 6.2 计算主题

- Gibbs、Metropolis–Hastings；
- HMC/NUTS；
- 非中心参数化；
- \(\hat R\)、ESS、发散；
- prior predictive；
- posterior predictive；
- simulation-based calibration；
- LOO/WAIC；
- posterior predictive scoring。

### 6.3 医学项目

至少完成三个：

1. 多中心二分类层级模型；
2. 稀有事件 logistic 的弱信息先验；
3. 历史对照借力临床试验；
4. 贝叶斯状态空间疾病监测；
5. 贝叶斯生存或 competing risk；
6. 多终点层级模型。

### 6.4 操作特征实验

对贝叶斯试验模拟：

- 真效应为 0、临床边界和目标效应；
- 先验正确、过乐观和冲突；
- 停止概率；
- 样本量分布；
- 错误决策率；
- 后验区间覆盖；
- 历史借力程度。

通过标准：既能解释后验，又能向频率学派审评者报告操作特征。

---

## 7. 阶段 IV：因果、纵向与生存（第 11–14 月）

### 7.1 因果问题形式化

- 潜在结局；
- 一致性；
- 可交换性；
- positivity；
- SUTVA/干扰；
- 目标试验；
- transportability；
- competing events；
- intercurrent events。

### 7.2 方法主题

- 标准化/g-computation；
- IPW；
- matching；
- doubly robust estimation；
- longitudinal g-formula；
- marginal structural models；
- structural nested models；
- mediation；
- instrumental variables；
- regression discontinuity；
- difference-in-differences；
- interrupted time series；
- negative controls；
- quantitative bias analysis。

### 7.3 生存与事件史

- counting process 表示；
- risk set；
- Kaplan–Meier 与 Nelson–Aalen；
- Cox 与非比例风险；
- RMST；
- competing risks；
- multi-state；
- recurrent events；
- joint models；
- interval censoring；
- dependent censoring。

### 7.4 必做项目

1. 将一篇观察性研究重写为目标试验方案；
2. 构造 time-varying confounding 模拟；
3. 比较 Cox HR 与 RMST 差；
4. 做未测混杂 E-value 之外的定量偏倚分析；
5. 设计一个负对照；
6. 在多中心数据上做 transportability 分析。

通过标准：能明确区分关联模型、预测模型和因果 estimand，并能写出识别公式。

---

## 8. 阶段 V：预测、机器学习与医学 AI（第 15–18 月）

### 8.1 数据科学主题

- 数据谱系和数据契约；
- 标签治理；
- 时间可用性；
- feature store；
- nested resampling；
- regularization；
- trees/boosting/random forest；
- SVM；
- neural networks；
- sequence models；
- multimodal learning；
- uncertainty estimation；
- calibration；
- domain shift；
- fairness；
- interpretability；
- deployment monitoring。

### 8.2 模型评价

- discrimination；
- calibration；
- proper scoring rules；
- decision curve；
- prediction intervals；
- external validation；
- internal-external CV；
- temporal validation；
- silent prospective validation；
- impact evaluation。

### 8.3 必做 benchmark

选择一个临床任务，比较：

1. 基线风险率；
2. 临床评分；
3. logistic/penalized logistic；
4. GAM；
5. tree ensemble；
6. neural model；
7. calibrated ensemble。

统一：

- 相同数据切分；
- 相同信息边界；
- 嵌套调参；
- 相同指标；
- 亚组评价；
- 计算成本；
- 可解释性和部署成本。

### 8.4 工程产出

- 模型卡；
- 数据卡；
- 单元测试；
- 容器或环境锁；
- API；
- 监测 dashboard；
- 漂移规则；
- 回滚方案。

通过标准：模型能够在独立时间/中心数据上重建并评价，而非仅在 notebook 中运行。

---

## 9. 阶段 VI：原创方法与学术领导（第 19–24 月）

### 9.1 研究缺口识别

从以下交叉处寻找问题：

- estimand 与算法不匹配；
- 复杂抽样与机器学习；
- 时间依赖和数据漂移；
- 高维 nuisance 与有限样本覆盖；
- 多中心可迁移性；
- 混合暴露和因果效应；
- 动态治疗策略；
- 生存预测校准；
- 缺失非随机和预测部署；
- 医学 AI 反馈回路；
- 临床试验中的外部数据借力。

### 9.2 方法论文最低组成

1. 清楚的目标参数；
2. 识别条件；
3. 估计程序；
4. 一致性/渐近线性/效率或有限样本性质；
5. 计算算法；
6. 模拟设计；
7. 与强基线比较；
8. 实证应用；
9. 软件；
10. 局限与失败场景。

### 9.3 Benchmark 论文最低组成

- 预注册或冻结方案；
- 多数据集；
- 统一预处理和调参预算；
- 无泄漏；
- 统计不确定性；
- 运行时间和资源；
- 失败记录；
- 可复现代码；
- 不只比较平均排名；
- 评价数据集与算法交互。

### 9.4 学术领导产出

- 领域报告规范；
- 多中心数据字典；
- 方法课程；
- 开源 R 包；
- 青年教师/研究生训练营；
- 统计审稿模板；
- reproducibility checklist；
- 数据和模型治理委员会流程。

通过标准：形成至少一项可被其他团队复用的公共方法资产。

---

## 10. 每周训练节律

建议每周 12–15 小时高强度方法训练，按比例分配：

| 模块 | 比例 | 产出 |
|---|---:|---|
| 理论阅读与推导 | 25% | 定理卡、手推证明 |
| 模拟与数值实验 | 25% | 可运行脚本、覆盖图 |
| 实证复现 | 20% | 重现论文、差异日志 |
| 软件工程 | 15% | 函数、测试、CI |
| 写作与教学 | 10% | 方法说明、课程页 |
| 文献与研究议题 | 5% | gap memo |

### 10.1 每周固定交付

- 一页定理或方法卡；
- 一个模拟图；
- 一个经过测试的 R 函数；
- 一段方法学批判；
- 一次 10 分钟口头讲解。

---

## 11. 定理卡模板

```text
定理/结果：
目标：
模型与参数空间：
主要条件：
结论：
证明主线：
影响函数/极限分布：
有限样本风险：
失败场景：
模拟验证：
医学应用：
可替代方法：
```

定理卡的重点不是抄证明，而是识别每个条件在医学数据中对应什么。

---

## 12. 模拟实验标准

### 12.1 场景维度

- 样本量/事件数；
- 效应大小；
- 分布尾部；
- 非线性；
- 共线性；
- 缺失；
- 误分类；
- 聚类；
- 时间依赖；
- positivity；
- 模型错设；
- 数据漂移。

### 12.2 结果

- bias；
- empirical SE；
- mean estimated SE；
- coverage；
- type I error；
- power；
- RMSE；
- convergence/failure；
- runtime；
- memory；
- calibration；
- decision utility。

### 12.3 Monte Carlo 误差

对覆盖率 \(\hat p\)，报告

\[
MCSE=\sqrt{\hat p(1-\hat p)/R}.
\]

模拟重复次数应由目标精度决定，而不是固定使用 1000 次。

---

## 13. 论文复现标准

复现分为四层：

1. **结果复现**：相同数据和代码得到相同结果；
2. **分析复现**：独立实现得到近似结果；
3. **稳健复现**：合理替代模型下结论稳定；
4. **外部复现**：新数据中结果成立。

复现日志应记录：

- 数据版本；
- 软件版本；
- 与原文差异；
- 未说明选择；
- warning；
- 无法重建部分；
- 结论敏感点。

---

## 14. 高水平 R 能力路线

### 14.1 分析层

- vectorization；
- formulas/design matrices；
- S3/S4/R6 基础；
- numerical optimization；
- sparse matrices；
- parallel computing；
- reproducible RNG；
- profiling。

### 14.2 包开发层

- `usethis`/`devtools`；
- roxygen2；
- testthat；
- vignettes；
- pkgdown；
- CI；
- semantic versioning；
- dependency control；
- reverse dependency checks。

### 14.3 研究流水线

- `targets` 或等价 DAG pipeline；
- `renv`；
- Quarto/R Markdown；
- Git/GitHub；
- container；
- data validation；
- automated reports。

### 14.4 性能层

- profiling first；
- efficient data.table/dplyr；
- Rcpp only when justified；
- memory-aware processing；
- chunking/Arrow/database pushdown；
- reproducible parallelism。

---

## 15. Python 与 SQL 的补充要求

虽然 R 是主分析语言，Top 数据科学专家还需：

### SQL

- join cardinality；
- window functions；
- temporal joins；
- slowly changing dimensions；
- query plans；
- transaction/version semantics；
- data quality assertions。

### Python

- NumPy/pandas 或 Polars；
- scikit-learn pipeline；
- PyTorch/JAX 基础；
- model serialization；
- API/service；
- interoperability with R；
- reproducible environment。

目标不是语言数量，而是能够审查完整医学数据系统。

---

## 16. 数学先修与补强

### 必须掌握

- 多元微积分；
- 线性代数与投影；
- 概率与条件期望；
- 优化；
- 测度论基础；
- 度量/赋范/Hilbert 空间基础；
- 随机过程基础。

### 针对渐近和半参数

- 弱收敛；
- Radon–Nikodym 导数；
- Fréchet/Gâteaux/Hadamard 导数；
- 正交投影；
- 函数空间紧性；
- 经验过程复杂度。

数学学习应直接链接统计对象，不必脱离应用追求形式堆积。

---

## 17. 阅读仓库的高阶顺序

### 第一层：问题与设计

- 03 整合研究工作流；
- 01 Gordis；
- 08 科研解释边界。

### 第二层：经典推断

- 04 医学统计学第 8 版；
- 17 Casella–Berger；
- 21 推断统一框架。

### 第三层：渐近与半参数

- 18 van der Vaart；
- 24 定理地图与医学桥接。

### 第四层：计算和贝叶斯

- 05 医学统计分析与 R；
- 10 R 语言实战；
- 19 Press 贝叶斯；
- 11 统计学精通路线。

### 第五层：预测与工程

- 20 Torgo；
- 22 医学模型开发部署规范；
- 16 现代时间序列实战；
- 12–15 时间序列体系。

### 第六层：专题原创

- 02 环境混合物；
- 生存、因果、高维、动态预测等后续专题。

---

## 18. 专家作品集

24 个月结束时，建议形成：

1. 100 张定理卡；
2. 30 个覆盖率/功效模拟；
3. 10 篇高水平方法论文复现；
4. 3 个完整医学预测 benchmark；
5. 2 个半参数或因果估计器实现；
6. 1 个公开 R 包；
7. 1 套医学统计审稿规范；
8. 1 套可复现课程；
9. 1 个多中心数据标准；
10. 1–2 篇原创方法或规范论文。

数量不是目的，要求每项可运行、可审计、可被他人复用。

---

## 19. 专家级自评量表

每项 0–4 分：

- 0：未接触；
- 1：能解释概念；
- 2：能正确应用；
- 3：能推导、诊断和教学；
- 4：能改进方法并形成公共产出。

| 领域 | 目标分 |
|---|---:|
| 概率与经典推断 | 4 |
| 渐近与半参数 | 3–4 |
| 贝叶斯计算 | 3–4 |
| 因果推断 | 4 |
| 生存与纵向 | 4 |
| 预测与校准 | 4 |
| 时间序列 | 3–4 |
| 高维与组学 | 3–4 |
| 数据工程 | 3 |
| R 软件工程 | 4 |
| 临床试验 | 4 |
| 部署治理 | 3–4 |

每季度用实际作品而非自我感受评分。

---

## 20. 从审稿人到领域方法领导者

### 审稿层

- 识别 estimand 与方法不一致；
- 识别信息泄漏和错误验证；
- 识别渐近近似薄弱；
- 识别 P 值、OR、HR 和变量重要性误释；
- 要求敏感性和可复现性。

### 编辑层

- 制定统计报告最低标准；
- 建立统计审稿专家库；
- 要求代码/数据可用声明；
- 规范 AI/预测论文外部验证；
- 推动 protocol/SAP 注册；
- 处理统计争议和更正。

### 领域领导层

- 组织 benchmark 与共识；
- 建立多中心验证联盟；
- 开放方法软件和模拟框架；
- 培养交叉学科团队；
- 将方法创新转为临床和公共卫生决策改进。

---

## 21. 原创研究问题筛选器

一个值得投入的方法问题应同时满足：

1. 真实医学决策中反复出现；
2. 现有方法的 estimand、假定或验证存在缺口；
3. 可形成清楚的理论或算法贡献；
4. 有可用数据或可可信模拟；
5. 能与强基线公平比较；
6. 可开发软件；
7. 结果具有可迁移性；
8. 失败情形也有科学价值。

避免只做“把某热门模型应用于某数据集”的方法论文。

---

## 22. 学术影响的三层结构

### 层 1：可信分析

每个研究可重现、假定透明、解释不过界。

### 层 2：可复用方法资产

软件、模拟、数据字典、报告模板可被其他团队采用。

### 层 3：改变领域实践

方法或规范进入多中心研究、指南、课程、期刊政策或监管流程。

Top 水平主要体现在第二、三层，而不是单篇论文的模型复杂度。

---

## 23. 持续更新机制

每 6 个月进行一次知识库审计：

- 哪些软件接口过时；
- 哪些方法已有新证据；
- 哪些笔记混淆来源与扩展；
- 哪些模拟尚未覆盖真实失败场景；
- 哪些领域缺少外部验证；
- 哪些方法需要淘汰或降级；
- 哪些公共资产被实际使用。

仓库应记录版本日期和变更理由，而不是只累积文档。

---

## 24. 最终标准

达到本路线的目标，不意味着对所有统计分支无所不知，而是具备以下稳定能力：

1. 面对陌生医学问题，能够首先定义 estimand、数据生成机制和决策，而不是搜索检验名称；
2. 面对复杂估计器，能够追踪其一致性、渐近线性、方差和失败条件；
3. 面对机器学习结果，能够审计信息边界、验证、校准、效用和漂移；
4. 面对贝叶斯模型，能够审查先验、计算、预测检查和操作特征；
5. 面对统计争议，能够用理论、模拟和实证三类证据解决；
6. 能将个人分析能力转化为软件、标准、课程和团队能力；
7. 能够持续产出可被高水平同行复核、复用和扩展的方法学成果。
