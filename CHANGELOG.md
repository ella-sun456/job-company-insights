# Changelog

## v1.2.0 · 2026-11-06

**变更（下载按钮按新规范重做）**
- 按钮文案统一为 `📥 下载 HTML 报告`（英文报告为 `📥 Download HTML report`），顶部工具栏与右下角浮动按钮各一个
- `downloadHTML()` 精简为纯 Blob + `a[download]`，**删除复制源码弹窗、提示卡与二次确认**，点击直接触发浏览器下载
- 下载文件名固定 `JD分析报告-【岗位名称】.html`，岗位名称从 JD 自动提取并写入模板 `JOB_TITLE`
- 模板、Demo、中英文说明页、两个知识库上传版、智能体提示词全部同步；安装包（`.skill` / `.zip`）同步重建
- `references/html-spec.md` 新增「Download（下载按钮）」规范，含文件命名与禁止项

**说明**
- 在 iframe 沙箱的在线预览里，浏览器会静默拦截下载（平台限制）；把文件下载到本地后双击打开，按钮一律正常

## v1.1.2 · 2026-11-06

**修复**
- 「⤓ 保存 / 下载 HTML」点击无反应：改为延迟 4 秒回收 blob 地址，避免下载刚触发就被 revoke 打断
- 在线预览（iframe 沙箱）里浏览器禁止触发下载：改为弹出可操作面板（复制 HTML 源码 / Ctrl+S 提示），不再「点了没反应」
- 模板、Demo 报告、中英文说明页四处同步该修复

**新增**
- `docs/skill-guide-en.html`：技能说明页完整英文版（8 节全译，含安装、红线、输出规范、工作流、模板规范）
- 中文说明页工具栏加 `EN` 入口；首页「技能说明」按钮随语言指向中/英版本

## v1.1.1 · 2026-11-06

**新增**
- 首页中英双语切换：默认英文，右上角 `EN / 中文` 可切，选择记在本地；标题、卡片、截图说明、命令示例全部双语
- `assets/images/banner-en.png` 英文版封面；首页按语言自动切换首图
- README 改为双语版：英文在上、中文在下
- `docs/skill-guide.html` 顶部新增 English overview（中文详版在下）

**说明**
- 双语页面为纯 CSS + 少量 JS 实现，不引入外部依赖，仍是单文件、离线可开
- 技能说明页的英文块已同步写入 `scripts/build_guide.py`，重新生成不会丢失

## v1.1.0 · 2026-11-06

**新增**
- `index.html` 项目主页：封面 + 流程图 + 6 张真机截图 + 卡片式收益说明，打开即知这是什么
- `docs/skill-guide.html` 技能说明网页版：在对应章节插入流程图与报告截图
- `assets/images/`：封面 banner、四步流程图、6 张报告真机截图
- `demo/report-demo.html`：脱敏示例报告（「星澜宠物」× 用户研究专家岗），双 Tab 可交互
- `install/`：桌面端一键导入 zip、标准 `.skill` 包、聊天型 AI 提示词与知识库模板

**变更**
- 技能名统一为 `job-company-insights`（原 `jd-requirement-decomposition`），SKILL.md、文档、安装包同步更新
- README 重写：先给「点开即看」入口，再讲这是什么、能得到什么、怎么装
- 补充使用说明、参考来源与致谢、版本迭代三节

**说明**
- GitHub 网页不渲染 HTML，README 中提供在线预览与下载两条路径；开启 GitHub Pages 后可永久在线访问

## v1.0.0 · 2026-10-30

**初始版本**
- 技能本体：`SKILL.md`（角色、约束红线、双 Tab 工作流、初始化话术）
- `references/html-spec.md`（CSS 规范 + 逐模块数据 schema）
- `assets/template.html`（可直接运行的单文件骨架）
