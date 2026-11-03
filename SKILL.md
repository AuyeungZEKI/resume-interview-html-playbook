---
name: resume-interview-html-playbook
version: 1.0.0
description: This skill should be used to prepare for or review a job interview from a candidate resume and a JD / JD screenshot / interview transcript, producing a single-file offline HTML document from a fixed magazine-style template. Prep mode builds a tailored interview playbook (JD match, resume defensibility map, Q&A, case, interviewer questions); review mode turns a transcript or feedback into failure diagnosis, repair rules, rewritten answers, and next-round predictions. Triggers include 面试准备, 面试手册, 准备一面/二面/主管面/HR面, 模拟面试题, 根据简历和JD准备面试, 面试复盘, 面后复盘, 面试逐字稿分析, 面试反馈, 下一轮怎么准备, interview prep, interview review. Never invents metrics absent from the resume.
display_name: 简历面试手册
display_name_en: Resume Interview Playbook
description_zh: 上传简历 + JD（或截图），生成定制面试手册：JD 匹配矩阵、简历追问防守地图、自我介绍、高频问答、场景案例、反问清单；面试后提供逐字稿或反馈，生成复盘：失分诊断、修复规则、回答重写、下一轮预测。单文件离线 HTML，杂志风固定模板，不编造简历里没有的数据。
description_en: Resume interview playbook & post-interview review
disable: false
agent_created: true
author: zekiouyang
repository: https://github.com/AuyeungZEKI/resume-interview-html-playbook
---

# 简历面试手册 · Resume Interview Playbook

> 作者：zekiouyang · GitHub：https://github.com/AuyeungZEKI/resume-interview-html-playbook

## Modes
| Mode | Trigger | Required input | Output file |
|---|---|---|---|
| **Prep 面前手册** | 准备面试 / 面试手册 / 模拟题 | Resume + JD (text or screenshot); optional prior-round feedback | `面试手册.html` |
| **Review 面后复盘** | 面试复盘 / 逐字稿 / 面试反馈 / 下一轮怎么准备 | Transcript, recalled Q&A, or feedback; resume | `面试复盘.html` |

If the request mentions a finished interview, use Review. If both are wanted (复盘后准备下一轮), run Review first, then Prep with the repair rules fed into `#prior`.

## Workspace & file locations (mandatory)
`ROOT = <current workspace>/interview_prep/` by default. If the user names a different folder, use it as ROOT and keep using it for later rounds of the same job search.

| Path | Purpose |
|---|---|
| `ROOT/inputs/<公司>_<岗位>/` | Copies of every input: resume, JD, screenshots, transcripts, feedback. |
| `ROOT/outputs/<公司>_<岗位>_<YYYYMMDD>/` | Deliverable HTML plus intermediate notes. |

- `mkdir -p` the folders first; unknown company/role → `未知公司` / `未知岗位`.
- Copy inputs, never move, modify, or delete the user's originals.
- If a folder for the same company and role exists, read its latest HTML first and reuse verified facts; write into a new dated folder, never overwrite.
- Never write deliverables into the invoking workspace root, Desktop, or Downloads.

## Bundled resources
- `assets/template.html` — the only allowed layout. Copy it, fill `{{placeholders}}`, duplicate `<!-- REPEAT -->` blocks, delete sections of the other mode (`data-mode`) and their TOC links, delete OPTIONAL sections without content, then remove the instruction comment at the top. Do not alter the `<style>` tokens.
- `references/answer-rules.md` — evidence tagging, answer structures, round emphasis, defensibility map, pitfalls. Load before drafting any answer.
- `references/review-mode.md` — full Review workflow and failure taxonomy. Load in Review mode.

## Prep workflow
1. Extract confirmed resume facts only (see `answer-rules.md` §1).
2. Parse the JD into responsibility → capability statements; keep job requirements separate from inferred assessment criteria.
3. Build the match matrix: JD item → resume evidence → role translation → gap and honest bridging narrative.
4. Identify the round and its emphasis (`answer-rules.md` §3); convert prior-round feedback into repair rules.
5. Build the resume defensibility map (`answer-rules.md` §4).
6. Draft interview flow, 60–90 s intro, ≥8 tailored Q&As, one scenario case, interviewer questions, and pre-interview checklist using `answer-rules.md` §2.
7. Fill `assets/template.html` (prep sections) and save to `ROOT/outputs/<公司>_<岗位>_<YYYYMMDD>/面试手册.html`.

## Review workflow
Follow `references/review-mode.md`; save to `.../面试复盘.html`.

## Verification
- Every named result traces to the supplied resume or is marked `待补` / `推断`.
- Every prominent number, award, superlative, and broad ownership claim has a follow-up chain and attribution note.
- Layout comes from `assets/template.html`; no leftover `{{` placeholders, `<!-- REPEAT` markers, other-mode sections, or the top instruction comment (`grep -c '{{\|REPEAT\|data-mode="review"'` for prep, swap mode for review).
- Single offline file: no external fonts, scripts, or images.
- No version labels (V1/V2), change notes, revision history, or remarks addressed to the user.
- Prep includes JD match, flow, intro, ≥8 Q&As, case, interviewer questions, checklist. Review includes replay, diagnosis, repair rules, rewrites, next-round predictions, study list.
- Files saved under `ROOT/inputs/` and `ROOT/outputs/`; present the final HTML.
