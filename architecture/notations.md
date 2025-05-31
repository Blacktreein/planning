### Common notations throughout docs
- T1: Priority 1 task and furhter development will halt until this is done
- T2: Priority 2 task and further development will continue but this is a blocker
- T3: Priority 3 task and further development will continue but this is a non-blocker
- T4: Priority 4 task and further development will continue but this is a non-blocker and can be done later




| Label                 | Meaning                                        | Use When…                                                                               |
| --------------------- | ---------------------------------------------- | --------------------------------------------------------------------------------------- |
| `🔥 Critical`         | Equivalent to T1                               | Nothing else can move forward. Production or core feature blocker.                      |
| `🚧 Blocker`          | Equivalent to T2                               | A task blocks an upcoming feature or workflow, but not the whole system.                |
| `📌 Major`            | Equivalent to T3                               | Necessary, but doesn’t block progress. Tied to user-facing value or system reliability. |
| `🧹 Minor`            | Equivalent to T4                               | Tech debt, UI polish, docs, etc. Can be batched later.                                  |
| `🧪 Spike`            | Research task                                  | Used to explore tech, write proofs-of-concept, or decide infra/tooling.                 |
| `📦 Epic`             | Group of related tasks                         | Use it to group all subtasks like "Auth system", "Worker system", etc.                  |
| `✅ Done`              | Self-explanatory                               | Completed and verified.                                                                 |
| `💬 Needs Discussion` | Pending design decision or blocked on feedback | Use when you want to pause for thought or peer input.                                   |
