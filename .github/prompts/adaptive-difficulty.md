GEONGAMEHUB — ADAPTIVE DIFFICULTY

READ FIRST

Before modifying Adaptive Difficulty, read:

- "../copilot-instructions.md"
- "./geonquizscreen.md"
- "./level-selection.md"
- "./save-system.md"

The current repository code is the source of truth.

Inspect the existing question and level system before editing.

PURPOSE

If Adaptive Difficulty is implemented or modified, it must work with the existing quiz architecture.

Do NOT create a second quiz engine.

Do NOT replace the existing 80-level progression.

BEFORE EDITING

Inspect:

- question loading
- question selection
- level selection
- subject selection
- question-bank selection
- answer validation
- score
- timer
- lives
- streak
- progress
- question history
- used-question tracking
- difficulty fields if present
- localStorage
- quiz mode

Search every reference before modifying question selection.

CURRENT QUESTION SYSTEM

The project contains:

- "questions.json"
- "questions.new.json"
- "questions.embedded.js"
- "questions.new.embedded.js"

Do not merge these accidentally.

Do not delete questions.

Do not duplicate question objects.

Inspect the actual question structure before using difficulty data.

DIFFICULTY DATA

Do not assume that a question has a difficulty field.

Inspect the actual JSON structure.

If difficulty already exists:

reuse it.

If difficulty does not exist:

do not invent a parallel question database.

Any new difficulty metadata must fit the existing question structure and must be explicitly required by the task.

LEVEL COMPATIBILITY

The normal game uses an existing 80-level progression.

Adaptive Difficulty must NOT:

- change level IDs
- unlock levels automatically
- skip required progression
- alter completed-level state
- overwrite level progress

unless explicitly requested.

SUBJECT COMPATIBILITY

Preserve:

- MATH
- SCIENCE
- PSYCHOLOGY
- TECH 1
- TECH 2

and:

- SUBJECT 1
- SUBJECT 2

Do not allow difficulty selection from one subject to affect another subject.

QUESTION SELECTION

If adaptive selection is requested:

inspect the existing question selection function first.

Prefer the smallest safe modification.

Do not copy the entire question engine.

Avoid:

- duplicate questions
- invalid question records
- questions from the wrong subject
- questions from the wrong level
- wrong question-bank selection

ANSWER HISTORY

If adaptive behavior uses answer history:

inspect existing:

- used-question tracking
- correct-answer tracking
- wrong-answer tracking
- streak data
- statistics

Do not create duplicate history storage.

Do not reset existing history.

DIFFICULTY ADJUSTMENT

If difficulty changes based on performance:

use the actual existing game metrics.

Do not invent arbitrary thresholds without an explicit task requirement.

Possible existing signals may include:

- correct answers
- incorrect answers
- streak
- completion rate
- timer performance
- level performance

Inspect which signals already exist before implementation.

TIMER

If adaptive difficulty changes timer behavior:

inspect the existing timer system.

Do not create another timer.

Preserve:

- timer start
- timer stop
- timeout
- next question
- game over

Do not let an old timer continue after a mode change.

LIVES

If difficulty affects lives:

reuse the existing lives system.

Do not create another lives counter.

Do not change the normal maximum unless explicitly requested.

SCORE / POINTS / COINS

Adaptive difficulty must not accidentally duplicate rewards.

Reuse existing:

- score
- points
- coins
- reward functions

Do not create bonus currency merely because a question is harder.

STREAK / COMBO

Do not create another streak or combo system.

Reuse existing streak/combo handling.

Difficulty changes must not incorrectly reset streaks.

SPECIAL MODES

Inspect compatibility with:

- Normal Quiz
- Daily Challenge
- Reviewer Mode

Do not automatically apply Adaptive Difficulty to every mode.

Follow the existing mode architecture.

Daily Challenge must remain isolated from normal progression.

Reviewer Mode must remain isolated from normal progression.

SAVE DATA

If adaptive state is saved:

first inspect existing localStorage architecture.

Do not create unnecessary persistent state.

If performance data already exists:

reuse it.

If temporary session state is sufficient:

do not permanently save it.

Never reset unrelated player data.

HOME / LEVEL UI

Do not redesign Home or Level Selection unnecessarily.

If difficulty information must be displayed:

integrate it into existing UI conventions.

Preserve current navigation.

THREE THEMES

Any Adaptive Difficulty UI must work with:

- original
- light
- dark

Check:

- labels
- difficulty indicators
- question cards
- buttons
- progress
- borders
- selected states

Keep text readable.

MOBILE

The game is primarily used on phones.

Difficulty UI must be:

- compact
- readable
- responsive
- touch friendly

Avoid:

- horizontal scrolling
- tiny labels
- oversized cards
- unnecessary animations

SAFETY RULE

Adaptive Difficulty must never make the game impossible to complete because of a selection bug.

If there are not enough valid questions at a selected difficulty:

use the existing fallback behavior when available.

Do NOT create invalid questions.

Do NOT silently duplicate questions.

Do NOT modify the question bank automatically to hide the problem.

VALIDATION

After implementation verify:

[ ] Existing question loading still works.

[ ] Correct question bank is used.

[ ] Correct subject is used.

[ ] SUBJECT 1 works.

[ ] SUBJECT 2 works.

[ ] Level selection still works.

[ ] 80-level progression remains intact.

[ ] No invalid questions are selected.

[ ] No accidental duplicate questions appear.

[ ] Answer validation works.

[ ] Timer works.

[ ] Lives work.

[ ] Score works.

[ ] Points work.

[ ] Coins work.

[ ] Streak works.

[ ] Achievements work.

[ ] Save data remains correct.

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

Do NOT:

- create another quiz engine
- replace question banks
- create duplicate question data
- rewrite level progression
- create duplicate history
- create duplicate timers
- create duplicate rewards
- modify unrelated systems
- add unnecessary libraries

Inspect first.

Reuse existing architecture.

Change only what the task requires.

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

READ GEONQUIZSCREEN INSTRUCTIONS.

INSPECT THE ACTUAL QUESTION SELECTION SYSTEM.

PRESERVE THE 80-LEVEL ARCHITECTURE.

PRESERVE SUBJECT 1 / SUBJECT 2.

PRESERVE BOTH QUESTION BANKS.

REUSE EXISTING QUIZ FUNCTIONS.

DO NOT CREATE A SECOND QUIZ ENGINE.

PROTECT SAVE DATA.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

MAKE THE SMALLEST SAFE CHANGE.
