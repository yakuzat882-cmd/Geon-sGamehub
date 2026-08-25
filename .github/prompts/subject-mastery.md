GEONGAMEHUB — SUBJECT MASTERY

READ FIRST

Before implementing or modifying Subject Mastery, read:

../copilot-instructions.md

Then read:

./geonquizscreen.md

Also inspect the existing mastery, progress, subject and save systems.

The current repository code is the source of truth.

Do not guess the architecture.

PURPOSE

Subject Mastery tracks the player's progress and mastery for each existing subject.

Improve or extend the existing system without creating a second progression system.

Do NOT replace the existing subject progress.

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

subject data
subject IDs
SUBJECT 1 / SUBJECT 2
level progress
mastery functions
mastery tiers
completion checks
Home progress display
localStorage keys
reward functions
title functions
achievement functions

Search all references before changing IDs, functions or storage keys.

SUBJECT STRUCTURE

Existing subjects:

MATH
SCIENCE
PSYCHOLOGY
TECH 1
TECH 2

Each subject contains:

SUBJECT 1
SUBJECT 2

Preserve this structure.

Do not merge subjects.

Do not create another subject database.

Do not rename existing subject IDs.

PROGRESS

The normal progression uses 80 levels/questions per quiz type.

Existing progress must remain compatible with the 0–80 range.

Before changing progress calculations:

find the existing progress function
find all callers
find Home screen references
find localStorage references

Do not create another progress counter.

SUBJECT SEPARATION

Subject Mastery must keep progress separated by:

subject
SUBJECT 1 / SUBJECT 2
existing quiz/questioner type

Do not allow progress from one subject to increase another subject's mastery.

Do not allow SUBJECT 1 progress to overwrite SUBJECT 2 progress.

Do not merge previous/new question-bank progress accidentally.

MASTERY TIERS

Inspect the actual existing mastery tiers before modifying them.

Do not assume tier names, thresholds or rewards.

Preserve existing mastery definitions.

If new tiers are explicitly requested:

use the existing architecture
use unique IDs
keep thresholds consistent
avoid duplicate tiers

Do not rewrite the entire mastery system.

MASTERY CALCULATION

Use the existing level/progress data whenever possible.

Do not create a second calculation based on unrelated question counts.

If mastery is based on completed levels, use the existing completion state.

If mastery is based on percentage/progress, use the existing calculation.

Do not count the same progress twice.

HOME DISPLAY

If Subject Mastery appears on Home:

reuse the existing subject progress UI.

Do not redesign the entire Home screen.

Mastery changes should update the correct subject only.

Check:

subject name
progress
mastery tier
progress bar
colors
icons
labels

Do not break existing Home controls.

REWARDS

If mastery gives rewards:

reuse existing points, coins, items, titles or achievement systems.

Do not create a new currency.

Do not create duplicate reward storage.

Prevent the same mastery reward from being granted repeatedly.

Before changing rewards:

find existing reward functions
find existing reward storage
find existing callers

SAVE DATA

Save compatibility is critical.

Before changing localStorage:

find the existing mastery/progress keys
find all references
inspect the stored structure
preserve existing data
add safe defaults if necessary

Never casually rename existing keys.

Never reset the player's save.

Never overwrite unrelated progress.

Do not create a second save system.

BACKWARD COMPATIBILITY

Existing players may have saved progress without newer mastery fields.

Handle missing data safely.

Use defaults only where required.

Do not erase existing progress because a new mastery field is missing.

LEVEL COMPLETION

Subject Mastery must use the existing level completion system.

Selecting a level must not increase mastery.

Only valid existing completion/progress events should affect mastery.

Do not create fake completions.

Do not automatically unlock levels.

QUESTION COUNTS

If mastery uses question statistics:

inspect the existing statistics system first.

Prevent double counting.

Do not automatically combine:

Normal Quiz
Daily Challenge
Reviewer Mode

unless the existing design explicitly counts them together.

SPECIAL MODES

Daily Challenge and Reviewer Mode are separate systems.

Do not allow them to accidentally corrupt Subject Mastery.

If they are intentionally included in mastery:

reuse existing mode-aware tracking.

Otherwise keep them separate.

STREAKS

If mastery interacts with streaks:

reuse the existing streak system.

Do not create another streak counter.

Do not reset streaks incorrectly.

ACHIEVEMENTS

If mastery unlocks achievements:

reuse the existing achievement system.

Do not create duplicate achievement storage.

Do not trigger the same achievement repeatedly.

TITLES

If mastery affects titles:

reuse the existing title system.

Do not create a second title system.

Preserve existing title progress.

THREE THEMES

Subject Mastery MUST work with all 3 themes:

original
light
dark

Check:

progress bars
mastery labels
cards
text
icons
backgrounds
borders
selected states
completed states

Never hard-code a color that becomes unreadable in another theme.

MOBILE

The game is primarily used on phones.

Mastery UI must remain:

responsive
readable
compact
touch friendly

Check:

small screens
subject rows
progress bars
labels
mastery cards

Avoid:

horizontal scrolling
tiny text
oversized cards
unnecessary animations

COMPATIBILITY

Subject Mastery must remain compatible with:

Normal Quiz
Level Selection
Daily Challenge
Reviewer Mode
Achievements
Streak system
Points
Coins
Titles
Profile
Settings
localStorage
all 3 themes

Do not modify unrelated systems.

ERROR HANDLING

If mastery data is missing or invalid:

do not crash the game.

Use safe existing defaults.

Do not reset unrelated save data.

Do not invent fake progress.

VALIDATION

After implementation verify:

[ ] Subject Mastery displays correctly.

[ ] All 5 subjects remain separate.

[ ] SUBJECT 1 works.

[ ] SUBJECT 2 works.

[ ] Progress remains 0–80.

[ ] Existing level progress is preserved.

[ ] Selecting a level does not increase mastery.

[ ] Completing a valid level updates mastery correctly.

[ ] Mastery tiers use the existing definitions.

[ ] Rewards are not duplicated.

[ ] Save data survives reload.

[ ] Existing player progress is preserved.

[ ] Home display updates correctly.

[ ] Normal Quiz still works.

[ ] Level Selection still works.

[ ] Daily Challenge still works.

[ ] Reviewer Mode still works.

[ ] Achievements still work.

[ ] Titles still work.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do not:

rewrite script.js
replace the progression system
create another mastery system
create duplicate localStorage
reset player progress
create duplicate rewards
redesign Home
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

INSPECT THE EXISTING MASTERY SYSTEM.

PRESERVE SUBJECT 1 / SUBJECT 2.

PRESERVE EXISTING PROGRESS.

REUSE EXISTING SAVE AND REWARD SYSTEMS.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
