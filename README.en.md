<div align="center">
  <img src="assets/images/banner-en.png" alt="JD Decoder × Deep Company Research" />
</div>

<h1 align="center">job-company-insights</h1>

<p align="center"><b>One JD in. A full “role + company” report out.</b><br/>
Before you apply, see who they really want, what the role solves, and how far you are from it.</p>

<p align="center">
  English · <a href="README.md">中文</a>
  &nbsp;|&nbsp;
  <img alt="format" src="https://img.shields.io/badge/SKILL.md-Agent%20Skills-2563eb?style=flat-square" />
  <img alt="output" src="https://img.shields.io/badge/output-single--file%20HTML-10b981?style=flat-square" />
</p>

---

## Open it in one click

| What | One click |
|---|---|
| Homepage (EN / 中文 switch) | **[▶ Open homepage](https://htmlpreview.github.io/?https://github.com/ella-sun456/job-company-insights/blob/main/index.html)** |
| Full demo report (redacted sample) | **[▶ Open demo](https://htmlpreview.github.io/?https://github.com/ella-sun456/job-company-insights/blob/main/demo/report-demo.html)** |
| Skill guide (principles, modules, install) | **[▶ Open guide](https://htmlpreview.github.io/?https://github.com/ella-sun456/job-company-insights/blob/main/docs/skill-guide-en.html)** |

> GitHub does not render HTML — clicking a `.html` file shows raw source. That is platform behaviour. The links above go through an online renderer and open the formatted page directly; you can also download the files and open them locally.

## What it is

An AI skill for job seekers. Send the target JD (screenshot, link or plain text) plus a company name. It researches first, then returns a **single-file, two-tab HTML report**: the left tab decodes the role and your fit, the right tab covers the company from registration data through business model, competitors and unstated needs.

Not keyword parroting — recruiter view (five HR questions, intent decoding, target persona) and candidate view (fit score, gaps, interview strategy) live in the same document.

## What you get

| Module | The question you can answer |
|---|---|
| Five HR questions + persona card | What is this role really doing? Which type of person are they hiring? |
| JD line-by-line decode (blue = stated / yellow = inferred) | What sits behind each requirement? |
| 100-point fit + gap list (only with a résumé) | How far off on each of the four dimensions? What to fix within two weeks? |
| Company fundamentals, model, competitors | How does it make money? Main battlefield or side project? |
| Unstated needs + questions to ask back + interview intel | What gets tested? Which three questions should I ask? |

## What the report looks like

Real report screenshots (the demo company is a fictional alias; layout matches the real output exactly):

<table>
  <tr>
    <td align="center" width="50%"><b>① Header · four overview cards</b><br/><img src="assets/images/preview-01-overview.png" width="100%" alt="Header"/></td>
    <td align="center" width="50%"><b>② JD text + five HR questions</b><br/><img src="assets/images/preview-02-jd-hr.png" width="100%" alt="JD + HR"/></td>
  </tr>
  <tr>
    <td align="center"><b>③ Target persona card</b><br/><img src="assets/images/preview-03-persona.png" width="100%" alt="Persona"/></td>
    <td align="center"><b>④ JD line-by-line decode (blue = stated / yellow = inferred)</b><br/><img src="assets/images/preview-04-table.png" width="100%" alt="Decode"/></td>
  </tr>
  <tr>
    <td align="center"><b>⑤ 100-point fit · four-dimension breakdown</b><br/><img src="assets/images/preview-05-match.png" width="100%" alt="Fit"/></td>
    <td align="center"><b>⑥ Company research dashboard (right tab)</b><br/><img src="assets/images/preview-06-company.png" width="100%" alt="Dashboard"/></td>
  </tr>
</table>

> For the interactive experience (tab switching, image zoom, the download button), open the demo link in the "Open it in one click" table above.

## Three rules it never breaks

- **Anti-hallucination**: primary sources first; when something can't be verified it says "unconfirmed" instead of inventing numbers.
- **Colour-coded confidence**: stated in the JD = blue, reasonable inference = yellow, so you know what is safe to say out loud.
- **No score without a résumé**: with only a JD it decodes the role and asks whether to add a résumé.

## Install

1. **Desktop app**: download [install/job-company-insights.zip](install/job-company-insights.zip) and import it — no unzip needed.
2. **Coding agents**: copy `SKILL.md` + `references/` + `assets/` into `~/.codebuddy/skills/`, `~/.claude/skills/` etc., or use [install/job-company-insights.skill](install/job-company-insights.skill).
3. **Chat AIs**: paste `install/智能体系统提示词.txt` into the system prompt and upload the template file to the knowledge base.

Platform entry points and troubleshooting: [docs/install.md](docs/install.md).

**Updating**: the skill is a local copy and never self-updates. Grab the latest zip from [Releases](https://github.com/ella-sun456/job-company-insights/releases/latest) and import it again to overwrite; `git clone` users can simply `git pull`. The version is printed at the top of `SKILL.md`.

**How to verify it installed**: in a fresh chat, say "Use job-company-insights to analyze this JD: …" — if the AI starts decoding the role and produces the report, it is installed.

**Distribution**: the skill is platform-agnostic — grab it from GitHub or import via any link shared on channels like Xiaohongshu; the archive imports directly into any AI tool that supports skill packages (WorkBuddy, Claude, MiniMax Code, Trae, etc.), no per-platform adaptation needed.

## How to use it (what to send → what happens)

One-liner template:

```
Use job-company-insights to analyze this JD: [paste JD text / screenshot / link], company: Acme Tech
```

The JD can arrive as a **screenshot**, a **link**, or **plain text** — any one form works. Sending it immediately triggers company research; no extra command needed. The company name is optional: it is extracted from the JD first and asked for only if undetectable.

| What you send | What happens |
|---|---|
| **JD only** | Company research and role decoding start immediately (requirements / thresholds / what gets tested); since no résumé arrived, it asks in plain words whether to add one |
| **JD + résumé** | No questions — full decode plus the **100-point fit score**: experience / skills / industry insight / seniority scored separately, with strengths, gaps and a to-do list |
| **JD + company name** | Role decode + the **company research dashboard**: fundamentals / business model / competitors / unstated needs / questions to ask back |
| **JD + résumé + company name** | The **full report**: left tab "JD decoding & fit", right tab "company research dashboard" |
| **Résumé sent after the report** | Automatically upgraded to the full scored report |
| **Language specified** (e.g. "report in English") | Language follows your instruction; otherwise auto-detected from the JD — Chinese JD → Chinese report, English JD → English report |

The generated report opens in any browser; the bottom-right button downloads the single-file HTML report directly, fully offline-readable.

## Notes

1. Company information relies on publicly verifiable sources; anything unverifiable is marked "inferred" or "unconfirmed".
2. Analysis is for job-search reference only, not the sole basis for an application decision.
3. Reports are single files and readable offline once downloaded.
4. In the demo, "Starlan Pets" is a pseudonym and all figures are fictional; the layout matches real output.
5. If the layout degrades, tell it: output the full HTML exactly as the template, do not simplify.

## Credits & versioning

This project grew out of studying publicly shared AI-skill patterns, job-analysis methods and company-research case studies. Some early references can no longer be traced to their authors or links; they will be added as they are verified — open an issue and it will be credited immediately.

Release history: [CHANGELOG.md](CHANGELOG.md). Current version **v1.2.4**.
