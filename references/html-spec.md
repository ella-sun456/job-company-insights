# HTML & CSS Design Specification

Mandatory spec for every generated report. Copy the structure and class names
verbatim from `assets/template.html`; only fill content. No external dependencies
(no CDN, no web fonts, no external images — embed JD screenshot as base64 (if provided); for JD link embed the URL, for JD text embed the quoted text).

> **Real-data rule.** Every placeholder in the template must be replaced with
> real, sourced content. If a fact cannot be verified, write 「无法确认」or
> 「公开信息未披露」— never fabricate numbers, funding, or founder biographies.

## Global

- Background `#f4f7f9`; system sans-serif stack.
- Header gradient `linear-gradient(135deg, #f8fafc, #e2e8f0)`.
- Card: white bg, `border-radius:12px`, light shadow, `1px solid #e2e8f0`.
- Two tabs switched by JS `switchTab(event, id)`: labels 「JD 透视与匹配」「深度调研看板」. No leading numbers, no parentheses in labels.
- Header 含 4 个数据卡片：`公司阶段` / `核心赛道` / `综合匹配度` / `风险等级`。**`综合匹配度` 用百分制**（如 `82/100`），遵循「有简历才打分」规则：
  - **JD + 简历都上传** → 直接输出百分制总分；并在「逐条匹配分析」下方渲染 **📊 综合匹配度维度拆解**（`经验 / 技能 / 行业认知 / 岗位层级` 四维度各给分，权重合计 100），列适配点（绿框）与差距点（红框）；不反问。
  - **只有 JD、没有简历** → 卡片显示「待评估」，不做任何匹配度评分；涉及个人对比的维度拆解/简历依据列/适配差距点统一标 `待补充` / `待评估`；系统先用大白话反问是否补简历（见 SKILL.md 约束 7）。

## Language（报告语言）

报告语言 = 用户提问语言（英文提问 → 全英文报告；中文提问 → 中文报告）；用户显式要求时以要求为准；无法判断时以 JD 原文语言为准。**除专有名词/公司名/文件路径外不混排。**

英文报告时，模块标题按下表替换（其余版式、颜色、结构完全一致）：

| 中文标题 | English title |
|---|---|
| JD 需求拆解全景报告 | JD & Company Insight Report |
| JD 透视与匹配 | JD Decoding & Fit |
| 深度调研看板 | Company Research Dashboard |
| JD 原文与来源 | JD Text & Source |
| 资深 HR 视角五问 | Five Questions a Senior HR Would Ask |
| 目标人才画像 | Target Persona |
| JD 逐条解码 | Line-by-line JD Decode |
| 逐条匹配分析 | Requirement-by-requirement Fit |
| 综合匹配度维度拆解 | Fit Score Breakdown |
| 适配点 / 差距点 | Strengths / Gaps |
| 定制自我介绍 | Tailored Self-intro |
| 公司基本面 | Company Fundamentals |
| 创始人画像 | Founder Profile |
| 商业模式 | Business Model |
| 产品与业务线 | Products & Business Lines |
| 竞品矩阵 | Competitor Matrix |
| 隐藏需求与岗位差异 | Unstated Needs & Role Variance |
| 结论建议 | Verdict |
| ⤓ 保存 / 下载 HTML | ⤓ Save / download HTML |
| 待补充 / 待评估 | To be added / Not assessed |
| 事实·工商 / 推测 | Fact · registry / Inference |

## Title

`<h1>` = `【公司名称】 - 【岗位名称】JD 需求拆解全景报告`. No serial numbers, no `()`/`（）`.

## Color tokens (CSS variables)

```
--bg:#f4f7f9; --card:#fff; --ink:#0f172a; --muted:#64748b; --border:#e2e8f0;
--blue:#3b82f6;  --blue-light:#eff6ff;
--yellow:#f59e0b;--yellow-light:#fffbeb;
--green:#10b981; --green-light:#ecfdf5;
--red:#ef4444;   --red-light:#fef2f2; --radius:12px;
```

## Highlight Boxes

| Purpose | Class | Background | Border-left |
|---|---|---|---|
| 成功 / 结论 | `.hl-green` | `#ecfdf5` | `4px solid #10b981` |
| 警告 / 策略 | `.hl-yellow` | `#fffbeb` | `4px solid #f59e0b` |
| 风险 / 大客户依赖 | `.hl-red` | `#fef2f2` | `4px solid #ef4444` |
| HR判断 / 反问 | `.hl-blue` | `#eff6ff` | `4px solid #3b82f6` |

## Tag Badges（信息分离）

- `.tag.jd` / `.tag.fact` → blue (`#dbeafe`/`#1e40af`) = JD 明确 / 事实·工商
- `.tag.infer` / `.tag.infer2` → yellow (`#fef3c7`/`#92400e`) = 合理推测

## Tables — `.matrix-table`

`border-collapse:collapse`; `th` bg `#f8fafc` centered; each `td` has
`border-right:1px solid #e2e8f0` except the last column. `tr:hover` tint.

## Tab 1 — JD 透视与匹配

1. **JD 原文与来源 + HR五问 双排**：外层 `.grid-2` 包两个 `.card`——左卡为「JD 原文与来源」：顶部 `.jd-source-bar` 标注来源方式（截图/链接/文字），下方按实际保留一种来源区块（`.jd-img` 内 `.jd-shot` 放 base64 img 可点击放大；`.jd-link` 内 `.jd-link-box` 放可点击链接；`.jd-label`+`.jd-quote` 放 JD 文字引用）；右卡 HR 五问：`.hr-block` ×4。左卡 `.jd-shot`（img `onclick="zoomJD(this)"`，base64 内嵌；无图则虚线占位），右卡 HR 五问（`.hr-block` ×4：白话解读 / 职责能力特质带 tag / 协作图 `.role-map` / 真实案例三方向）。
2. **HR 终局判断**：`.hr-block` 蓝左边框，写清真正想要的人画像。
3. **JD 深度解码：他们到底要什么人**：1 句话 archetype + `.grid-2` 两栏「🔧 硬门槛 / 🧠 软特质」+ 下方 `.chips` 列核心特质与隐藏期待。
4. **JD 逐条拆解**：`.matrix-table` 列 `原文摘句 / 类型(硬性·软性·加分) / 解码：他到底要什么 / 标注(蓝 JD明确·黄 合理推测)`。
5. **逐条匹配分析 简历 vs JD**：`.matrix-table` 列 `JD 要求/简历依据/匹配度/gap·风险/面试具体策略`；表下新增 **📊 综合匹配度维度拆解**（`经验/技能/行业认知/岗位层级` 四维度各给分，权重合计 100，附适配点绿框 + 差距点红框）。**无简历时**：简历依据列留【待填】、维度拆解标「待补充」、综合匹配度卡标「待评估」，不强行打分。
6. **定制自我介绍**：`.intro-box`，≤250 字填空。
7. **Gap 清单**：`.gap.gap-red/.gap-yellow/.gap-green`，带 `<input type=checkbox>`。
8. **面经总结、真题预测与面试行动指南**（单卡 5 子块）：📚 面经总结与真题预测（平台/关键词 + 高频真题信号）· ✅ 面试前准备清单（checkbox）· 🌙 面试前 1 天必做 · 🎯 面试中关键原则（`.chips`）· 🎒 面试当天的准备。

## Tab 2 — 深度调研看板

- 1. **公司基本面** → `.info-grid`（全称&成立/赛道&背景/模式/人员规模），工商项标 `事实·工商`；同一 card 内下方追加「🎯 近期重点方向（推测）」子块：业务/市场/组织 列表 + `.hl-yellow` 与岗位匹配度。生命周期/融资/营收等可并入 info-grid 子注（如「资方：未披露」「生命周期：推测」），不再单列卡片。
- 2. **创始人画像** → full-width card：姓名行（事实+推测标签）+ 内部 `.grid-2` 两列——🧭 背景与旅程（`.ftl` 蓝/绿点时间轴）、⚡ 关键转折·低谷与逆袭（`.ftl` 黄/绿/红点，`red` 点承接「无法确认→面试反问素材」）；下方 🧠 经营哲学用 `.chips`（蓝/绿 chip）+ 两个 `.mini-stat`（最大杠杆点 / 待验证）。**禁止大段文字罗列**；无法确认项如实标注。
- 3. **商业模式** → `.grid-2` 两卡：盈利逻辑 | 大客户依赖风险（高则 `.hl-red`）。
- 4. **产品与业务线** → `.matrix-table`：核心/主力/利润/引流（每行列一句简注，禁止 rowspan）；表下 `.hl-blue` 写「岗位业务线地位」。再追加「📌 主推产品」**数据驱动**占位（均有【待填】注入点，尾部 `.sub-text` 注明「数据驱动：接入真实销售数据后自动替换」）：
  - 📌 **主推产品**（当前重点销售&推广）：产品/品类/场景 · 主推定位与打法 · 渠道 · 核心卖点。示例数字用 `【示例 …】` 包裹并标「示意·待真实数据」，不得伪造成事实。
  - **分类维度不写死电商口径**（引流/利润/形象款等），优先按实际品类/功能/用户类型/使用场景/价格带；多子品牌按子品牌分组；无某项可整段省略。
- 5. **竞品分析** → `.matrix-table`：直接/间接/潜在威胁 的优劣势。
- 6. **隐藏需求与岗位差异** → `.hl-blue`（真实痛点反推/同行差异/未写明看重）+ `.hl-yellow`（面试可反问问题）。
- 7. **结论建议** → `.hl-green`：三句话总结 + 机会/风险两栏 + 面试展示重点虚线框。

## JD 原文与来源（截图 / 链接 / 文字）

- **截图**：用户提供截图 → embed `<img src="data:image/png;base64,...">`（single-file, no external dep）, `onclick="zoomJD(this)"` opens `.lightbox`；无截图则 `.jd-shot` 虚线占位 + 文字提示。
- **链接**：用户提供 JD 链接 → 在 `.jd-link-box` 内放可点击的 `<a href="URL" target="_blank" rel="noopener">`，新标签页打开原始 JD。
- **文字**：用户直接粘贴 JD 文本 → 在 `.jd-quote` 引用块内展示 JD 原文全文。
- 卡片顶部 `.jd-source-bar` 必须标注实际来源方式（截图 / 链接 / 文字），且仅保留用户实际提供的那一种来源区块，其余两种占位整段删除。

## CSS Collaboration Diagram — `.role-map`

flexbox boxes + arrow connectors (no images): `.role-node` (`.self` for 本岗位) + `.role-arrow`. Wrap in `.grid-2` with JD card for the left-right layout.

## Founder Timeline — `.ftl`

`ul.ftl > li.ftl-item` with `.ftl-dot.blue|green|yellow|red` (color = status/来源), `.ftl-title`, `.ftl-sub`. Keeps info density low vs prose.

## Responsive

`@media(max-width:768px)` → `.grid-2/.info-grid/.role-map/.scorecard` collapse to 1 column; `.role-arrow` rotate 90°.
