# Changelog

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
