GEONGAMEHUB — POINTS COINS

READ FIRST

Before modifying Points or Coins, read:

../copilot-instructions.md
./geonquizscreen.md

Inspect existing code before editing.
The repository is the source of truth.

PURPOSE

Preserve and improve the existing Points and Coins systems.

Do NOT create another currency system.

POINTS VS COINS

The project has separate:

score
points
coins

Do not merge them.

Do not treat score as coins.

Do not treat points as coins.

Preserve existing meanings and storage.

CONVERSION

The existing conversion is:

100 points = 1 coin

Do not change this rate unless explicitly requested.

Before modifying conversion:

inspect the current function
inspect input handling
inspect validation
inspect coin saving
inspect Home display

CONVERSION FLOW

When converting points:

1. Validate the input.
2. Verify sufficient points.
3. Calculate the correct coin amount.
4. Deduct converted points using existing logic.
5. Add coins using existing logic.
6. Save the result.
7. Update the UI.
8. Preserve the result after reload.

Do not create duplicate conversion functions.

INPUT

The conversion input must:

accept valid numbers
reject invalid values
prevent negative values
prevent unintended decimals if current design requires whole points
handle empty input safely

Do not crash on invalid input.

REWARDS

Points and coins may come from:

quiz rewards
streak rewards
achievements
Daily Challenge
shop/items
other existing systems

Inspect existing reward functions before modifying them.

Do not duplicate rewards.

Do not award the same event twice.

SHOP

The project contains an item/shop system.

If shop purchases use coins:

reuse existing inventory and currency logic.

Do not create another coin balance.

SAVE DATA

Before changing localStorage:

find points keys
find coins keys
find conversion keys if present
find all references
inspect stored structures

Never casually rename keys.

Never reset existing balances.

Never overwrite unrelated save data.

Preserve existing player data after reload.

BACKWARD COMPATIBILITY

Existing players may already have saved:

points
coins
inventory
conversion progress

New code must preserve these values.

Use safe defaults only when necessary.

QUIZ INTEGRATION

Reuse the existing quiz reward system.

Do not rewrite quiz logic just to modify currency.

Ensure:

correct answers
level completion
streaks
achievements
special modes

continue using the existing reward architecture.

DAILY CHALLENGE

Inspect whether Daily Challenge already awards points/coins.

Preserve its current behavior.

Do not accidentally award normal level rewards twice.

REVIEWER MODE

Inspect whether Reviewer Mode currently awards currency.

Do not change it unless explicitly requested.

LEVEL SELECTION

Selecting a level must not award points or coins.

Rewards should occur only through existing game events.

THREE THEMES

Points/Coins UI must support:

original
light
dark

Check:

balance display
conversion panel
input
buttons
messages
cards
text
icons
borders

Keep all text readable.

MOBILE

The UI must remain:

responsive
compact
readable
touch friendly

Check:

conversion input
buttons
balance display
small screens

Avoid horizontal scrolling.

VALIDATION

Verify:

[ ] Points display correctly.

[ ] Coins display correctly.

[ ] Conversion accepts valid input.

[ ] Invalid input is handled safely.

[ ] Conversion uses 100 points = 1 coin.

[ ] Points are deducted correctly.

[ ] Coins are added correctly.

[ ] Conversion saves correctly.

[ ] Reload preserves balances.

[ ] Quiz rewards still work.

[ ] Streak rewards still work.

[ ] Achievement rewards still work.

[ ] Daily Challenge still works.

[ ] Reviewer Mode still works.

[ ] Shop/items still work.

[ ] Original theme works.

[ ] Light theme works.

[ ] Dark theme works.

[ ] Mobile layout works.

[ ] No unrelated files were modified.

CHANGE POLICY

Make the smallest safe change.

Do not:

create another currency
create another conversion system
reset balances
rewrite the quiz engine
rewrite the shop
rename save keys unnecessarily
modify unrelated features
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

INSPECT EXISTING POINTS AND COINS CODE.

PRESERVE SCORE, POINTS AND COINS AS SEPARATE SYSTEMS.

PRESERVE 100 POINTS = 1 COIN.

PRESERVE SAVE DATA.

PREVENT DUPLICATE REWARDS.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
