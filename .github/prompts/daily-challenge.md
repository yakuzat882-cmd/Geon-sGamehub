GEONGAMEHUB — DAILY CHALLENGE

READ FIRST

Before implementing or modifying Daily Challenge, read:

../copilot-instructions.md

Then read:

./geonquizscreen.md

The current repository code is the final source of truth.

Inspect the existing implementation before editing.

Do not guess the architecture.

---

PURPOSE

Daily Challenge is a separate replay feature.

It must provide a daily 10-question challenge while remaining isolated from normal 80-level progression.

Reuse the existing quiz/question system whenever possible.

Do NOT create a second quiz engine.

---

CURRENT DAILY CHALLENGE

Current session size:

10 questions.

Daily Challenge should have its own:

- entry point
- challenge session
- progress display
- completion state
- reward handling
- date/state persistence

It must remain separate from normal level progression.

---

BEFORE EDITING

Inspect the current repository and find:

- existing Daily Challenge HTML
- Daily Challenge CSS
- Daily Challenge JavaScript
- challenge state
- challenge question generation
- challenge date handling
- challenge progress
- challenge rewards
- localStorage keys
- existing quiz functions
- existing question-bank functions

Search all references before changing any existing function.

Reuse existing functions whenever possible.

---

QUESTION SOURCE

Daily Challenge must use the existing question-bank architecture.

The project has:

- questions.json
- questions.new.json
- questions.embedded.js
- questions.new.embedded.js

Do not create a new question database.

Do not duplicate the question objects.

Do not modify existing question-bank structure just to implement Daily Challenge.

The challenge must use valid existing question records.

---

QUESTION SELECTION

Daily Challenge contains 10 questions.

Questions should be selected using the existing question system.

Preserve:

- subject structure
- SUBJECT 1 / SUBJECT 2
- question-bank selection
- question format
- answer validation
- explanation behavior

Avoid accidental duplicate questions inside the same challenge.

Do not change normal level/question ordering.

If the existing project already has a challenge selection algorithm, reuse it instead of replacing it.

---

SUBJECT HANDLING

Daily Challenge must respect the existing subject architecture.

Existing subjects:

- MATH
- SCIENCE
- PSYCHOLOGY
- TECH 1
- TECH 2

Each subject has:

- SUBJECT 1
- SUBJECT 2

Do not create another subject system.

If Daily Challenge already determines a subject/type automatically, preserve that behavior.

If the requested task requires subject selection, use the existing subject-selection UI and data structure.

---

NORMAL PROGRESSION ISOLATION

This is critical.

Daily Challenge must NOT accidentally behave like a normal level.

Unless explicitly requested, Daily Challenge must NOT:

- advance normal levels
- change normal level progress
- unlock normal levels
- complete normal levels
- change normal subject progression
- consume normal progression state
- overwrite normal quiz state

Daily Challenge may use shared quiz rendering and answer functions, but its completion must remain mode-aware.

---

REWARDS

The current Daily Challenge has its own reward behavior.

Existing challenge rewards include:

- bonus points
- bonus coins

Before modifying rewards:

1. Find the existing reward functions.
2. Find how Daily Challenge calls them.
3. Check whether the reward is already saved.
4. Prevent duplicate rewards.
5. Preserve the existing points/coins systems.

Do not create another currency system.

Do not award normal level rewards accidentally.

Do not award the same Daily Challenge reward twice for one completed challenge.

---

DAILY DATE LOGIC

Daily Challenge is date-based.

Inspect the existing implementation for how the current date is stored and compared.

The challenge should represent the current calendar day.

Do not use a fragile timestamp comparison if the existing implementation already uses a date key.

A completed challenge should remain completed for that same day after page reload.

A new day should allow the next challenge.

Do not erase unrelated player save data when the date changes.

---

SAVE DATA

Daily Challenge persistence is critical.

Before changing storage:

1. Find the existing Daily Challenge localStorage key(s).
2. Find every reference.
3. Understand the stored structure.
4. Preserve existing saved data.
5. Add defaults safely if needed.
6. Test page reload.

Never casually rename an existing storage key.

Never reset the entire player save.

Never overwrite unrelated progress.

---

CHALLENGE STATE

Daily Challenge should keep its state separate from normal quiz state.

Track only what the existing architecture requires, such as:

- current date
- challenge questions
- current question
- progress
- completion
- reward claim/completion state

Do not duplicate global quiz state unnecessarily.

If the existing quiz engine supports a quiz mode/state identifier, reuse it.

---

START / PROGRESS / COMPLETION

The Daily Challenge flow should be:

HOME / MENU
→ DAILY CHALLENGE
→ CHALLENGE PANEL
→ START
→ 10-question session
→ RESULT / COMPLETION
→ DAILY REWARD
→ return to normal game

Do not destroy or replace the normal Home screen.

Use the existing panel/navigation conventions.

If the project convention uses BACK instead of X, preserve it.

---

UI REQUIREMENTS

Daily Challenge UI must match the existing game.

The panel should clearly communicate:

- DAILY CHALLENGE
- current date/challenge status
- number of questions
- progress
- reward preview
- START
- BACK

Do not add unnecessary navigation controls.

Do not redesign unrelated Home UI.

---

THREE THEMES

Daily Challenge MUST support all existing themes:

- original
- light
- dark

Check:

- panel background
- title
- text
- buttons
- progress
- reward display
- question cards
- answer buttons
- result screen
- borders
- selected states
- disabled states

Never introduce a hard-coded color that breaks another theme.

---

MOBILE

Daily Challenge must remain mobile friendly.

Check:

- panel width
- button size
- text wrapping
- question wrapping
- reward display
- progress display
- touch targets
- small screen layout

Avoid horizontal scrolling.

Do not make the challenge panel unnecessarily large.

---

QUIZ ENGINE REUSE

Reuse existing quiz functions for:

- question rendering
- answer validation
- timer
- lives if applicable
- result handling
- common UI

Do not copy the entire normal quiz implementation.

If a shared function needs to distinguish Daily Challenge from Normal Quiz, use the existing mode/state architecture or make the smallest safe addition.

---

TIMER AND LIVES

Before changing Daily Challenge timer/lives behavior, inspect the current implementation.

Do not assume Daily Challenge should have the same behavior as Normal Quiz unless the existing code already does so.

If shared timer/lives functions are used, ensure they do not modify normal progression.

Prevent timers from continuing after completion or leaving the challenge.

---

STATISTICS

Do not automatically add Daily Challenge results to normal statistics unless the existing design already does so.

Before changing statistics:

- inspect current statistics storage
- inspect current statistics calculations
- determine whether Daily Challenge is already included

Do not double-count challenge questions.

---

REVIEWER MODE COMPATIBILITY

Daily Challenge and Reviewer Mode are separate special modes.

Do not accidentally make their state or question history conflict.

Do not change Reviewer Mode while implementing Daily Challenge unless required.

---

QUESTION HISTORY

Before changing challenge question selection:

Inspect existing used-question/history logic.

Determine whether challenge questions currently have separate tracking.

Do not reset normal question history.

Do not accidentally make Daily Challenge consume normal progression history unless that is already the intended implementation.

---

ERROR HANDLING

If fewer than 10 valid questions are available:

Do NOT silently create invalid question objects.

Inspect why the pool is insufficient.

Use the existing fallback/question-bank behavior when available.

Do not crash the entire quiz.

Do not modify question-bank data automatically to hide the problem.

---

VALIDATION

After implementing Daily Challenge, verify:

[ ] Daily Challenge opens.

[ ] Panel displays correctly.

[ ] START works.

[ ] Exactly 10 valid questions are used.

[ ] Questions come from the existing question system.

[ ] No accidental duplicate question appears in one challenge.

[ ] Answers work.

[ ] Timer works if applicable.

[ ] Lives work if applicable.

[ ] Progress updates.

[ ] Completion works.

[ ] Reward is granted correctly.

[ ] Reward is not duplicated.

[ ] Points remain correct.

[ ] Coins remain correct.

[ ] Normal level progress is unchanged.

[ ] Normal subject progress is unchanged.

[ ] Save survives reload.

[ ] Same-day completion remains completed.

[ ] New-day behavior works.

[ ] Reviewer Mode still works.

[ ] Normal Quiz still works.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

---

CHANGE POLICY

Make the smallest safe change.

Do not:

- rewrite script.js
- replace the quiz engine
- replace the question banks
- redesign Home
- redesign unrelated panels
- create duplicate localStorage systems
- create duplicate reward systems
- add unnecessary libraries
- modify unrelated features

Inspect first.

Reuse existing systems.

Change only what the task requires.

---

RESPONSE

The user works mainly from a phone.

Do not paste huge code blocks.

After completing the task, respond with:

DONE

Files changed:
[file names]

Changes:
[short summary]

Tests:
[short summary]

Commit/PR:
[real link if available]

Notes:
[only if necessary]

Never invent commit hashes, links, or test results.

---

FINAL RULE

READ MASTER INSTRUCTIONS.

READ GEONQUIZSCREEN INSTRUCTIONS.

INSPECT CURRENT DAILY CHALLENGE CODE.

REUSE EXISTING QUIZ SYSTEM.

KEEP DAILY CHALLENGE ISOLATED FROM NORMAL PROGRESSION.

PRESERVE SAVE DATA.

PRESERVE ALL 3 THEMES.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
