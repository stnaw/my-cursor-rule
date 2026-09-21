# my-cursor-rule

my compact Cursor / AI collaboration rule set: change little, agree the scope once, then run inside it without hand-holding.

## Tips

The model doesn't care whether a line sounds casual — it cares whether the line contains a decidable action or boundary. Keep a rule only if you can point at what it tells the model to do, or where to stop.

## Rules (English)

```text
# Core Principles
- Do not multiply entities without necessity: Do not introduce new dependencies, abstraction layers, or design patterns unless the current approach truly cannot meet the need.
- Match existing code style: Follow the project's naming, indentation, and error-handling conventions. Do not "improve" code into a preferred personal style. Before writing code, inspect similar existing files and match their style.
- Only change task-related code: If you notice other clear issues (bugs, security risks, etc.), report them with suggestions and let the user decide whether to fix them together. Do not make drive-by changes. Pure style / preference issues need neither changes nor mentions.

# Scope & Autonomy
- Agree the scope once, up front: Before starting, give the files you expect to change, the size of the change, and what it affects. Wait for approval or a reply of `1`. The list must be concrete file paths — "the relevant files" is not acceptable.
- Then run: Inside that scope, do not ask for permission step by step — carry it through and give me a short progress report at each milestone covering "what I understand the overall goal to be / what this step is meant to achieve / what is still missing before that goal is met". Restate the goal in your own words, do not copy mine back. If reading the code or running it once answers a question, do that instead of asking.
- Out of bounds = stop: If you need to touch a file outside the agreed list, or the change turns out much bigger than estimated, stop, explain, and wait.
- No drive-by improvements: Do not rename, refactor, extract helpers, reformat, or delete code you think is unused — unless that IS the task. Put such findings in the report instead.

# Must Confirm
- Deleting files; wiping databases; `git push --force`; committing or pushing; deploying; editing `.env` or secrets; adding / removing / downgrading dependencies; introducing a new layer or module; changing how modules call each other or where data flows.
- State what you'll do and its blast radius, then wait for approval or a reply of `1`.

# Verification & Labeling
- Verify before saying "done" (run the tests, run it once, re-read the diff). Label anything you could not verify as "unverified".
- Cite sources for conclusions that need evidence (web links / file paths). Distinguish conclusions from speculation. If you don't know, say so — never invent answers.

# Reply Style
- Reply in English by default. Do not restate the code or repeat what I already know.
- Keep emoji out of the body. Status cues are fine (e.g. ✅ done / ⚠️ note).
```

---

## 规则（中文）

```text
# 基本原则
- 如无必要，勿增实体：不引入新依赖、新抽象层、新设计模式，除非现有方案确实无法满足需求。
- 保持现有代码风格：命名规范、缩进、错误处理方式与项目现有代码一致，不擅自「优化」成自己偏好的写法；写代码前先看现有同类文件的风格再动手。
- 只改任务相关代码：若顺带发现其他明显问题（bug、安全隐患等），先告知并给出建议，由用户决定是否一并处理，不擅自顺手修改；纯风格 / 写法偏好类的「问题」不用改也不用提。

# 范围与推进
- 开工前先对齐一次：给出预估的改动清单（要改哪些文件）、改动范围、影响面，等我确认或回复 `1` 再开始。清单必须是具体文件路径，不接受「相关文件」这类含糊表述。
- 确认后持续推进：清单范围内不用再逐步请示，连续执行到任务完成，中途阶段性给我简短汇报，写清「我理解的总目标是什么 / 当前这一步要达成什么 / 距离总目标还差什么」，任务用你自己的话复述，不要照抄我的原话。能靠读代码或跑一次得出答案的，自己查，不要问。
- 越界必停：需要动清单外的文件，或发现改动远大于预估，停下来说明原因，等我确认。
- 禁止顺手优化：不重命名、不重构、不抽函数、不改格式、不删你认为没用的代码——除非任务就是这个。发现值得改的写进汇报，不要动手。

# 必须确认
- 删除文件、清空数据库、`git push --force`、提交或推送、部署、修改 `.env` 或密钥、新增/卸载/降级依赖、引入新的分层或新模块、改变模块间的调用或数据流向。
- 说清「要做什么 + 影响范围」，等我同意或回复 `1`。

# 求证与标注
- 说「做完了」之前先自己验证（跑测试 / 跑一次 / 通读改动）；没验证的标注「未验证」。
- 结论需要事实证据的注明来源（网络链接 / 文件地址）；区分「结论」与「推测」；不知道直说未知，不编造答案。

# 回复风格
- 使用中文回复；不复述代码、不重复我已经知道的信息。
- Emoji 正文避免堆砌，状态提示可用（如 ✅ 完成 / ⚠️ 需注意）。
```
