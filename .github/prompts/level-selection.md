GEONGAMEHUB — LEVEL SELECTION

READ FIRST

Before implementing or modifying Level Selection, read:

../copilot-instructions.md

Then read:

./geonquizscreen.md

The current repository code is the source of truth.

Inspect the existing code before editing.

Do not guess the architecture.

PURPOSE

Add or improve Level Selection without breaking the existing quiz system.

The player must be able to choose a specific level before starting the quiz.

Level Selection must use the existing level/question architecture.

Do NOT create a second level system.

CORE RULE

Preserve the existing 80-level structure.

Do not rename existing level IDs.

Do not change existing level/question relationships.

Do not rewrite the quiz engine.

Do not automatically unlock levels unless explicitly requested.

BEFORE EDITING

Inspect:

index.html
style.css
script.js
questions.json
questions.new.json
questions.embedded.js
questions.new.embedded.js

Find:

level data
level IDs
level/question mapping
subject selection
quiz start functions
question loading
progress storage
selected-level state
localStorage keys
existing level UI
event listeners
DOM IDs/classes

Search references before changing IDs, classes, functions, or storage keys.

LEVEL STRUCTURE

The game uses 80 levels.

Existing quiz structure includes:

MATH
SCIENCE
PSYCHOLOGY
TECH 1
TECH 2

Each subject contains:

SUBJECT 1
SUBJECT 2

Preserve this structure.

Do not merge SUBJECT 1 and SUBJECT 2.

Do not create another subject or level database.

LEVEL GRID

If Level Selection is shown as a grid:

Use the existing visual language.

Example:

01 02 03 04 05
06 07 08 09 10

Continue through the existing 80 levels.

Use actual level IDs from the repository.

Do not hard-code a different numbering system if the existing data uses another ID format.

LEVEL SELECTION BEHAVIOR

When the player taps a level:

1. Store/select the chosen level.
2. Keep the selected subject and quiz type.
3. Load the correct question set.
4. Start the existing quiz flow.
5. Do not alter unrelated progress.

The selected level must load the correct questions.

Never load questions from another level accidentally.

SUBJECT COMPATIBILITY

Level Selection must preserve:

selected subject
SUBJECT 1 / SUBJECT 2
question-bank selection
selected quiz type
existing questioner mode

Do not allow a selected level from one subject to load another subject's questions.

Do not allow SUBJECT 1 questions to appear in SUBJECT 2 accidentally.

PROGRESSION

Level Selection must remain compatible with the existing progression system.

Important:

Choosing a level is not the same as completing a level.

Do not mark a level complete simply because it was selected.

Do not change progress until the existing quiz completion logic says it should change.

Do not automatically unlock levels unless explicitly requested.

If the current project already has unlocked/completed state, preserve it.

REPLAY

If a completed level is selected again:

Use the existing replay behavior.

Do not create duplicate progress entries.

Do not duplicate rewards.

Do not corrupt completion state.

SAVE DATA

Before changing level selection storage:

Find the existing localStorage keys.

Find every reference.

Understand the stored structure.

Preserve existing data.

Add safe defaults if necessary.

Never casually rename existing keys.

Never reset the entire player save.

Do not create a second progress system.

QUIZ ENGINE

Reuse the existing quiz engine.

Reuse existing functions for:

question loading
question rendering
answer checking
timer
lives
score
points
coins
streak
completion
result handling

Do not copy the normal quiz engine into Level Selection.

Level Selection only chooses what the existing quiz engine should play.

REWARDS

Selecting a level must not automatically award rewards.

Rewards should only occur through the existing completion/reward logic.

Do not create another reward system.

Do not duplicate points, coins, streak, or achievement rewards.

TIMER AND LIVES

Do not change the existing timer or lives values.

Level Selection should pass the selected level into the normal quiz flow.

Ensure:

timer starts correctly
timer stops correctly
lives behave normally
timeout works
game-over works
completion works

Do not leave an old timer running when changing screens.

UI

Level Selection should match the existing game.

Suggested panel structure:

SELECT A LEVEL

[01] [02] [03] [04] [05]
[06] [07] [08] [09] [10]
...

START
BACK

Use the existing project conventions.

If the project uses BACK instead of X, use BACK.

Do not redesign unrelated screens.

Do not add unnecessary navigation.

THREE THEMES

Level Selection MUST support all 3 themes:

original
light
dark

Check:

panel
level boxes
text
borders
selected state
completed state
buttons
hover/active states
disabled states

Never use a hard-coded color that breaks another theme.

MOBILE

The game is primarily used on phones.

Level Selection must be:

responsive
touch friendly
readable
compact

Check:

small screens
level grid
button sizes
spacing
text
panel height

Avoid:

horizontal scrolling
tiny level buttons
overflow
oversized panels

The level grid must remain usable on narrow phone screens.

LEVEL STATES

If the existing system has level states, preserve them.

Possible states may include:

available
completed
selected
locked

Do not invent new state behavior without inspecting the current code.

IMPORTANT:

Do not automatically unlock every level.

If the requested design requires all levels to be selectable, implement that only if explicitly requested and preserve completion/progress separately.

QUESTION VALIDATION

When a level starts:

Verify that its question list is valid.

Verify questions belong to:

selected subject
selected quiz type
selected level

Do not silently use unrelated questions.

Do not modify question-bank data automatically.

ERROR HANDLING

If the selected level has no valid questions:

Do not crash.

Inspect why the question pool is missing.

Use an existing fallback only if the project already provides one.

Do not create fake question objects.

Do not silently load another level's questions.

LEVEL PROGRESS

After completing a level:

Use the existing completion/progress functions.

Do not create duplicate progress calculations.

Preserve the existing 0–80 progress system.

Home progress must continue to reflect the existing stored progress.

COMPATIBILITY

Level Selection must remain compatible with:

Normal Quiz
Daily Challenge
Reviewer Mode
Subject Mastery
Achievements
Streak system
Points
Coins
Profile
Settings
localStorage
all 3 themes

Do not modify these systems unless required.

VALIDATION

After implementation verify:

[ ] Level Selection opens.

[ ] Level grid displays correctly.

[ ] Levels use the existing IDs.

[ ] Correct subject is preserved.

[ ] SUBJECT 1 works.

[ ] SUBJECT 2 works.

[ ] Correct question bank is selected.

[ ] Correct level questions load.

[ ] Selected level starts correctly.

[ ] 10/normal question flow remains correct according to existing quiz rules.

[ ] Timer works.

[ ] Lives work.

[ ] Answers work.

[ ] Completion works.

[ ] Progress updates only through existing logic.

[ ] Selecting a level does not mark it complete.

[ ] Rewards are not duplicated.

[ ] Save data survives reload.

[ ] Normal Quiz still works.

[ ] Daily Challenge still works.

[ ] Reviewer Mode still works.

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
create another level system
create duplicate progress storage
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

INSPECT CURRENT LEVEL SYSTEM.

REUSE THE EXISTING QUIZ ENGINE.

PRESERVE THE 80-LEVEL ARCHITECTURE.

PRESERVE SUBJECT 1 / SUBJECT 2.

PRESERVE SAVE DATA.

DO NOT AUTO-UNLOCK UNLESS REQUESTED.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
