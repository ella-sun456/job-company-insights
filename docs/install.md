# 跨平台安装指南 — 一个技能包，让任何 AI 都用它、输出同一版式

> 目标：**国内主流 AI（豆包 / Kimi / MiniMax / 通义 / ChatGPT 等）装上就能用，且输出的报告版式与设定的完全一致。**
> 原理：版式是内联在 HTML 里的标准 CSS/JS，与平台无关；只要 AI 按系统提示词 + 知识库模板输出完整 HTML，浏览器打开就是同一版式。
> 本包已合并为**单一压缩包 `job-company-insights.zip`**，三种通道（桌面端导入 / 编程型 Agent / 聊天型 AI）都用它，无需再区分“导入专用包”。
>
> 本仓库中所有安装物料统一放在 [`install/`](../install) 目录：`job-company-insights.zip`（桌面端导入）、`jd-requirement-decomposition.skill`（原生安装）、`智能体系统提示词.txt` 与 `JD需求拆解-HTML模板-知识库上传版.txt`（聊天型 AI 用）。技能本体则是根目录的 `SKILL.md` + `references/` + `assets/`。

## 包内安装物料（本包已备齐）

| 文件 | 用途 |
|---|---|
| `SKILL.md`（根目录）+ `references/` + `assets/` | **技能本体**，桌面端导入 / 文件夹安装都用它 |
| `jd-requirement-decomposition.skill` | 标准技能包，支持 .skill 的运行时可直接安装 |
| `智能体系统提示词.txt` | **粘贴到智能体"系统提示词/角色设定"栏**（聊天型 AI 用） |
| `JD需求拆解-HTML模板-知识库上传版.txt` | **上传到智能体知识库**（AI 按它原样输出版式） |
| `模板样例Demo-知识库上传版.txt` | 上传到知识库（AI 参考成品效果，可选） |
| `JD需求拆解-技能说明.md` | 也可整份粘贴为提示词（含内联模板，适合提示词上限宽松的平台） |

## 一、桌面端一键导入（WorkBuddy 桌面端等）

**直接导入 `job-company-insights.zip`，无需解压**：SKILL.md 位于压缩包根目录，导入器可直接识别技能。

## 二、编程型 Agent（原生安装 .skill / 技能文件夹，零改动）

解压 `jd-requirement-decomposition.skill`，把其中的 `jd-requirement-decomposition/` 文件夹放进对应目录；
或解压整个 `job-company-insights.zip`，把根目录（含 SKILL.md + references/ + assets/）整体放进对应目录：

| 平台 | 安装目录 |
|---|---|
| CodeBuddy / WorkBuddy | 直接安装 .skill，或 `~/.codebuddy/skills/` |
| Claude Code / Claude 桌面·网页 | `~/.claude/skills/`（桌面端也可设置里上传 zip） |
| OpenAI Codex CLI | `~/.codex/skills/` 或项目 `.codex/skills/` |
| 字节 Trae / TraeWork | `~/.trae/skills/` |
| Cursor 2.4+ | `~/.cursor/skills/` |
| GitHub Copilot | `.github/skills/` |
| Windsurf / Cline / Roo Code / Kiro / Continue / Goose 等 | 各自 `skills/` 目录 |
| 通用 | 项目根 `.agents/skills/` |

安装后说「用 jd-requirement-decomposition 分析这个 JD」即可触发；Codex 也可用 `$jd-requirement-decomposition` 显式调用。

## 三、聊天型 AI（豆包 / Kimi / MiniMax / 通义 / ChatGPT）

通用三步（各平台入口见下）：

1. **创建智能体 / Bot**，简介写：「输入目标岗位 JD 和公司名称，输出双 Tab 高保真 HTML JD 需求拆解全景报告」（触发词对齐）。
2. **系统提示词**：把 `智能体系统提示词.txt` 全文粘贴进去。
   - 若平台提示词上限够大，也可直接粘贴 `JD需求拆解-技能说明.md` 全文。
3. **知识库**：上传 `JD需求拆解-HTML模板-知识库上传版.txt`（建议再传 `模板样例Demo-知识库上传版.txt`），开启知识库检索。
   - 平台只收 PDF/DOCX/MD 不收 TXT 时，把该 .txt 内容另存为 .md 或 .docx 上传。

### 各平台入口

| 平台 | 创建入口 | 知识库支持 |
|---|---|---|
| 豆包 | 网页端 doubao.com 左侧【智能体】→ 创建智能体 | PDF/DOCX/TXT/MD，单库 100MB |
| Kimi | kimi.com/bot → 创建智能体 | PDF/Word/Markdown |
| MiniMax | MiniMax Agent / 智能体 → 创建 | 文件上传 |
| 通义千问 | 通义 APP/网页 → 智能体 → 创建 | 文档上传 |
| ChatGPT | Explore GPTs → Create → Instructions + Knowledge | Instructions 粘贴提示词，Knowledge 上传文件 |

### 使用方式

对智能体发送 JD（截图/链接/文字）+ 公司名称即可。AI 输出完整 HTML 后，**把 HTML 保存为 .html 文件用浏览器打开**（或让 AI 直接给可下载文件），页面上「⤓ 保存 / 下载 HTML」按钮可随时再导出。

## 四、版式一致性保证（两条关键）

1. **AI 必须原样输出模板的 CSS/JS 骨架，只替换占位符**——系统提示词已写死此要求；若某次输出版式走样，回复「按知识库《JD需求拆解-HTML模板》原样输出完整 HTML，不要简化」即可纠正。
2. **下载按钮与双 Tab 是模板自带功能**，只要 AI 没删改模板就一定保留；生成后在浏览器打开，「⤓ 保存 / 下载 HTML」随时可再导出单文件。

## 五、平台兼容性总览（含小红书 / GitHub）

| 平台 | 类型 | 支持方式 | 本包用法 |
|---|---|---|---|
| WorkBuddy 桌面端 | 运行时 | **直接导入 zip** | SKILL.md 在压缩包根目录，一键导入，无需解压 |
| WorkBuddy 网页 / CodeBuddy | 运行时 | .skill / skills/ 目录 | 安装 `jd-requirement-decomposition.skill`，或放 `~/.codebuddy/skills/` |
| GitHub | 代码托管 | 仓库 + Release | 解压后文件夹直接作仓库提交（根目录 SKILL.md 即技能入口）；zip 作 Release 附件，无大小 / 格式限制 |
| 小红书 Red Skill | 内容平台 | **上传知识物料** | 创作者服务平台 → Red Skill：把 `智能体系统提示词.txt` + `JD需求拆解-HTML模板-知识库上传版.txt` + Demo txt 作为素材上传，AI 结构化后可挂载到笔记（注意：Red Skill 吃的是知识物料，不是 .skill 格式） |
| 小红书店铺智能体 | 电商 AI | 知识库上传 | 支持 TXT / MD / HTML / PDF / DOCX 等，单文件 ≤15MB，本包 txt 可直接传 |
| Claude Code / Claude 桌面·网页 | 编程型 | `.claude/skills/` 或设置上传 zip | 原生支持 Agent Skills |
| Codex CLI / Cursor / Trae / Copilot / Windsurf / Cline / Roo / Goose / Kiro / Continue / Gemini CLI / Antigravity 等 68+ Agent | 编程型 | 各自 `skills/` 目录 | Agent Skills 开放标准，SKILL.md 即装即用 |
| 豆包 / Kimi / MiniMax / 通义 / ChatGPT | 聊天型 | 智能体 + 知识库 | 系统提示词 + 知识库 txt（见第三节） |

结论：**GitHub 与全部编程型 Agent 完全兼容；小红书走 Red Skill / 店铺智能体的知识物料路线；聊天型 AI 走智能体 + 知识库路线。** 一个包覆盖所有通道，无需为任何平台单独打包。
