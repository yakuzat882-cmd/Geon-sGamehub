GEONGAMEHUB — ACHIEVEMENTS

READ FIRST

Before implementing or modifying Achievements, read:

../copilot-instructions.md

Then read:

./geonquizscreen.md

Also inspect existing achievement code before editing.

The current repository code is the source of truth.

Do not guess the architecture.

PURPOSE

Achievements are persistent player milestones.

Improve or extend the existing achievement system without creating a second system.

Reuse existing achievement definitions, checks, rewards and save logic whenever possible.

Do NOT rewrite the achievement architecture for a small change.

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

achievement definitions
achievement IDs
achievement checks
achievement unlock functions
achievement display
achievement rewards
achievement localStorage
notification/toast logic
statistics references
level/progress references
streak references
coin/point references

Search all references before changing IDs, functions or storage keys.

EXISTING ACHIEVEMENTS

Preserve all existing achievements.

Examples may include:

Streak Master
Perfect Level
Survivor
Speed Quizzer
Coin Collector

These are examples only.

Inspect the actual repository and use the real current achievement definitions.

Do not assume the examples are complete.

ACHIEVEMENT IDs

Do not rename existing achievement IDs.

Do not create duplicate IDs.

Before adding an achievement:

check existing IDs
check existing definitions
check existing save data
check existing unlock logic

New IDs must be unique and follow the existing project convention.

UNLOCK LOGIC

Achievements should unlock only when their real condition is satisfied.

Do not unlock achievements merely because a screen is opened.

Do not repeatedly trigger the same achievement.

If an achievement is already unlocked:

do not award it again.

Reuse existing achievement-check functions whenever possible.

PROGRESSION

Achievements may depend on:

levels
correct answers
perfect levels
streaks
coins
points
speed
lives
subjects
mastery
Daily Challenge
Reviewer Mode

Before changing any condition, inspect the existing game-state values.

Do not create duplicate progress counters.

Do not change normal progression just to support an achievement.

REWARDS

Preserve the existing reward system.

If achievements give:

points
coins
items
titles

use the existing reward functions.

Do not create another currency or inventory system.

Prevent duplicate rewards.

An already-unlocked achievement must never repeatedly grant its reward after reload or repeated checks.

SAVE DATA

Achievement persistence is critical.

Before changing localStorage:

find the existing achievement key
find all references
inspect its structure
preserve existing data
add safe defaults if needed

Never casually rename or delete an existing key.

Never reset unrelated player data.

Never create a second achievement save system.

BACKWARD COMPATIBILITY

Existing players may already have saved achievement data.

New code must safely handle:

missing achievement data
old achievement data
new achievement definitions
already-unlocked achievements

Do not force existing players to lose achievement progress.

Use safe defaults and migration only when necessary.

DISPLAY

Achievement UI must match the existing game.

Preserve the existing visual language.

An achievement display may show:

achievement name
description
icon
locked/unlocked state
progress if supported
reward if supported

Do not redesign unrelated screens.

If the project already uses a panel/modal convention, reuse it.

If the project uses BACK instead of X, preserve that convention.

NOTIFICATIONS

If the existing system displays an unlock notification:

reuse it.

Do not create duplicate notifications.

An achievement should trigger its unlock notification only when it changes from locked to unlocked.

THREE THEMES

Achievement UI MUST work with all 3 existing themes:

original
light
dark

Check:

panel background
text
icons
cards
locked state
unlocked state
progress
buttons
borders
notifications

Never hard-code a color that breaks another theme.

MOBILE

The game is primarily used on phones.

Achievement UI must remain:

responsive
readable
touch friendly
compact

Check:

small screens
achievement cards
text wrapping
icons
buttons
panels

Avoid:

horizontal scrolling
tiny text
oversized cards
unnecessary animations

INTEGRATION

Achievements must remain compatible with:

Normal Quiz
Level Selection
Daily Challenge
Reviewer Mode
Subject Mastery
Streak system
Points
Coins
Titles
Profile
Settings
localStorage
three themes

Do not modify these systems unless required.

SPECIAL MODES

Before adding achievement triggers to:

Daily Challenge
Reviewer Mode

inspect whether the existing design already counts these modes.

Do not automatically change statistics or progression.

Do not let special modes accidentally unlock normal-progression achievements unless that is explicitly intended.

STREAKS

If an achievement depends on streaks:

reuse the existing streak value.

Do not create another streak counter.

Preserve existing streak milestones and rewards.

LEVELS

If an achievement depends on level completion:

use the existing level completion state.

Do not unlock an achievement simply because a level was selected.

Do not change the existing 80-level progression.

SUBJECTS

If an achievement depends on subjects:

use the existing subject IDs and subject progress.

Preserve:

MATH
SCIENCE
PSYCHOLOGY
TECH 1
TECH 2

and:

SUBJECT 1
SUBJECT 2

Do not create another subject structure.

QUESTION COUNTS

If an achievement depends on question counts:

use existing statistics/question counters.

Do not double-count questions from:

Normal Quiz
Daily Challenge
Reviewer Mode

unless the existing design intentionally combines them.

VALIDATION

After implementation verify:

[ ] Achievement system opens.

[ ] Existing achievements still appear.

[ ] Existing unlock state is preserved.

[ ] Existing achievement IDs remain valid.

[ ] New achievement IDs are unique.

[ ] Unlock conditions work.

[ ] Achievements do not unlock prematurely.

[ ] Already-unlocked achievements do not unlock again.

[ ] Rewards are granted once.

[ ] Achievement data survives reload.

[ ] Existing player data is preserved.

[ ] Normal Quiz still works.

[ ] Level Selection still works.

[ ] Daily Challenge still works.

[ ] Reviewer Mode still works.

[ ] Streak system still works.

[ ] Points remain correct.

[ ] Coins remain correct.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do not:

rewrite script.js
replace the achievement system
create duplicate achievement storage
create duplicate reward systems
reset existing achievement data
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

After completing a task, respond with:

DONE

Files changed: [file names]

Changes: [short summary]

Tests: [short summary]

Commit/PR: [real link if available]

Notes: [only if necessary]

Never invent commit hashes, links or test results.

FINAL RULE

READ MASTER INSTRUCTIONS.

READ GEONQUIZSCREEN INSTRUCTIONS.

INSPECT THE EXISTING ACHIEVEMENT SYSTEM.

PRESERVE EXISTING ACHIEVEMENTS.

PRESERVE SAVE DATA.

REUSE EXISTING REWARD LOGIC.

PREVENT DUPLICATE UNLOCKS AND REWARDS.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
