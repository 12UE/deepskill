# DeepSkill

[涓枃鏂囨。](README_CN.md)

**A battle-tested AGENTS.md skill file for DeepSeek V4 Pro 鈥?engineering discipline that turns AI coding assistants from "fast but sloppy" into "right the first time".**

---

## What is this?

A single `AGENTS.md` file that dramatically improves the code quality and reliability of AI coding assistants (especially **DeepSeek V4 Pro**) by injecting five core engineering disciplines into the system prompt:

| # | Skill | Core Idea |
|---|-------|-----------|
| 1 | **Risk Analysis** | Think before you code. Assess impact before making changes. |
| 2 | **Self-Verification** | Verify every change with tools, not memory. |
| 3 | **Precision Operations** | Prefer accuracy over speed in batch modifications. |
| 4 | **Environment Awareness** | Always confirm the build environment before writing code. |
| 5 | **Completeness Assurance** | Fix all instances of a problem in one pass, not across multiple rounds. |

## The Core Principle

> **Think 鈫?Do once 鈫?Verify 鈫?Done**
>
> NOT: Do 鈫?fail 鈫?fix 鈫?fail again 鈫?fix again 鈫?finally pass

**Slow is fast.** Getting it right the first time costs far less than rework.

## Available Versions

| Language | File |
|----------|------|
| English | [`AGENTS_EN.md`](AGENTS_EN.md) |
| 涓枃 | [`AGENTS.md`](AGENTS.md) |

## Quick Start

### Global (all projects)

Copy the AGENTS file to your home directory:

```bash
# Linux / macOS
cp AGENTS.md ~/AGENTS.md

# Windows
copy AGENTS.md %USERPROFILE%\AGENTS.md
```

### Per-project

Copy `AGENTS.md` to your project root:

```bash
cp AGENTS.md /path/to/your/project/AGENTS.md
```

The AI assistant will automatically load it as system instructions.

## Why does it work?

Most AI coding assistants are **fast but reckless** 鈥?they jump straight into writing code without analyzing impact, skip verification after changes, and use global find-replace without checking for side effects. This leads to a frustrating cycle of compile errors, missing references, and broken builds.

This skill file installs **five mental guardrails** that force the assistant to:

- **Analyze before acting** 鈥?no more "edit first, think later"
- **Verify after every change** 鈥?grep confirms, not gut feeling
- **Prefer precision over speed** 鈥?one correct change beats five broken ones
- **Read the environment** 鈥?`.c` vs `.cpp` matters, compiler flags matter
- **Finish completely** 鈥?"mostly done" is not done

## Tested With

- **DeepSeek V4 Pro** (primary target, excellent results)
- Compatible with any AI coding tool that supports `AGENTS.md` system prompts (e.g., opencode, Cursor, etc.)

## License

[MIT](LICENSE)
