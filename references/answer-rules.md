# Answer rules & pitfalls

Load this file when drafting the match matrix, defensibility map, Q&A, case, or rewritten answers (prep mode step 3–7, review mode step 4–5).

## 1. Evidence discipline
- Extract only confirmed facts from the resume: roles, projects, scope, outcomes, numbers. If PDF extraction fails, use a local PDF parser in an isolated Python environment; never fill gaps from imagination.
- Tag every claim in the HTML: `.tag.ok` 简历可证 / `.tag.tr` 岗位翻译 / `.tag.gap` 缺口风险 / `.tag.inf` 推断.
- Any supporting detail missing from the source becomes `<span class="fill">待补：…</span>` — a visible pre-interview fill-in item, not an invented answer.
- Label individual ownership, collaboration, and team/project outcomes separately. Never restate a team award or resume superlative as a personal achievement.

## 2. Answer structures
| Question type | Order |
|---|---|
| Experience / capability | 结论 → 目标用户/场景 → 2–3 个动作 → 证据 → 指标或风险 |
| Behavioral | STAR（情境 → 任务 → 行动 → 结果），结果段必须有证据或 `待补` |
| Case / 方案题 | 目标与北极星指标 → 用户分层与参与阻力 → 机制（激励/内容分发/参与路径）→ 过程与结果指标 → 复盘节奏与风险预案 |
| Motivation | 动机绑定一项运营/产品能力或一个用户洞察，不说空泛热爱 |
| Gap / weakness | 承认 → 已有的相邻能力 → 已在做的补课动作 → 入职后计划 |

## 3. Round emphasis
| Round | Emphasis |
|---|---|
| HR 初筛 | 动机、稳定性、岗位理解、薪资与到岗 |
| 业务一面 | 个人执行细节、方法、数据、工具 |
| 主管 / 二面 | 业务判断、平台理解、优先级、跨团队协作、风险处理、可衡量交付 |
| HRBP / offer | 价值观、团队适配、职业规划 |

For a manager/lead round, convert every prior-round feedback gap into one explicit repair rule (template section `#prior`).

## 4. Defensibility map
For every prominent number, superlative, award, broad role title, and "主导/全流程/深度参与" claim, prepare:
1. likely follow-up chain (≥3 levels: what → how → why/what if)
2. ownership boundary (本人 / 协作 / 团队)
3. evidence from the resume, or a `待补` item
4. attribution-safe wording

## 5. Pitfalls
- Do not claim game knowledge, community growth results, SQL skill, or commercial outcomes absent from the resume.
- Do not equate content operations with community operations; translate through user participation, content supply, feedback loops, and cross-team delivery.
- Do not open an activity case with giveaways. Explain target users, participation friction, incentives, content distribution, and evaluation first.
- Do not reduce an official/community platform to an "announcement channel". Explain the user-intent scenario, the tool/content/interaction loop, and the feedback loop.
- Do not frame community governance as "only positive content". Distinguish avoiding amplification of harmful content from receiving, classifying, explaining, routing, and governing legitimate user feedback.
- Keep internal company experience desensitized; never expose confidential project details.
- Avoid generic lines such as "我热爱游戏"; attach every motivation claim to a capability or user insight.
