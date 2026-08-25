GEONGAMEHUB — PROFILE SETTINGS

READ FIRST

Before modifying Profile or Settings, read:

../copilot-instructions.md
./geonquizscreen.md

Inspect the existing implementation before editing.

The repository is the source of truth.

PURPOSE

Preserve and improve the existing Profile and Settings systems.

Do NOT create duplicate profile or settings systems.

BEFORE EDITING

Inspect:

index.html
style.css
script.js

Find:

profile UI
profile button
profile selector
emoji/profile choices
save button
back button
settings panel
theme settings
sound settings
other settings
localStorage keys
event listeners
Home screen references

Search all references before changing IDs, classes, functions or storage keys.

PROFILE

The Home screen has a clickable profile area.

If modifying it:

preserve the existing profile mechanism
preserve the Home display
reuse existing profile state
save the selected profile
restore it after reload

Do not create another profile storage system.

PROFILE CHOICES

If the project uses emoji profile icons:

preserve the existing choices.

Existing examples may include:

🥷
💂
🫅
🧑‍✈️
🧑‍🔬
🧑‍⚕️
🧑‍🔧
🧑‍🏭
🧑‍🌾
🧑‍🏫
🧑‍🎓
🧑‍💼
🧑‍⚖️
🧑‍💻
🧑‍🎤
🧑‍🎨
🧑‍🍳
👳

Inspect the actual repository before assuming the list is complete.

Do not remove existing choices unless explicitly requested.

PROFILE SAVE

When the player selects a profile:

1. Select the profile.
2. Save using the existing save system.
3. Close/return using the existing navigation behavior.
4. Update the Home profile display.
5. Preserve the selection after reload.

Do not save only in temporary memory.

Do not reset other player data.

NAVIGATION

If the current profile panel uses:

BACK
SAVE

preserve that convention.

Do not add an unnecessary X button.

Do not change unrelated navigation.

SETTINGS

Inspect all existing settings before modifying them.

Preserve existing:

theme
sound
music
effects
language if present
other existing settings

Do not assume the settings list is complete.

Do not create duplicate settings keys.

THEMES

The project supports:

original
light
dark

Theme selection must use the existing theme system.

Do not create a second theme engine.

When changing theme UI:

verify the selected theme persists
verify the theme applies after reload
verify text remains readable
verify buttons remain readable
verify panels remain readable

Do not hard-code colors that break another theme.

SOUND

If sound/music settings exist:

reuse the existing audio system.

Do not create another audio manager.

Changing sound settings must not break quiz audio or existing effects.

SAVE DATA

Before changing localStorage:

find profile keys
find settings keys
find theme keys
find audio keys
find all references

Understand the existing stored structure.

Never casually rename keys.

Never reset unrelated player data.

Preserve existing saves.

BACKWARD COMPATIBILITY

Existing players may have saved:

profile
theme
sound settings
other preferences

Missing new settings must receive safe defaults.

Existing settings must remain unchanged.

Do not wipe player preferences.

HOME INTEGRATION

After profile/settings changes:

Home must display the correct profile.

Theme changes must update the entire existing UI.

Settings must not break:

quiz
levels
progress
rewards
Daily Challenge
Reviewer Mode
Achievements
Mastery

Do not redesign Home unnecessarily.

MOBILE

The game is primarily used on phones.

Profile and Settings UI must be:

responsive
readable
touch friendly
compact

Check:

profile grid
buttons
panels
inputs
small screens

Avoid:

horizontal scrolling
tiny buttons
oversized panels
text overflow

THREE THEMES

Profile and Settings must work in:

original
light
dark

Check:

panel
profile icons
selected state
buttons
text
inputs
borders
backgrounds
settings controls

VALIDATION

Verify:

[ ] Profile panel opens.

[ ] Existing profile choices work.

[ ] Profile can be selected.

[ ] Save works.

[ ] Home displays selected profile.

[ ] Profile survives reload.

[ ] Back works.

[ ] Settings open correctly.

[ ] Existing settings still work.

[ ] Theme selection works.

[ ] Theme persists after reload.

[ ] Sound settings work if present.

[ ] Existing audio behavior is preserved.

[ ] Normal Quiz works.

[ ] Level Selection works.

[ ] Daily Challenge works.

[ ] Reviewer Mode works.

[ ] Achievements work.

[ ] Subject Mastery works.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do not:

create another profile system
create another settings system
create another theme system
create another audio system
reset saved preferences
rewrite script.js
redesign Home unnecessarily
add unnecessary libraries
modify unrelated features

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

INSPECT EXISTING PROFILE AND SETTINGS CODE.

PRESERVE EXISTING PROFILE DATA.

PRESERVE EXISTING SETTINGS.

REUSE EXISTING THEME AND AUDIO SYSTEMS.

PRESERVE SAVE DATA.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
