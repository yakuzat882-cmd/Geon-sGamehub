GEONGAMEHUB — EXPORT IMPORT SAVE

READ FIRST

Before modifying Export/Import Save, read:

- "../copilot-instructions.md"
- "./geonquizscreen.md"
- "./save-system.md"

The current repository code is the source of truth.

Inspect the existing implementation before editing.

PURPOSE

Protect the player's ability to export and import saved game data.

Reuse the existing save architecture.

Do NOT create a second save format unless explicitly requested.

BEFORE EDITING

Inspect:

- save functions
- load functions
- localStorage keys
- export functions
- import functions
- JSON serialization
- JSON parsing
- validation
- reset functions
- profile data
- settings
- progress
- rewards
- achievements
- mastery
- inventory
- Daily Challenge
- Reviewer Mode

Search all references before modifying export/import behavior.

EXPORT

Export must represent the existing player save state accurately.

Before changing export:

inspect exactly which data the current system saves.

Do not invent fields.

Do not omit important existing player data.

Preserve the current save architecture.

IMPORT

Import must:

1. receive the save data
2. validate the format
3. verify required structures
4. preserve compatible fields
5. reject unsafe/invalid data safely
6. save using the existing save system
7. reload/update the game state correctly

Do not crash on malformed input.

VALIDATION

Never blindly import arbitrary JSON into the game.

Check:

- expected structure
- expected data types
- valid progress ranges
- valid numeric values
- valid arrays/objects
- known fields

Unknown fields may be preserved only if compatible with the existing architecture.

Do not allow invalid data to corrupt unrelated save data.

PLAYER PROGRESS

Preserve existing:

- levels
- subjects
- SUBJECT 1
- SUBJECT 2
- question-bank separation
- points
- coins
- score
- streak
- achievements
- mastery
- titles
- inventory
- profile
- settings

Only preserve systems actually present in the current repository.

LEVEL SAFETY

Imported data must not accidentally:

- unlock invalid levels
- create impossible progress
- change existing level IDs
- exceed existing progress limits

Use the existing validation rules.

Do not invent new progression rules.

CURRENCY SAFETY

Preserve:

- score
- points
- coins

Do not merge balances.

Do not create duplicate currency storage.

Preserve the existing conversion:

"100 points = 1 coin"

unless explicitly requested otherwise.

INVENTORY SAFETY

If inventory is imported:

validate item data using the existing inventory structure.

Do not create invalid item IDs.

Do not create negative item counts.

Do not overwrite unrelated data accidentally.

ACHIEVEMENTS / MASTERY / TITLES

Preserve existing structures.

Do not duplicate unlocked achievements.

Do not create impossible mastery values.

Do not erase existing title progress.

PROFILE / SETTINGS

Import must correctly preserve compatible:

- profile
- theme
- sound
- settings

Do not break the current theme system.

DAILY CHALLENGE

Inspect the existing Daily Challenge save structure.

Do not import Daily Challenge data in a way that:

- corrupts the current challenge
- breaks date logic
- duplicates rewards
- overwrites normal quiz progression

Follow the existing architecture.

REVIEWER MODE

Preserve compatible Reviewer Mode state if it is currently saved.

Do not allow imported Reviewer data to overwrite normal progression.

BACKWARD COMPATIBILITY

Older exports may not contain newer fields.

Handle missing fields safely.

Do not reject an otherwise valid old save merely because newer optional fields are absent.

Use existing defaults.

SECURITY / SAFETY

Do not execute imported data as JavaScript.

Do not use dynamic code execution.

Treat imported data as data only.

Do not trust imported values blindly.

USER EXPERIENCE

Export and Import UI should follow the existing project style.

Preserve existing:

- buttons
- dialogs
- navigation
- labels

Do not redesign unrelated screens.

If an import fails, show a clear existing-style error.

Do not silently destroy the current save.

BACKUP SAFETY

If the architecture permits safe backup before import:

preserve the current save until the imported data has passed validation.

Do not overwrite valid player data with invalid input.

THREE THEMES

Export/Import UI must support:

- original
- light
- dark

Check:

- text
- buttons
- dialogs
- borders
- inputs
- error messages
- success messages

MOBILE

The game is primarily used on phones.

Check:

- import controls
- export button
- dialogs
- text wrapping
- button size
- small screens

Avoid horizontal scrolling.

VALIDATION

After implementation verify:

[ ] Export works.

[ ] Export contains the required existing save data.

[ ] Export does not invent unrelated fields.

[ ] Import accepts valid save data.

[ ] Invalid data is rejected safely.

[ ] Malformed data does not crash the game.

[ ] Existing save is not destroyed by failed import.

[ ] Imported progress is restored.

[ ] Points are restored correctly.

[ ] Coins are restored correctly.

[ ] Achievements are restored correctly.

[ ] Mastery is restored correctly.

[ ] Titles are restored correctly.

[ ] Inventory is restored correctly.

[ ] Profile is restored correctly.

[ ] Settings are restored correctly.

[ ] Daily Challenge remains valid.

[ ] Reviewer Mode remains valid.

[ ] Normal Quiz still works.

[ ] Level Selection still works.

[ ] All 3 themes work.

[ ] Reload preserves imported data.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do NOT:

- replace the save architecture
- create duplicate save formats
- blindly import JSON
- execute imported data
- reset current save on invalid input
- rewrite unrelated quiz systems
- redesign unrelated UI
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

Never invent links, commits or test results.

FINAL RULE

READ MASTER INSTRUCTIONS.

READ SAVE SYSTEM INSTRUCTIONS.

INSPECT ACTUAL EXPORT/IMPORT CODE.

PRESERVE THE EXISTING SAVE FORMAT.

VALIDATE IMPORTED DATA.

NEVER EXECUTE IMPORTED DATA AS CODE.

PROTECT THE CURRENT PLAYER SAVE.

TEST EXPORT, IMPORT AND RELOAD.

MAKE THE SMALLEST SAFE CHANGE.
