# Engineering Discipline Skills

---

## Skill 1: Risk Analysis & Prediction

### Description

Complete a thorough risk assessment and impact analysis before writing any code. Eliminate errors at the design stage, not the execution stage.

### Checklist

- [ ] After receiving a task, read all related code completely and map the impact scope
- [ ] List "potential chain-reaction problems from this change" and assess each one
- [ ] Answer three questions: **What could break? What are the hidden assumptions? What are the edge cases?**
- [ ] Before large-scale changes, validate the full "modify 鈫?compile 鈫?verify" cycle on a single function first
- [ ] Only proceed broadly after confirming feasibility 鈥?never change everything at once then compile
- [ ] Before starting any new task, review the "known pitfalls checklist"

### Anti-Patterns

- Writing code without prior analysis
- Using the compiler as a substitute for thinking
- Allowing the same class of error to occur twice

---

## Skill 2: Self-Verification

### Description

Actively verify after every change using tools, not memory, to confirm correctness and completeness.

### Checklist

- [ ] **Rename operations**: grep to confirm zero residual occurrences of the old name
- [ ] **Deletion operations**: grep to confirm no dangling references
- [ ] **Type operations**: compile to verify type compatibility
- [ ] Check that forward declarations match function definitions
- [ ] Check that all call sites have synchronized parameter updates
- [ ] Check that no references remain after variable removal
- [ ] After batch replacements, immediately run grep for reverse verification

### Anti-Patterns

- Finishing changes without verification, assuming "it should be fine"
- Relying on memory instead of process
- Saying "I think I changed them all" instead of "grep tells me I changed them all"

---

## Skill 3: Precision Operations

### Description

When facing batch modifications, prioritize precision over speed. Correctness comes before velocity.

### Checklist

- [ ] Before replacing, use grep to count expected matches
- [ ] After replacing, use grep to count actual replacements 鈥?numbers must match
- [ ] Use exact string matching over regex when possible
- [ ] Modify function-by-function rather than global replace when possible
- [ ] When same-named identifiers exist in different scopes, handle each function individually
- [ ] Adopt "do one, verify one" instead of "do all, verify later"

### Anti-Patterns

- Executing global replacements without dry runs
- Blindly replacing same-named identifiers across scopes
- Sacrificing correctness for speed

---

## Skill 4: Environment Awareness

### Description

Maintain active awareness of the working environment. Confirm the environmental context before writing code.

### Checklist

- [ ] Before starting work, confirm the compilation language (C / C++ / mixed)
- [ ] Confirm the compiler version and language standard
- [ ] Confirm project configuration (character set, calling convention, warning level)
- [ ] When file names, extensions, or project configurations change, immediately assess impact
- [ ] When unsure if a construct is legal, write a minimal test to verify first
- [ ] Maintain a "C vs C++ key differences" quick-reference

### Anti-Patterns

- Looking only at code content, never at the code environment
- Assuming "what compiled before will compile now"
- Replacing "verified it works" with "it should work"

---

## Skill 5: Completeness Assurance

### Description

Clear all instances of a problem class in one pass. Raise the definition of "done" to truly mean one-and-done.

### Checklist

- [ ] "Done" means: tool-scanned confirmation that nothing was missed
- [ ] When encountering one problem, immediately search for "are there other instances of this class?"
- [ ] Use grep/glob for comprehensive search 鈥?don't just fix what's in front of you
- [ ] Identify all sub-tasks at the requirements stage (e.g., renaming 鈫?v-variables, a-parameters, register names, Hungarian notation 鈥?all covered)
- [ ] Before ending each step, run a full scan to confirm zero residuals

### Anti-Patterns

- Settling for "mostly changed" instead of "completely changed"
- Waiting for the user to ask before covering related instances
- Spreading same-class fixes across multiple rounds

---

## Core Principle

> **Think 鈫?Do once 鈫?Verify 鈫?Done**

- **Slow is fast**: Getting it right once costs far less than rework
- **Replacing thinking with execution is the root of all problems**
- **Rely on process and tools, not memory**
- **Always doubt your own changes**
