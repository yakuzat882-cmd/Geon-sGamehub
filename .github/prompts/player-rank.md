GEONGAMEHUB — PLAYER RANK

READ FIRST

Before modifying Player Rank, read:

- "../copilot-instructions.md"
- "./geonquizscreen.md"
- "./save-system.md"

The current repository code is the source of truth.

Inspect the actual rank implementation before editing.

PURPOSE

Preserve and improve the existing Player Rank system.

Do NOT create a second ranking/progression system.

BEFORE EDITING

Inspect:

- rank variables
- rank definitions
- rank thresholds
- level progress
- points
- score
- achievements
- streak
- mastery
- titles
- Home UI
- rank UI
- localStorage keys
- reward functions

Search every reference before changing rank calculations.

EXISTING ARCHITECTURE

Do not assume how Rank is calculated.

Inspect the actual repository.

Determine whether rank is based on:

- levels
- points
- score
- achievements
- mastery
- another existing metric

Use the existing implementation.

Do not invent a new formula unless explicitly requested.

RANK CALCULATION

If modifying rank calculation:

1. inspect the current formula
2. inspect all callers
3. inspect saved rank data
4. identify dependent UI
5. identify reward dependencies
6. make the smallest safe change

Do not double-count the same progress.

PROGRESSION

Rank must remain compatible with existing:

- 80-level system
- subject progress
- SUBJECT 1
- SUBJECT 2
- question-bank separation
- quiz types

Do not automatically unlock levels because of rank.

Do not modify level progression unless explicitly requested.

POINTS / SCORE

If rank uses points or score:

use the existing values.

Do not create a second points or score counter.

Keep:

score
points
coins

separate.

Preserve:

"100 points = 1 coin"

unless explicitly requested otherwise.

ACHIEVEMENTS

If achievements affect rank:

reuse the existing achievement system.

Do not create duplicate achievement storage.

Do not repeatedly trigger rank rewards.

MASTERY

If Subject Mastery affects rank:

reuse the existing mastery data.

Do not create another mastery calculation.

Do not double-count SUBJECT 1 and SUBJECT 2.

STREAK

If streak affects rank:

reuse the existing streak system.

Do not create another streak counter.

Do not reset best streak.

TITLES

If Rank and Titles are connected:

reuse the existing title system.

Do not create duplicate title storage.

REWARDS

If rank changes grant rewards:

reuse existing:

- points
- coins
- items
- achievements
- titles

Prevent duplicate rewards.

Do not create another reward system.

SAVE DATA

Before modifying rank persistence:

find the existing localStorage key(s).

Search all reads/writes.

Preserve existing player data.

If rank is calculated dynamically and is not currently saved:

do not create unnecessary saved rank data.

If rank is already saved:

preserve its structure.

HOME UI

If Rank appears on Home:

preserve the existing layout.

Update only the necessary:

- rank label
- progress
- progress bar
- related information

Do not redesign Home.

LEVEL SELECTION

Rank must not break Level Selection.

Selecting a level must not falsely increase rank.

Only valid existing progression events should affect rank.

SPECIAL MODES

Inspect:

- Daily Challenge
- Reviewer Mode

Do not automatically include or exclude them from rank.

Follow the actual existing architecture.

Do not let special modes corrupt normal rank progression.

THREE THEMES

Rank UI must support:

- original
- light
- dark

Check:

- rank card
- progress
- text
- borders
- icons
- buttons
- selected states

Keep all text readable.

MOBILE

Rank UI must remain:

- responsive
- compact
- readable
- touch friendly

Avoid:

- horizontal scrolling
- oversized rank panels
- tiny labels
- text overflow

VALIDATION

After implementation verify:

[ ] Rank displays correctly.

[ ] Rank calculation uses the existing architecture.

[ ] Rank does not double-count progress.

[ ] Level progress remains correct.

[ ] Subject progress remains correct.

[ ] Points remain correct.

[ ] Coins remain correct.

[ ] Achievements remain correct.

[ ] Mastery remains correct.

[ ] Streak remains correct.

[ ] Titles remain correct.

[ ] Rewards are not duplicated.

[ ] Save/reload works.

[ ] Normal Quiz works.

[ ] Level Selection works.

[ ] Daily Challenge works.

[ ] Reviewer Mode works.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do NOT:

- create another rank system
- invent a new formula unnecessarily
- create duplicate save data
- create duplicate rewards
- rewrite the quiz engine
- redesign Home
- modify unrelated progression
- add unnecessary libraries

Inspect first.

Reuse existing systems.

Change only what is required.

RESPONSE

The user works mainly from a phone.

Do not paste huge code blocks.

After completion:

DONE

Files changed: [files]

Changes: [short summary]

Tests: [short summary]

Commit/PR: [real link if available]

Notes: [only if necessary]

Never invent commits, links or test results.

FINAL RULE

READ MASTER INSTRUCTIONS.

INSPECT ACTUAL PLAYER RANK CODE.

PRESERVE EXISTING RANK LOGIC.

DO NOT INVENT A SECOND RANK SYSTEM.

PRESERVE SAVE DATA.

REUSE EXISTING POINTS, ACHIEVEMENTS, MASTERY AND STREAK SYSTEMS.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
