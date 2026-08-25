GEONGAMEHUB — SAVE SYSTEM

READ FIRST

Before modifying the Save System, read:

- "../copilot-instructions.md"
- "./geonquizscreen.md"

The current repository code is the source of truth.

Inspect the actual implementation before editing.

Never guess localStorage keys, save structures, functions or dependencies.

PURPOSE

Protect the existing player save system.

Reuse the existing save/load architecture.

Do NOT create a second save system.

Do NOT replace working persistence with a new architecture unless explicitly requested.

BEFORE EDITING

Inspect:

- "index.html"
- "style.css"
- "script.js"
- "questions.json"
- "questions.new.json"
- "questions.embedded.js"
- "questions.new.embedded.js"

Search the repository for:

- "localStorage"
- save functions
- load functions
- reset functions
- default data
- migration logic
- profile data
- settings data
- progress data
- level data
- points
- coins
- streak
- achievements
- mastery
- titles
- inventory
- Daily Challenge
- Reviewer Mode

Find every reference before changing an existing key or data structure.

SOURCE OF TRUTH

The actual current JavaScript implementation has priority over this document.

If this prompt conflicts with the current repository:

1. inspect the actual code
2. identify the conflict
3. preserve working behavior
4. make the smallest safe change
5. explain the conflict if necessary

LOCALSTORAGE

Never casually:

- rename an existing key
- delete an existing key
- reset all data
- overwrite unrelated data
- create duplicate keys for the same feature

Before changing a key:

1. find its definition
2. find every read
3. find every write
4. inspect its stored structure
5. check dependencies
6. preserve backward compatibility

PLAYER DATA

Preserve existing player information, including any systems actually present in the repository:

- quiz progress
- level progress
- subject progress
- selected level
- score
- points
- coins
- streak
- best streak
- achievements
- mastery
- titles
- inventory
- profile
- settings
- theme
- sound settings
- Daily Challenge
- Reviewer Mode
- other existing saved state

Do not assume every item above uses the same storage key.

Inspect the actual implementation.

SAVE STRUCTURE

Do not create a new master save object if the project already has separate storage systems.

If the project already uses separate keys:

preserve them.

If the project already uses one combined object:

preserve that architecture.

Do not migrate everything unnecessarily.

LOAD PROCESS

When the game starts, preserve the existing load order.

A safe load process should:

1. read existing data
2. validate required structures
3. detect missing optional fields
4. apply safe defaults
5. preserve valid existing values
6. update the appropriate UI

Do not erase valid data because an optional field is missing.

BACKWARD COMPATIBILITY

Existing players may have older saved data.

If a new field is required:

- detect whether it exists
- add a safe default only if missing
- preserve all existing fields
- save the compatible result

Never force old players to start over.

Never reset unrelated progress during migration.

INVALID DATA

If saved data is malformed:

do not crash the entire game.

Use the safest existing recovery behavior.

Do not silently replace all player data with a blank save.

Do not invent progress.

If recovery could cause data loss, preserve the original data when the architecture allows it.

QUIZ DATA

Save-system changes must not break:

- question loading
- answer validation
- current question
- timer
- lives
- score
- points
- coins
- level completion
- quiz progression

Do not rewrite the quiz engine merely to modify persistence.

LEVEL PROGRESS

Preserve the existing level architecture.

Do not:

- reset completed levels
- unlock levels automatically
- change level IDs
- change progress ranges
- overwrite selected level

Unless the task explicitly requires such behavior.

SUBJECT PROGRESS

Preserve separation between:

- MATH
- SCIENCE
- PSYCHOLOGY
- TECH 1
- TECH 2

Also preserve:

- SUBJECT 1
- SUBJECT 2
- existing question-bank separation
- existing quiz-type separation

Do not merge progress accidentally.

POINTS AND COINS

Preserve the existing currency architecture.

Keep:

- score
- points
- coins

as separate concepts.

The existing conversion is:

"100 points = 1 coin"

Do not change it unless explicitly requested.

STREAK AND ACHIEVEMENTS

Preserve:

- current streak
- best streak
- streak milestones
- achievement completion

Do not reset streak or achievement data during save migration.

Reuse existing reward/save functions.

MASTERY AND TITLES

Preserve existing:

- Subject Mastery
- title progress
- title unlock state

Do not create duplicate storage.

Do not recalculate existing progress incorrectly.

INVENTORY

If the project contains item inventory:

preserve existing item counts.

Do not create a second inventory object.

Do not reset purchased items.

Inspect existing item keys before changing inventory storage.

PROFILE AND SETTINGS

Preserve:

- selected profile
- theme
- sound
- music
- other existing preferences

Do not reset user preferences when adding new settings.

DAILY CHALLENGE

Daily Challenge must remain isolated from normal progression.

Preserve its existing:

- date state
- question state
- progress
- completion state
- reward state

Do not let save changes overwrite normal quiz progress.

REVIEWER MODE

Reviewer Mode must remain compatible with its existing persistence behavior.

Do not allow Reviewer Mode to overwrite normal level progress.

Do not change its storage behavior unless explicitly required.

SAVE TIMING

Use the existing save architecture.

Important state changes may include:

- quiz completion
- rewards
- profile changes
- settings changes
- achievements
- mastery
- streak
- inventory
- Daily Challenge completion

Do not add unnecessary duplicate save operations.

RESET FUNCTIONS

Before modifying any reset function:

inspect exactly what it resets.

Never assume a function named reset means reset everything.

Do not allow a feature-specific reset to erase unrelated player data.

EXPORT / IMPORT COMPATIBILITY

If Export/Import Save already exists:

preserve its current structure.

Do not change stored field names without checking import compatibility.

If a save format changes:

provide backward-compatible handling when possible.

THREE THEMES

Save changes must preserve persistence of:

- original
- light
- dark

After reload, the selected theme must still apply correctly.

Do not create a second theme-storage system.

MOBILE

The game is primarily used on phones.

If save/load messages are visible:

keep them:

- compact
- readable
- responsive
- touch friendly

Do not add unnecessary large dialogs.

TESTING

After implementation verify:

[ ] Existing save data loads.

[ ] New data saves.

[ ] Reload preserves data.

[ ] Missing optional fields receive safe defaults.

[ ] Existing progress is preserved.

[ ] Level progress is preserved.

[ ] Subject progress is preserved.

[ ] Points remain correct.

[ ] Coins remain correct.

[ ] Streak remains correct.

[ ] Achievements remain correct.

[ ] Mastery remains correct.

[ ] Titles remain correct.

[ ] Inventory remains correct.

[ ] Profile remains correct.

[ ] Settings remain correct.

[ ] Daily Challenge remains correct.

[ ] Reviewer Mode remains correct.

[ ] Normal Quiz still works.

[ ] Level Selection still works.

[ ] All 3 themes still work.

[ ] Mobile layout is unaffected.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do NOT:

- rewrite "script.js"
- replace the save architecture
- rename keys unnecessarily
- reset player data
- create duplicate storage
- modify unrelated progression
- redesign unrelated UI
- add unnecessary libraries

Inspect first.

Understand dependencies.

Reuse existing systems.

Change only what the task requires.

RESPONSE

The user works mainly from a phone.

Do not paste entire modified files.

Do not paste huge code blocks.

After completion respond with:

DONE

Files changed: [files]

Changes: [short summary]

Tests: [short summary]

Commit/PR: [real GitHub link if available]

Notes: [only if necessary]

Never invent:

- commit hashes
- PR numbers
- GitHub links
- test results

FINAL RULE

READ MASTER INSTRUCTIONS.

INSPECT THE ACTUAL SAVE SYSTEM.

PRESERVE EXISTING STORAGE KEYS.

PRESERVE EXISTING PLAYER DATA.

USE BACKWARD-COMPATIBLE DEFAULTS.

DO NOT CREATE A SECOND SAVE SYSTEM.

DO NOT RESET UNRELATED DATA.

TEST SAVE AND RELOAD.

MAKE THE SMALLEST SAFE CHANGE.
