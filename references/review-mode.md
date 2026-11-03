# Review mode (面后复盘)

Use after an interview when the user supplies a transcript, recording transcription, recalled Q&A, or interviewer feedback.

## Inputs
- Required: transcript / recalled question list / feedback (any one).
- Strongly preferred: the prep playbook for the same company and role under `ROOT/outputs/<公司>_<岗位>_*/面试手册.html` — read it first to compare planned vs actual answers.
- If only audio is available, transcribe it first (speaker separation on), then save the text into `ROOT/inputs/<公司>_<岗位>/`.

## Steps
1. **Replay** — Rebuild the timeline: each interviewer question, the candidate's key points, interviewer reaction or follow-up. Rate each item 稳 / 弱 / 失分 (`.score.hi/.mid/.lo`). Rate by content (structure, evidence, attribution, business judgment), not by tone.
2. **Diagnose** — Classify every 弱/失分 item into exactly one category:
   | Category | Signal |
   |---|---|
   | 结构缺失 | 没有先给结论；动作和结果混在一起 |
   | 证据不足 | 有观点但没有数字、案例或产出物 |
   | 归因不清 | 团队成果说成个人，或被追问边界时说不清 |
   | 业务理解浅 | 对平台/用户/闭环的描述停在表层 |
   | 能力缺口 | JD 硬要求确实不具备（如 SQL、PRD） |
   | 动机模糊 | 说不清为什么是这家、这个岗位 |
   Separate "没说清楚"（可通过表达修复）from "确实没有"（需要补课或诚实补位）.
3. **Repair rules** — One executable rule per failure point, in the form「当被问到 X 时，先说 Y，再用 Z 证明」.
4. **Rewrite** — Rewrite only 弱/失分 answers using `answer-rules.md` §2. Keep every fact traceable to the resume; mark missing ones `待补`.
5. **Predict next round** — Derive likely follow-ups from what this round exposed, plus the next round's emphasis (`answer-rules.md` §3).
6. **Study list** — Turn 能力缺口 items into concrete study actions with a deliverable (e.g. 一份产品拆解、一份 SQL 练习记录、一页 PRD).

## Output
- Use `assets/template.html`, keep `data-mode="review"` and `data-mode="both"` sections, delete prep sections and their TOC links.
- Save to `ROOT/outputs/<公司>_<岗位>_<YYYYMMDD>/面试复盘.html`.
- If the next round is confirmed, offer to generate the next-round prep playbook; feed the repair rules into its `#prior` section.
