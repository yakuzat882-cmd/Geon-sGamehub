# GEONGAMEHUB — COPILOT MASTER INSTRUCTIONS V2

## SOURCE OF TRUTH

Repository:
https://github.com/yakuzat882-cmd/GeonGameHub.1

Verified project reference:
Geon'sGameHub ZIP provided by the user.

The CURRENT repository code is always the source of truth.

Before editing anything:
1. Inspect the current files.
2. Understand the existing implementation.
3. Search dependencies and references.
4. Make the smallest safe change.
5. Test the affected feature.
6. Review the final diff.

Never rely only on old prompts, memory, or assumptions.

---

# PROJECT STRUCTURE

The main game currently contains:

- index.html
- style.css
- script.js
- questions.json
- questions.new.json
- questions.embedded.js
- questions.new.embedded.js

Audio assets are also part of the project.

Do not rename or remove these files unless explicitly requested.

---

# CORE ARCHITECTURE

The main application is a browser-based HTML/CSS/JavaScript quiz game.

Primary responsibilities:

index.html
- UI structure
- screens
- panels
- buttons
- quiz containers
- selectors
- dialogs/modals

style.css
- visual design
- layout
- responsive behavior
- themes
- component states

script.js
- game state
- quiz logic
- question loading
- level/progress
- answers
- timer
- lives
- rewards
- statistics
- achievements
- mastery
- reviewer mode
- daily challenge
- shop/items
- profile/settings
- localStorage persistence

questions.json
- previous question bank

questions.new.json
- new question bank

questions.embedded.js
- embedded/fallback previous question data

questions.new.embedded.js
- embedded/fallback new question data

---

# SUBJECT STRUCTURE

The current question system contains 5 subjects:

- MATH
- SCIENCE
- PSYCHOLOGY
- TECH 1
- TECH 2

Each subject contains:

- SUBJECT 1
- SUBJECT 2

The normal progression uses 80 levels/questions per quiz type.

Do not change this structure unless explicitly requested.

---

# QUESTION BANKS

There are two questioner/question-bank modes:

- previous
- new

The main external banks are:

questions.json
questions.new.json

The application also contains embedded versions.

Do not merge the banks accidentally.

Do not replace the previous bank with the new bank.

Do not delete existing questions unless explicitly requested.

Do not duplicate questions.

Preserve the existing question object structure.

Before changing question data, inspect the actual JSON structure.

---

# QUESTION OBJECTS

The current question data uses fields including:

- id
- level
- question
- choices
- answer
- explanation

Do not rename these fields without inspecting every dependent JavaScript reference.

Do not change question ordering when existing logic depends on it.

New questions must follow the existing structure.

Avoid repetitive wording and repetitive answer patterns.

Do not make every answer unnecessarily long.

---

# QUIZ FLOW

The quiz system is state-based.

Important existing concepts include:

- selected subject
- selected quiz type
- selected questioner
- current level
- current question index
- question list
- score
- points
- coins
- lives
- timer
- streak
- best streak
- correct answers
- level progress
- completion state
- quiz mode

Do not create a second quiz engine when an existing function can be reused.

Before modifying quiz flow, trace the existing functions and state transitions.

---

# TIMER AND LIVES

The normal quiz currently uses:

- 30-second question timer
- maximum 8 quiz lives

Do not change these values unless explicitly requested.

Timer changes must preserve:
- timer start
- timer stop
- timeout behavior
- answer handling
- next-question behavior
- game-over behavior

Lives changes must preserve existing reward/save behavior.

---

# LEVEL SYSTEM

The game uses 80-level progression.

Existing progress values are bounded to 0–80.

Preserve:
- level IDs
- level/question relationships
- progress storage
- completed level behavior
- selected level behavior
- home progress display

Do not automatically unlock levels unless explicitly requested.

Do not redesign the progression system for a small level-related feature.

---

# SUBJECT PROGRESS AND MASTERY

The Home screen has subject progress.

Progress is calculated from existing quiz progress.

The project also has Subject Mastery tiers.

Do not replace the existing progress calculation.

If modifying progress:
- inspect existing functions first
- preserve both SUBJECT 1 and SUBJECT 2
- preserve questioner separation
- keep the 0–80 range
- verify Home updates correctly

---

# TITLES

The project has a title system based on completed levels.

Title progress uses the existing storage architecture.

Titles are associated with subjects and quiz types.

Do not create a second title system.

Do not overwrite existing title progress.

---

# STREAK AND COMBO

The project contains streak milestones including:

- 3
- 5
- 10
- 15
- 20

Existing streak rewards include score, coins and/or points.

Preserve existing streak behavior.

Do not reset streaks incorrectly.

Do not duplicate rewards.

---

# ACHIEVEMENTS

The project contains special achievements.

Examples include:
- Streak Master
- Perfect Level
- Survivor
- Speed Quizzer
- Coin Collector
- other existing achievements

Achievement state is persisted.

Do not create duplicate achievement storage.

Inspect the existing achievement definitions and storage before adding new ones.

---

# DAILY CHALLENGE

Daily Challenge is an isolated replay system.

Current size:
10 questions.

Existing daily challenge rewards include:
- bonus points
- bonus coins

Daily Challenge must remain separate from normal level progression.

Do not accidentally write normal progression from Daily Challenge.

Do not allow Daily Challenge to corrupt normal quiz state.

Preserve date-based daily challenge storage.

---

# REVIEWER MODE

Reviewer Mode is an isolated review layer.

Current session size:
10 questions.

It uses the existing question banks and quiz UI.

Reviewer Mode should NOT write:
- normal progression
- normal rewards
- normal statistics
- normal used-question history

unless explicitly requested.

Reuse existing question loading and quiz rendering where possible.

Do not create a separate question database.

---

# SHOP AND ITEMS

The project contains a shop/item inventory system.

Existing items include systems such as:
- Life Token
- Time Boost
- Hint
- 50/50

Coins are used by the existing inventory architecture.

Do not create another currency or inventory system.

Inspect existing item storage before modifying it.

---

# POINTS AND COINS

The project has separate:
- score
- points
- coins

The existing conversion system uses:

100 points = 1 coin

Do not change the conversion rate unless explicitly requested.

When modifying conversion:
- validate input
- validate calculation
- save the result
- update Home display
- verify persistence after reload

---

# PLAYER SAVE SYSTEM

The project uses localStorage extensively.

Examples of existing persisted systems include:
- game data
- quiz progress
- used questions
- titles
- achievements
- item inventory
- best streak
- daily challenge
- profile
- settings

Never casually rename or delete a localStorage key.

Before changing save data:
1. Find the key.
2. Find all references.
3. Understand its structure.
4. Preserve existing data.
5. Add backward-compatible defaults.
6. Test reload persistence.

Never create duplicate save systems for an existing feature.

---

# THREE THEMES

The project currently supports three themes:

- original
- light
- dark

Every UI change MUST work in all three.

Check:
- backgrounds
- text
- buttons
- borders
- cards
- inputs
- progress bars
- icons
- panels
- modals
- success/error states

Never introduce a color that becomes unreadable in another theme.

---

# HTML / CSS / JS DEPENDENCIES

Before modifying HTML:

Search script.js for:
- IDs
- classes
- event listeners
- querySelector
- getElementById
- data attributes
- dynamically generated elements

Before modifying CSS:

Check whether classes are used by:
- HTML
- JavaScript
- theme logic
- animations
- state changes

Before modifying JavaScript:

Check:
- callers
- event listeners
- DOM dependencies
- localStorage dependencies
- data dependencies

Never remove an apparently unused element/function without checking references.

---

# MOBILE FIRST

The game is primarily used on phones.

All UI changes must remain:
- responsive
- touch friendly
- readable
- properly spaced

Check small screens.

Avoid:
- oversized panels
- tiny buttons
- text overflow
- broken grids
- unnecessary horizontal scrolling

Do not redesign the entire interface for a small feature.

---

# CHANGE POLICY

ONLY change what the task requires.

Do not perform unrelated:
- redesigns
- refactors
- cleanup
- renaming
- optimization
- library changes
- architecture rewrites

If a requested feature requires another change, make the smallest compatible change.

---

# TESTING

Before claiming DONE:

1. Check JavaScript syntax.
2. Check console errors when possible.
3. Test the requested feature.
4. Test normal quiz flow if quiz code changed.
5. Test affected subject/level.
6. Test save/reload if storage changed.
7. Test mobile layout.
8. Test all 3 themes for UI changes.
9. Check unrelated existing behavior.
10. Review the final diff.

Never claim a test was performed if it was not actually performed.

---

# GITHUB WORKFLOW

The GitHub repository is the primary workspace.

Before editing:
- inspect current files
- inspect relevant dependencies
- preserve existing user changes

After editing:
- review the diff
- remove accidental changes
- use a clear commit message
- commit only when authorized

Never invent:
- commit hashes
- PR numbers
- GitHub links
- test results

---

# RESPONSE FORMAT

The user primarily works from a phone.

Do NOT paste entire modified files unless explicitly requested.

Do NOT paste huge code blocks.

After completing a task use:

DONE

Files changed:
[file names]

Commit/PR:
[real link if available]

Changes:
[short summary]

Tests:
[short result]

Notes:
[only if necessary]

Keep the response short.

---

# FINAL PRINCIPLE

INSPECT FIRST.

PRESERVE FIRST.

USE THE EXISTING ARCHITECTURE.

CHANGE ONLY WHAT IS REQUESTED.

PROTECT QUESTIONS, LEVELS AND SAVE DATA.

KEEP ALL 3 THEMES COMPATIBLE.

TEST BEFORE CLAIMING DONE.

NEVER INVENT RESULTS.

KEEP FINAL RESPONSES SHORT.
