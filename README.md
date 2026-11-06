<div align="center">
  <img src="assets/images/banner.png" alt="JD 需求拆解 × 企业深度调研" />
</div>

<h1 align="center">job-company-insights</h1>

<p align="center"><b>一条 JD 进去，一份「岗位 + 公司」全景报告出来。</b><br/>
投递之前，先看清这家公司要什么人、这个岗位解决什么问题、你还差多远。</p>

<p align="center">
  <a href="README.en.md">English</a> · 中文
  &nbsp;|&nbsp;
  <img alt="format" src="https://img.shields.io/badge/SKILL.md-Agent%20Skills-2563eb?style=flat-square" />
  <img alt="output" src="https://img.shields.io/badge/output-single--file%20HTML-10b981?style=flat-square" />
</p>

---

## 点开就看

| 看什么 | 一点就开 |
|---|---|
| 项目主页（双 Tab，可切中/英） | **[▶ 打开主页](https://htmlpreview.github.io/?https://github.com/ella-sun456/job-company-insights/blob/main/index.html)** |
| 完整 Demo 报告（虚构脱敏样例） | **[▶ 打开 Demo](https://htmlpreview.github.io/?https://github.com/ella-sun456/job-company-insights/blob/main/demo/report-demo.html)** |
| 技能说明（原理、模块、安装） | **[▶ 打开说明](https://htmlpreview.github.io/?https://github.com/ella-sun456/job-company-insights/blob/main/docs/skill-guide.html)** |

> GitHub 不渲染 HTML，直接点 `.html` 只会看到源码，这是平台行为。上面三个链接走在线渲染，点一下就是排版好的页面；也可以下载文件双击打开。

## 这是什么

面向求职者的 AI 技能。把目标岗位的 JD 发过来（截图 / 链接 / 文字都行），再给个公司名，它先做真实调研，再输出**单文件、双 Tab 的 HTML 报告**：左边拆岗位与你的匹配度，右边把公司从工商信息讲到商业模式、竞品和隐藏需求。

不是关键词复述，而是把招聘方视角（HR 五问、意图解码、人才画像）和候选人视角（匹配度、差距、面试打法）放进同一份文档。

## 你会得到什么

| 模块 | 你能回答的问题 |
|---|---|
| 资深 HR 五问 + 人才画像卡 | 这个岗位到底在干什么？他们真正想招哪种人？ |
| JD 逐条解码（蓝＝明确 / 黄＝推测） | 每一句要求背后的真实意图是什么？ |
| 百分制匹配度 + Gap 清单（有简历才算） | 四个维度各差多少？两周内补什么？ |
| 公司基本面 + 商业模式 + 竞品 | 它靠什么赚钱？这条业务是主战场还是边缘？ |
| 隐藏需求 + 可反问问题 + 面经 | 会考什么？面试时该反问哪三个问题？ |

## 三条底线

- **防幻觉**：优先一手来源，查不到就写「无法确认」，不编数字。
- **信息分色**：JD 明确标蓝、合理推测标黄，一眼看出哪些能直接说。
- **有简历才打分**：只给 JD 就只拆岗位，不硬凑匹配度。

## 安装

1. **桌面端**：下载 [install/job-company-insights.zip](install/job-company-insights.zip)，直接导入，无需解压。
2. **编程型 Agent**：把 `SKILL.md` + `references/` + `assets/` 放进 `~/.codebuddy/skills/`、`~/.claude/skills/` 等目录，或用 [install/job-company-insights.skill](install/job-company-insights.skill)。
3. **聊天型 AI**：`install/智能体系统提示词.txt` 贴进系统提示词，模板文件传到知识库。

平台入口与排查见 [docs/install.md](docs/install.md)。

**更新**：技能是本地文件副本、不会自更新。到 [Releases](https://github.com/ella-sun456/job-company-insights/releases/latest) 下载最新 zip 重新导入即可覆盖；`git clone` 的用户直接 `git pull`。装的是哪一版看 `SKILL.md` 顶部版本号。

## 用法

```
用 job-company-insights 分析这个 JD：[粘贴 JD 文字 / 截图 / 链接]，公司：某某科技
```

想算匹配度就一起发简历；只发 JD 也行，它会先拆岗位再问你要不要补简历。生成的文件浏览器打开即看，右下角可直接下载。

## 使用说明

1. 企业信息以公开可验证资料为准，无法确认的标「推测 / 待验证」。
2. 分析结果仅供求职参考，不作为投递的唯一依据。
3. 报告为单文件，下载后离线可读。
4. Demo 中「星澜宠物」为化名，数据均为演示虚构，版式与真实输出一致。
5. 版式走样时对它说：按知识库模板原样输出完整 HTML，不要简化。

## 致谢与版本

本项目在学习公开分享的 AI Skill 写法、岗位分析方法与企业调研案例的基础上整理实践而成；部分早期参考暂无法确认原作者与链接，核实后持续补充（欢迎提 Issue，我立刻补上）。

版本记录见 [CHANGELOG.md](CHANGELOG.md)，当前 **v1.1.2**。
