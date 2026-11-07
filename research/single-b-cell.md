# 单 B 细胞与重组 IgM 验证方案

此路线为后续实验设计。先在对照样本完成培养和质量验证，再决定候选克隆的功能复测。

## 2. 两条主培养路线与可选路线的最小比较矩阵

| 维度 | Route 1：R848 + IL-2 | Route 2：CD40L + IL-2 + IL-21 feeder | Route 3：EBV + CpG expand-then-secrete |
|---|---|---|---|
| 主要文献 | Pinna 2009；Conde 2026/预印本；Vásquez 2015 | Whaley 2020；Ettinger 2005 | Traggiai 2004/2012 |
| 设计目的 | 短周期选择性激活 memory B cell | strict single-cell 存活、扩增与分泌 | 长期保留与二次扩增 |
| 单细胞证据 | IgG+ memory B cell 极限稀释；新平台有 SCC | 明确 1 cell/well | 1/5/25 cells/well 方法学；永生化 |
| IgM 直接性 | bulk/同型观察较强；严格单 IgM 定量不足 | 定量主要 IgG；IgM 待验证 | 可产生人 mAb；IgM 同型保持待验证 |
| 预实验刺激条件 | 文献起点：R848 `2.5 μg/mL` + IL-2 `1,000 U/mL`；Conde 预印本为候选变体 | 文献 feeder 起点：`87,500 live cells/cm²`；照射 `5,000 rad`；13 d | 文献 protocol：CpG `2.5 μg/mL`、50 μL、384 孔、照射 PBMC |
| 主 readout | responder rate、total IgM、同型保持、binding | responder rate、total IgM、存活/扩增、BCR 回收 | 长期复苏、分泌稳定性、功能漂移 |
| 主要优势 | 轻量、短周期、少刺激物 | strict single-cell 和身份闭环最成熟 | 可留活克隆、便于二次产量放大 |
| 主要风险 | 自体 feeder 背景；IgG 证据多于 IgM | CD40 信号可能促同型转换/偏倚 | EBV 选择偏倚、表型漂移和生物安全 |
| Phase 1 go | responder 孔比例、total IgM 与 BCR 回收达到预注册阈值 | 同左，且同型保持不劣于 Route 1 | 仅在需要长期扩增且漂移可接受时启用 |

说明：

- 文献值只用于决定比较范围，不能直接成为本地 SOP。
- “预注册阈值”在首轮小规模 pilot 后由实验团队锁定；本任务不伪造数值。
- 两条主路线应使用同一 donor、同一 sort gate、随机分配和同批 readout，以免把 donor effect 误作培养路线差异。

## 3. Master/daughter plate 闭环

```text
FACS 单细胞分选
  ↓ sort index + plate/well ID
Master plate（活细胞/克隆身份）
  ├─ 定时取样 → Daughter A：total IgM
  ├─ 定时取样 → Daughter B：PS-only / PT-only / PS/PT binding
  ├─ 候选上清 → Daughter C：低体积功能中间层
  ├─ 少量候选 → Daughter D：TGA
  └─ 阳性/边界孔 → 复苏扩增或同孔 lysis → paired BCR
                                  ↓
                           重组多聚 IgM
                                  ↓
                    binding + 功能独立批次复现
```

最小追踪字段：

- donor、sample、分选日期、细胞亚群、sort index；
- master plate/well、培养路线、feeder lot、培养日；
- 每次 daughter 转移的目的、体积、冻存位置和剩余体积；
- total IgM、binding、功能结果及原始数据路径；
- paired VH/VL、测序质控、表达批次、聚合态 QC；
- 排除原因与是否进入漏筛抽样。

## 4. 漏斗筛选与每一关的 go/no-go

### Gate 0：单细胞身份与培养完整性

| 项目 | 内容 |
|---|---|
| 输入 | 单个可追溯 B cell + 指定 feeder/刺激 |
| readout | sort index、单细胞概率、master 孔状态、污染/蒸发 |
| go | 身份映射完整；无交叉污染；细胞/克隆可继续追踪 |
| no-go | 多细胞事件、孔位映射丢失、污染 |
| 对照 | 空分选孔、feeder-only、荧光补偿/索引质控 |
| 失败解释 | 分选双ts、边缘孔蒸发、feeder 过度生长 |

### Gate 1：total IgM

| 项目 | 内容 |
|---|---|
| 输入 | daughter A 上清 |
| readout | total IgM 浓度；重复测定 |
| go | 高于本地 LLOQ 且复孔一致；足够完成 binding panel |
| no-go | 低于 LOD；只在单次测量接近阈值 |
| 对照 | 标准曲线、matched medium、mock well、健康 IgM |
| 失败解释 | 非 responder、分泌时间不合适、assay matrix interference |

说明：Gate 1 阴性孔保留预设比例做延迟取样或敏感方法复测，用于估计漏筛。

### Gate 2：binding specificity

| 项目 | 内容 |
|---|---|
| 输入 | total IgM 阳性上清，按原孔或 IgM 等量 |
| readout | PS/PT、PT-only、PS-only、无抗原；必要时竞争/稀释 |
| go | PS/PT 信号在复孔成立，并能与 PT-only/PS-only/背景区分 |
| no-go | 仅黏板、仅 PS-only、所有抗原均阳性或无剂量关系 |
| 对照 | 无关 IgM、健康/APS disease control、secondary-only |
| 失败解释 | polyreactivity、IgM 聚集、bait 呈递错误、PS 密度/构象问题 |

PS/PT bait 最终形式必须等待 APS-LE-0006；本文件只规定比较矩阵。

### Gate 3：低体积功能中间层

| 项目 | 内容 |
|---|---|
| 输入 | 复核后的 binding-positive 上清；同时保留少量 binding-negative matched controls |
| readout | 96 孔显色 TG/prothrombinase 或 FXa/FVa/PL-dependent readout |
| go | 在 matched medium、IgM 等量和剂量梯度下可重复改变 readout |
| no-go | 只在未归一化原上清出现；buffer exchange 后消失；mock 同方向 |
| 对照 | matched medium、mock、buffer-exchange blank、健康/疾病 IgM、无关 IgM |
| 失败解释 | cytokine/盐/pH、内毒素、聚集体、非 IgM 蛋白、底物干扰 |

Gate 3 不能自动称为 aPS/PT-specific；它只决定是否值得进入 TGA。

### Gate 4：TGA 候选确认

| 项目 | 内容 |
|---|---|
| 输入 | 少量候选上清浓缩物或初步纯化 IgM |
| readout | lag time、time to peak、peak、ETP；方向允许上升或下降 |
| go | 至少两个独立制备/重复中有剂量关系；matched controls 阴性 |
| no-go | 单点、单次、只在一种异常基质条件成立 |
| 对照 | 健康/疾病 IgM、无关 IgM、medium/mock、PL/TF 条件、必要时 TM/APC |
| 失败解释 | 平台条件依赖、非单调真实效应、聚集/内毒素、抗凝物污染 |

### Gate 5：IgM depletion/add-back 与 paired BCR

| 项目 | 内容 |
|---|---|
| 输入 | Gate 4 候选、原上清/纯化物、同孔细胞或裂解物 |
| readout | IgM depletion 前后功能；纯化 IgM 回补；paired VH/VL |
| go | 去除 IgM 后效应下降，等量回补恢复；paired BCR 通过序列 QC |
| no-go | depletion 不改变功能；回补不恢复；只回收到单链或污染序列 |
| 对照 | mock depletion、同流程 buffer blank、IgG fraction、无关 IgM |
| 失败解释 | depletion 非特异、IgM 失活、功能来自其他上清成分 |

### Gate 6：重组多聚 IgM 复现

| 项目 | 内容 |
|---|---|
| 输入 | 通过 QC 的 paired VH/VL |
| readout | μ constant + secretory tailpiece + J-chain expression；聚合态；binding；TGA/中间 readout |
| go | 两个独立批次的多聚 IgM 经 QC 后复现 specificity 与功能方向 |
| no-go | 只有 IgG1 桥接 binding；IgM 聚集/异质；功能不复现 |
| 对照 | 同 variable region IgG1、无关多聚 IgM、健康/疾病 control clone |
| 失败解释 | 原上清伪影、变量区不充分、聚合态/糖基化/宿主差异 |

Gate 6 允许表述“该重组多聚 IgM 在体外复现当前 assay 的 binding/功能”；仍不能称体内致病或保护。

## 5. 样本、细胞与上清预算

当前不填伪造数值，所有预算分成两类：

| 预算项 | 文献值 | 本地状态 |
|---|---|---|
| 单细胞培养孔体积 | Traggiai protocol 50 μL；Whaley 使用半面积 96 孔；其余体系不同 | `平台预实验待定` |
| 培养时长 | 6–7 d、10 d、13 d、长期 EBV 路线均有文献先例 | `路线比较后确定` |
| total IgM assay 体积 | 各论文 assay 不同 | `平台预实验待定` |
| PS/PT binding panel 体积 | 受 bait format 和板型影响 | `APS-LE-0006 + 平台预实验待定` |
| 显色 prothrombinase/TG | Sakai 约 120 μL；Sheng 175 μL | `本地缩微/基质验证待定` |
| TGA 单条件/复孔体积 | 平台与 trigger 不同 | `凝血平台咨询待定` |
| paired BCR 输入 | Tiller/Whaley 有单细胞裂解先例 | `本地 RT-PCR/测序平台待定` |
| 重组 IgM 产量 | PER.C6/HEK/CHO 有文献值，不能外推到本地 transient run | `表达平台预实验待定` |

预算原则：

1. 先锁定每孔最小必要的 total IgM + binding panel，再决定培养体积。
2. 原始上清不承诺覆盖 TGA；只把候选孔送入二次扩增/浓缩。
3. 每一步至少保留一个未解冻备份或等价 identity backup。
4. Case LX 运行前，用“预期最低 responder rate × 漏斗通过率”做情景预算，不把健康/病毒抗体文献的高 responder rate 直接代入。

## 6. 功能实验统一控制清单

- matched medium 与 mock well；
- 相同 feeder lot、培养时长和转移次数；
- buffer exchange/浓缩空白；
- total IgM 定量并按质量归一化；
- 原孔体积结果与 IgM 等量结果分开报告；
- 至少三个剂量点；
- IgM depletion、mock depletion、同孔 IgM 回补；
- 健康 IgM、APS disease-control IgM、无关 recombinant IgM；
- TG 升高和降低均保留；
- endotoxin、聚集、pH、盐、冻融和蛋白回收率；
- PS-only、PT-only、PS/PT、无关抗原；
- 至少两个独立表达/纯化批次；
- 不以 PL rescue 单独证明膜不足、竞争稀释或构象改变。

## 7. 重组多聚 IgM 的最小放行标准

1. paired VH/VL 无明显 PCR artifact；异常双 light chain 独立处理。
2. 表达构建含 human μ constant region、secretory tailpiece 与 J chain。
3. 记录表达宿主、转染批次、培养/收获时间和纯化流程。
4. SEC 或 SEC-MALS/等效方法确认 pentamer/hexamer、monomer/aggregate 分布。
5. 非还原电泳；必要时还原电泳确认链组成。
6. 蛋白浓度、纯度、回收率、内毒素、pH、盐、冻融稳定性。
7. 糖基化至少按 host/batch 记录；有功能差异时升级 glycan analysis。
8. 两个独立批次复现 binding 与功能。
9. 同 variable region IgG1 仅用于桥接“变量区是否能结合”，不能替代 IgM 放行。

