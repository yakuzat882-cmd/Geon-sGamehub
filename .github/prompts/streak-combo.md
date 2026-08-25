GEONGAMEHUB — STREAK COMBO

READ FIRST

Before modifying Streak or Combo, read:

../copilot-instructions.md
./geonquizscreen.md

The current repository code is the source of truth.

Inspect existing code before editing.
Do not guess the architecture.

PURPOSE

Preserve and improve the existing streak/combo system.

Do NOT create a second streak or combo system.

BEFORE EDITING

Inspect:

index.html
style.css
script.js

Find:

streak variables
combo variables
best streak
streak milestones
combo UI
streak rewards
points/coins rewards
achievement checks
localStorage keys
quiz answer handling
timeout handling
level completion

Search every reference before changing existing variables or functions.

EXISTING STREAK

The current project has streak milestones including:

3
5
10
15
20

Preserve existing milestones unless explicitly requested.

Do not assume these are the only milestones.
Inspect the actual implementation first.

STREAK RULES

A correct answer may increase the existing streak.

An incorrect answer or existing reset condition must use the current project behavior.

Do not change reset behavior without inspecting the current logic.

Do not create another streak counter.

BEST STREAK

Preserve existing best-streak behavior.

Best streak must not decrease because of reload.

Do not reset best streak accidentally.

Save best streak using the existing storage system.

COMBO

If the project has a separate combo system:

inspect how it currently works.

Do not assume combo equals streak.

Preserve the existing distinction if both systems exist.

Do not create duplicate combo variables.

REWARDS

Preserve existing streak/combo rewards.

Rewards may include:

score
points
coins
achievements
other existing rewards

Reuse existing reward functions.

Do not create another reward system.

Prevent duplicate rewards.

A milestone must not repeatedly reward the player after reload or repeated checks.

QUIZ INTEGRATION

Streak/combo must work with the existing quiz engine.

Reuse existing:

answer validation
question progression
score handling
points
coins
lives
timer
completion logic

Do not rewrite the quiz engine.

Do not change question-bank structure.

SPECIAL MODES

Inspect how the existing system treats:

Normal Quiz
Daily Challenge
Reviewer Mode

Do not automatically change special-mode behavior.

If Daily Challenge or Reviewer Mode intentionally uses streak/combo, preserve that behavior.

Otherwise keep their state isolated.

LEVELS

Do not let selecting a level change streak/combo.

Only actual quiz events should affect streak/combo according to the existing implementation.

Do not change the 80-level progression.

ACHIEVEMENTS

If streak milestones trigger achievements:

reuse the existing achievement system.

Do not create duplicate achievement storage.

Do not trigger the same achievement repeatedly.

POINTS AND COINS

If streak rewards points or coins:

use the existing points/coins system.

Do not create another currency.

Do not modify the existing conversion rate unless explicitly requested.

SAVE DATA

Before changing localStorage:

find the existing streak/combo keys
find all references
inspect stored data
preserve existing values
add safe defaults if necessary

Never casually rename existing keys.

Never reset unrelated player data.

THREE THEMES

All streak/combo UI must support:

original
light
dark

Check:

streak display
combo display
milestone notifications
reward notifications
text
icons
backgrounds
borders
buttons

Never hard-code a color that breaks another theme.

MOBILE

The game is primarily used on phones.

Keep streak/combo UI:

responsive
readable
compact
touch friendly

Avoid:

text overflow
oversized notifications
tiny text
horizontal scrolling

VALIDATION

After implementation verify:

[ ] Correct answers affect streak correctly.

[ ] Incorrect/reset conditions work correctly.

[ ] Best streak is preserved.

[ ] Existing milestones still work.

[ ] Combo works if present.

[ ] Rewards are not duplicated.

[ ] Points remain correct.

[ ] Coins remain correct.

[ ] Achievements remain correct.

[ ] Save survives reload.

[ ] Normal Quiz works.

[ ] Daily Challenge works.

[ ] Reviewer Mode works.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do not:

rewrite script.js
create another streak system
create another combo system
create another reward system
reset saved streaks
change unrelated progression
redesign unrelated UI
add unnecessary libraries

Inspect first.
Reuse existing systems.
Change only what is required.

RESPONSE

The user works mainly from a phone.

Do not paste huge code blocks.

After completing a task:

DONE

Files changed: [file names]

Changes: [short summary]

Tests: [short summary]

Commit/PR: [real link if available]

Notes: [only if necessary]

Never invent links, commits or test results.

FINAL RULE

READ MASTER INSTRUCTIONS.

READ GEONQUIZSCREEN INSTRUCTIONS.

INSPECT EXISTING STREAK/COMBO CODE.

PRESERVE EXISTING MILESTONES.

PRESERVE BEST STREAK.

REUSE EXISTING REWARDS AND SAVE DATA.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
