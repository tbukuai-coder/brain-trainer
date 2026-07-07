# 最强大脑 · 记忆训练 (Brain Trainer)

A single-file, zero-dependency HTML memory-training game inspired by the Chinese TV show 《最强大脑》 (*The Brain*, Jiangsu TV). Open `index.html` in any modern browser — no build step, no server needed.

## The four challenges

| 项目 | English | Discipline |
|---|---|---|
| 数字闪记 | Digit Flash | Digit span — a number flashes, type it back from memory. Starts at 3 digits, +1 per level. |
| 方格闪现 | Grid Flash | Spatial memory — cells light up on a board, tap them back. Board grows 3×3 → 6×6, display time shrinks. |
| 扑克速记 | Card Recall | Sequence memory — playing cards flash one by one; tap them back in original order from a shuffled pool. |
| 微观辨变 | Spot the Change | Observation memory (水哥-style) — study a board of near-identical symbols; one changes; find it. |

## Rules

- 3 lives per run; a mistake costs one life and replays the same level.
- Passing a level advances you; your best level per game is saved in `localStorage` (key `zqdn-bests`).
- Sound cues use WebAudio (no audio assets); toggle with the 音效 button, persisted in `localStorage`.

## Tech notes

- Pure vanilla HTML/CSS/JS in one file, Chinese-first UI with English captions.
- Committed single dark theme (stage-lighting look: ink navy + trophy gold). System font stacks only — Songti/serif for display, PingFang/YaHei for UI, monospace for digits.
- Async game rounds are cancellable via a session counter (`session++` on back/menu), so leaving mid-round cleanly abandons pending timers.
- Respects `prefers-reduced-motion`.
