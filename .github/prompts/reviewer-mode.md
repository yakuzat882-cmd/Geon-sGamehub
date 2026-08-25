GEONGAMEHUB — REVIEWER MODE

READ FIRST

Before implementing or modifying Reviewer Mode, read:

../copilot-instructions.md

Then read:

./geonquizscreen.md

Then inspect the current repository code.

The current repository code is the source of truth.

Do not guess the architecture.

PURPOSE

Reviewer Mode is a separate practice/review system.

It allows the player to review existing quiz questions without changing normal level progression.

Reuse the existing quiz/question system.

Do NOT create a second quiz engine.

CORE RULE

Reviewer Mode must remain separate from Normal Quiz and Daily Challenge.

It may reuse:

question loading
question rendering
answer checking
timer functions
lives UI
quiz UI
result UI

but its state must remain mode-aware.

BEFORE EDITING

Inspect:

Reviewer Mode HTML
Reviewer Mode CSS
Reviewer Mode JavaScript
existing subject selection
question-bank loading
quiz rendering
answer validation
quiz state
localStorage
used-question/history logic
reward functions
statistics functions
navigation/panel functions

Search all references before modifying existing functions.

Reuse existing functions whenever possible.

SUBJECTS

The existing subjects are:

MATH
SCIENCE
PSYCHOLOGY
TECH 1
TECH 2

Each subject contains:

SUBJECT 1
SUBJECT 2

Do not create another subject system.

Reviewer Mode must use the existing subject structure.

QUESTION SOURCE

Use the existing question banks:

questions.json
questions.new.json
questions.embedded.js
questions.new.embedded.js

Do not create a separate reviewer question database.

Do not copy all questions into a new file.

Do not modify the existing question-bank structure unless explicitly required.

Preserve the existing question object structure.

QUESTION SELECTION

Reviewer Mode should select valid existing questions from the selected subject/type.

Default reviewer session:

10 questions.

Avoid duplicate questions inside one reviewer session.

Do not change normal question ordering.

Do not corrupt normal question history.

If the repository already contains reviewer-selection logic, inspect and reuse it.

NORMAL PROGRESSION ISOLATION

Reviewer Mode must NOT:

advance normal levels
complete normal levels
unlock normal levels
change normal subject progress
change normal level progress
overwrite normal quiz state
consume normal progression state

Reviewer Mode is practice only unless a specific task explicitly requests another behavior.

REWARDS

Reviewer Mode must NOT automatically give normal progression rewards unless the existing project explicitly defines reviewer rewards.

Do not duplicate:

points
coins
level rewards
streak rewards
achievement rewards

Before changing rewards:

find the existing reward functions
find their callers
check how reward state is saved

Do not create another currency or reward system.

STATISTICS

Do not automatically modify normal statistics unless the existing implementation already includes Reviewer Mode.

Inspect:

statistics storage
statistics calculations
quiz completion tracking

Prevent reviewer questions from being double-counted.

SAVE DATA

Reviewer Mode must not damage existing localStorage data.

Before changing storage:

find existing keys
find all references
understand the stored structure
preserve existing data
add safe defaults if needed

Never casually rename existing keys.

Never reset the entire player save.

Do not create a duplicate save system.

QUIZ STATE

If the existing quiz engine has a mode/state identifier, reuse it.

Reviewer Mode should have a clear mode distinction from:

NORMAL
DAILY CHALLENGE

Do not duplicate global quiz state unnecessarily.

When leaving Reviewer Mode:

stop active timers
clear temporary reviewer state
return safely to the previous screen
do not overwrite normal quiz progress

UI FLOW

Expected flow:

HOME / MENU
→ REVIEWER MODE
→ REVIEWER PANEL
→ SELECT SUBJECT
→ START
→ 10 QUESTIONS
→ RESULT
→ BACK / RETURN

Use the existing navigation conventions.

If the project uses BACK instead of X for panels, preserve that convention.

UI REQUIREMENTS

Reviewer Mode panel should clearly show:

REVIEWER MODE
subject selection
selected subject
question count
START
BACK

Do not redesign the entire Home screen.

Do not modify unrelated panels.

QUESTION DISPLAY

Reuse the existing quiz question display.

Preserve:

question formatting
answer buttons
answer validation
explanation behavior
feedback
progress display

Do not create a second question renderer if the current renderer can be reused.

TIMER AND LIVES

Inspect the existing timer and lives implementation first.

Do not assume Reviewer Mode should use the same rules as Normal Quiz.

If Reviewer Mode uses the shared timer/lives system:

ensure it cannot modify normal progression
ensure the timer stops when leaving Reviewer Mode
ensure game-over handling returns correctly
ensure no state leaks into Normal Quiz

If the existing Reviewer Mode intentionally has no timer or lives, preserve that behavior.

QUESTION HISTORY

Inspect existing used-question/history logic.

Reviewer Mode should not accidentally consume or reset normal progression question history.

If the repository already has separate reviewer history, preserve it.

If no separate reviewer history exists, make the smallest safe implementation.

Do not rewrite the question-bank system.

THREE THEMES

Reviewer Mode MUST support all three existing themes:

original
light
dark

Check:

panel background
text
buttons
borders
subject cards
question cards
answer buttons
selected states
disabled states
result screen
progress display

Never introduce a hard-coded color that breaks another theme.

MOBILE

The game is primarily used on phones.

Reviewer Mode must remain:

responsive
touch friendly
readable
properly spaced

Check:

small screens
subject buttons
panel width
question text
answer buttons
START/BACK buttons
result screen

Avoid:

horizontal scrolling
tiny buttons
text overflow
oversized panels

ERROR HANDLING

If a selected subject has fewer than 10 valid questions:

do not create invalid questions.

Inspect the question pool.

Use the existing fallback behavior if available.

Do not modify question-bank data automatically just to hide the problem.

Do not crash the entire game.

COMPATIBILITY

Reviewer Mode must remain compatible with:

Normal Quiz
Daily Challenge
Subject Mastery
Achievements
Streak system
Points
Coins
Profile
Settings
three-theme system
existing save data

Do not modify these systems unless required.

VALIDATION

After implementation verify:

[ ] Reviewer Mode opens.

[ ] Reviewer panel displays correctly.

[ ] All subjects can be selected correctly.

[ ] SUBJECT 1 / SUBJECT 2 behavior is correct.

[ ] START works.

[ ] 10 valid questions are loaded.

[ ] Questions come from the existing question system.

[ ] No duplicate question appears in one session.

[ ] Question rendering works.

[ ] Answer checking works.

[ ] Explanations work if applicable.

[ ] Timer works correctly if applicable.

[ ] Lives work correctly if applicable.

[ ] Reviewer Mode completion works.

[ ] Reviewer Mode does not advance normal levels.

[ ] Reviewer Mode does not change normal subject progress.

[ ] Reviewer Mode does not corrupt normal quiz state.

[ ] Normal Quiz still works afterward.

[ ] Daily Challenge still works afterward.

[ ] Save data remains intact.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do not:

rewrite script.js
replace the quiz engine
replace question banks
create duplicate question databases
create duplicate localStorage systems
create duplicate reward systems
redesign Home
redesign unrelated panels
add unnecessary libraries
modify unrelated features

Inspect first.

Reuse existing systems.

Change only what the task requires.

RESPONSE

The user works mainly from a phone.

Do not paste huge code blocks.

After completing the task, respond with:

DONE

Files changed: [file names]

Changes: [short summary]

Tests: [short summary]

Commit/PR: [real link if available]

Notes: [only if necessary]

Never invent commit hashes, links, or test results.

FINAL RULE

READ MASTER INSTRUCTIONS.

READ GEONQUIZSCREEN INSTRUCTIONS.

INSPECT CURRENT REVIEWER MODE CODE.

REUSE EXISTING QUIZ SYSTEM.

KEEP REVIEWER MODE ISOLATED FROM NORMAL PROGRESSION.

KEEP DAILY CHALLENGE COMPATIBLE.

PRESERVE SAVE DATA.

PRESERVE ALL 3 THEMES.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
