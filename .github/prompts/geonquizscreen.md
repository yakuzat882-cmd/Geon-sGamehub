# GEONQUIZSCREEN — TECHNICAL COPILOT GUIDE V2

## READ FIRST

Before working on GeonQuizScreen, read:

https://github.com/yakuzat882-cmd/GeonGameHub.1/blob/main/.github/copilot-instructions.md

The master instructions are mandatory.

Then inspect the CURRENT repository before editing.

This file is only the specialized guide for the quiz system.

The current repository is always more authoritative than this document.

---

# QUIZ SYSTEM PURPOSE

GeonQuizScreen is the main interactive quiz experience.

It connects:
- subject selection
- subject type
- question bank
- level
- question loading
- answer validation
- timer
- lives
- score
- points
- coins
- streak/combo
- progression
- results
- statistics
- save data

Do not replace this architecture with a new quiz engine.

Reuse existing functions whenever possible.

---

# CURRENT SUBJECT STRUCTURE

The project has 5 main subjects:

1. MATH
2. SCIENCE
3. PSYCHOLOGY
4. TECH 1
5. TECH 2

Each subject contains:

- SUBJECT 1
- SUBJECT 2

The existing quiz architecture must preserve this relationship.

Never assume that SUBJECT 1 and SUBJECT 2 are interchangeable.

Always inspect how the selected subject/type is represented in the current JavaScript.

---

# CURRENT QUESTION BANK SYSTEM

The project contains two main question banks:

questions.json
questions.new.json

There are also embedded versions:

questions.embedded.js
questions.new.embedded.js

The application can distinguish between the existing/previous question bank and the new question bank.

Do not merge these systems.

Do not accidentally load the wrong bank.

Do not replace external question data with embedded data unless the existing code requires it.

Before changing question loading, inspect:
- bank selection
- fallback logic
- loading functions
- question normalization
- subject filtering
- level filtering

---

# QUESTION DATA

The question records use fields including:

- id
- level
- question
- choices
- answer
- explanation

Preserve the current data format.

Do not rename fields without searching all references.

Do not change the meaning of:
- id
- level
- choices
- answer
- explanation

When adding questions:
- preserve the existing structure
- preserve the correct subject
- preserve the correct subject type
- preserve the correct level
- avoid duplicate IDs
- avoid duplicate questions
- avoid accidental cross-level duplication

Do not reorder existing questions unless explicitly requested.

---

# LEVEL ALIGNMENT

The quiz uses an 80-level structure.

Level selection must load the correct level data.

When working with level selection:

1. Inspect how the selected level is stored.
2. Inspect how the question pool is built.
3. Inspect how questions are filtered.
4. Verify that the selected level maps to the intended questions.
5. Preserve existing level IDs.
6. Preserve existing progress.

Never create a second level mapping system.

Do not silently change the number of levels.

Do not automatically unlock levels unless explicitly requested.

---

# QUESTION POOL

Before changing question selection logic, inspect the existing functions responsible for:

- active question bank
- subject pool
- level filtering
- question session creation
- used-question tracking
- randomization
- question ordering

Reuse the existing pipeline.

Do not create a second question-selection pipeline unless absolutely necessary.

If randomization exists, preserve its intended behavior.

If level alignment exists, preserve it.

---

# QUIZ STATE

The quiz maintains runtime state.

Before modifying quiz state, identify the actual variables/objects/functions currently used for:

- selected subject
- selected subject type
- selected question bank
- selected level
- current question
- question index
- question list
- score
- points
- coins
- lives
- timer
- streak
- combo
- correct answers
- completion
- game-over state

Do not invent duplicate state variables when existing state can be reused.

---

# QUESTION RENDERING

The quiz screen displays the current question and answer choices.

Before modifying rendering:
- inspect the existing HTML elements
- inspect their IDs/classes
- inspect JavaScript references
- inspect answer event listeners
- inspect dynamic rendering functions

Do not rename IDs/classes without checking every dependency.

Do not remove existing answer elements simply to replace them with new markup.

Preserve:
- question text
- answer choices
- selected state
- correct/incorrect state
- disabled state
- explanation behavior
- next-question behavior

---

# ANSWER HANDLING

The existing answer system must remain authoritative.

Before modifying answer handling, trace:

answer selection
→ answer validation
→ correct/incorrect state
→ score/points
→ streak/combo
→ lives if applicable
→ rewards if applicable
→ question progression
→ completion/game-over
→ save

Do not duplicate answer validation.

Do not create a second scoring system.

Do not award rewards twice.

Do not advance the question twice.

---

# TIMER

The normal quiz currently uses a 30-second timer.

Do not change the default unless explicitly requested.

Timer behavior must preserve:
- start
- countdown
- timeout
- stop
- reset
- next question
- game-over
- result handling

When changing timer UI, verify the underlying timer logic still works.

Prevent multiple timer intervals from running simultaneously.

Do not leave timers running after:
- answer completion
- quiz completion
- game over
- leaving the quiz

---

# LIVES

The normal quiz currently supports up to 8 lives.

Do not change the maximum unless explicitly requested.

Before changing lives:
- inspect how lives are initialized
- inspect how lives decrease
- inspect how lives are saved
- inspect how lives recover
- inspect game-over handling

Do not create another life counter.

---

# SCORE / POINTS / COINS

These are separate systems.

Do not treat them as the same value.

Preserve existing relationships between:
- score
- points
- coins
- rewards

Existing points-to-coins conversion:
100 points = 1 coin

Do not change this unless explicitly requested.

When modifying reward logic, verify that one answer/completion cannot accidentally grant the same reward multiple times.

---

# STREAK / COMBO

The quiz contains streak/combo behavior.

Existing milestone values include:
3, 5, 10, 15, 20.

Before modifying streak logic:
- inspect current counters
- inspect reset behavior
- inspect reward behavior
- inspect persistence

Do not create duplicate streak counters.

Do not reset streak incorrectly when moving between quiz questions.

---

# NORMAL PROGRESSION

Normal Quiz Mode is connected to level progression.

Normal quiz completion may update:
- level progress
- subject progress
- mastery
- titles
- achievements
- streak
- statistics
- rewards

Do not let isolated modes accidentally modify normal progression.

When changing completion behavior, determine whether the current mode is:

- Normal Quiz
- Daily Challenge
- Reviewer Mode
- another special mode

Then preserve the intended mode-specific behavior.

---

# DAILY CHALLENGE ISOLATION

Daily Challenge uses a separate 10-question session.

Do not treat Daily Challenge as a normal level.

Do not:
- change normal level progression
- consume normal level progress
- duplicate normal rewards
- corrupt normal quiz state

Reuse question rendering and answer handling where possible, but preserve mode-specific save/reward rules.

---

# REVIEWER MODE ISOLATION

Reviewer Mode uses a separate 10-question review session.

It uses the existing question system.

Reviewer Mode must remain isolated from normal progression.

Unless explicitly requested, Reviewer Mode must NOT:
- advance normal levels
- award normal progression rewards
- change normal completion
- corrupt normal used-question tracking

Reuse existing quiz components instead of copying the entire quiz engine.

---

# SAVE AND LOCALSTORAGE

The quiz is connected to persistent localStorage data.

Before changing any quiz save behavior:

1. Search for the actual storage key.
2. Search all references.
3. Understand what is stored.
4. Preserve existing player data.
5. Add backward-compatible defaults if needed.
6. Test reload.
7. Test continuing the quiz where applicable.

Never rename a storage key casually.

Never delete saved progression.

Never initialize new default data in a way that overwrites existing player data.

---

# USED QUESTION TRACKING

The project has logic related to question history/used questions.

Before changing question selection:
- find the existing used-question storage
- understand its scope
- determine whether it is per subject, level, bank or mode

Do not reset used-question history unintentionally.

Do not make normal quiz and Reviewer Mode share history if the current implementation keeps them separate.

---

# SUBJECT PROGRESS

Quiz completion can affect subject progress.

Progress must remain aligned with the existing 80-level system.

Before modifying progress:
- inspect the current calculation
- inspect how Subject 1 and Subject 2 are handled
- inspect how Home reads the value

Do not create a duplicate progress calculation.

---

# MASTERY AND TITLES

Quiz progression can affect mastery and titles.

Before modifying completion:
- inspect existing mastery functions
- inspect title functions
- inspect their storage
- preserve existing thresholds

Do not duplicate these systems.

---

# ACHIEVEMENTS

Quiz actions may trigger achievements.

Before changing reward/completion logic:
- inspect existing achievement checks
- preserve existing achievement state
- avoid triggering the same achievement repeatedly

Do not create duplicate achievement storage.

---

# THREE THEMES

GeonQuizScreen MUST work with:

- original
- light
- dark

Every quiz UI change must be checked in all 3.

Check:
- question card
- answer buttons
- selected answer
- correct answer
- incorrect answer
- timer
- lives
- score
- progress
- panels
- result screen
- buttons
- text
- borders

Never hard-code a color that breaks another theme.

---

# MOBILE REQUIREMENTS

The quiz is primarily used on mobile.

Check:
- question wrapping
- answer button width
- touch target size
- timer visibility
- lives visibility
- score visibility
- long questions
- long choices
- small screens
- orientation/responsive layout

Do not create horizontal overflow.

Do not make buttons too small to tap.

---

# HTML SAFETY

Before changing index.html:

Search script.js for every affected:
- ID
- class
- data attribute
- event listener
- selector

If an element is dynamically accessed, preserve the expected structure.

Do not remove an element because it looks unused without checking JavaScript.

---

# CSS SAFETY

Before changing style.css:

Find existing selectors.

Determine whether a selector is shared by:
- Home
- Quiz
- panels
- themes
- other screens

Prefer a scoped selector for QuizScreen changes when possible.

Avoid changing global styles for a local QuizScreen problem.

---

# JAVASCRIPT SAFETY

Before changing script.js:

Find:
- function definition
- all callers
- event listeners
- state dependencies
- storage dependencies
- DOM dependencies

Prefer modifying the existing function over creating duplicate logic.

Keep changes localized.

---

# PERFORMANCE

Do not introduce unnecessary:
- repeated timers
- repeated event listeners
- duplicated DOM rendering
- repeated JSON parsing
- expensive loops

Do not optimize unrelated code unless requested.

---

# DEBUGGING

If the quiz breaks:

Do not immediately rewrite the system.

Trace in this order:

1. selected mode
2. selected subject
3. selected subject type
4. selected question bank
5. question pool
6. selected level
7. session questions
8. current question index
9. rendering
10. answer handler
11. timer
12. progression
13. save

Find the actual failure point first.

---

# VALIDATION CHECKLIST

After QuizScreen changes:

[ ] Page loads without JavaScript errors.

[ ] Subject selection still works.

[ ] Subject 1 works.

[ ] Subject 2 works.

[ ] Previous question bank works.

[ ] New question bank works.

[ ] Correct level loads correct questions.

[ ] Answer selection works.

[ ] Correct answers work.

[ ] Incorrect answers work.

[ ] Timer works.

[ ] Lives work.

[ ] Score/points work.

[ ] Coins/rewards are not duplicated.

[ ] Streak/combo works.

[ ] Normal progression works.

[ ] Save data survives reload.

[ ] Daily Challenge remains isolated.

[ ] Reviewer Mode remains isolated.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were changed.

---

# CHANGE LIMIT

Only modify files required for the requested QuizScreen task.

Do not:
- redesign the entire game
- replace the quiz engine
- rewrite script.js
- replace question banks
- rename unrelated files
- change unrelated screens
- add frameworks unnecessarily
- remove existing features

If a larger architectural change is genuinely necessary, explain why before doing it when possible.

---

# RESPONSE FORMAT

The user uses a phone.

Never paste entire modified files unless explicitly requested.

Never paste huge code blocks in the final response.

Use:

DONE

Files changed:
[file names]

Changes:
[short summary]

Tests:
[short summary]

Commit/PR:
[real GitHub link if available]

Notes:
[only if necessary]

Never invent a link, commit or test result.

---

# FINAL RULE

READ MASTER INSTRUCTIONS FIRST.

INSPECT CURRENT CODE SECOND.

TRACE DEPENDENCIES BEFORE EDITING.

REUSE EXISTING QUIZ SYSTEM.

PRESERVE QUESTIONS, LEVELS AND SAVE DATA.

KEEP SPECIAL MODES ISOLATED.

KEEP ALL 3 THEMES WORKING.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.

KEEP FINAL RESPONSES SHORT.
