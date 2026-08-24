GEONQUIZSCREEN — PORTABLE TASK INSTRUCTIONS

1. READ FIRST

Before doing anything, read:

https://github.com/yakuzat882-cmd/GeonGameHub.1/blob/main/.github/copilot-instructions.md

Then inspect the CURRENT repository files.

Do not rely only on this prompt or old code assumptions. The repository is the source of truth.

2. TASK SCOPE

This file contains the portable instructions for work related to GeonQuizScreen.

Before editing:

- Find the actual GeonQuizScreen HTML.
- Find its CSS.
- Find its JavaScript.
- Find its question JSON/data files.
- Find level and subject references.
- Find timer, lives, rewards, points, coins and statistics logic.
- Find localStorage/save logic.
- Find all JS dependencies connected to the screen.

Understand the current architecture first.

3. PRESERVE EXISTING SYSTEM

Do NOT rewrite the whole quiz system.

Do NOT remove existing working features.

Do NOT rename existing IDs/classes/functions/data keys unless absolutely required by the requested task.

Do NOT change unrelated files.

Do NOT change the question order if existing JavaScript depends on it.

Do NOT replace working systems with a new system just because it is easier.

Make the smallest safe modification that completes the requested task.

4. QUIZ SYSTEM

The existing quiz system must remain functional.

Preserve:

- Question loading
- Subject selection
- Level selection/progression
- Answer checking
- Correct/incorrect handling
- Timer
- Lives
- Points
- Coins
- Rewards
- Progress
- Statistics
- Streak/combo systems
- Existing quiz navigation
- Existing result/completion behavior

Before changing any of these, inspect how the current implementation works.

5. QUESTION DATA

When working with questions:

- Do not delete existing questions unless explicitly requested.
- Do not create duplicate questions.
- Keep questions connected to the correct subject and level.
- Preserve the existing JSON/data structure.
- Do not randomly reorder existing questions.
- Avoid repetitive question patterns.
- New questions should have varied wording and answer lengths.
- Do not make every answer unusually long.
- Verify question counts after changes.
- Verify that the correct questions load for the correct level.

If the task is not specifically about questions, do not modify question data.

6. LEVELS

Preserve the current level architecture.

When implementing level selection or level-related features:

- Inspect how levels are currently stored.
- Preserve existing level IDs.
- Preserve question-to-level relationships.
- Do not automatically unlock levels unless explicitly requested.
- Make selected levels load through the existing quiz engine.
- Do not create a second incompatible level system.

7. SUBJECTS

Preserve the existing subject system and selection layout.

Do not redesign or reorder subject selection unless explicitly requested.

Any new feature must correctly identify the selected subject and use the existing subject data structure.

8. THREE THEMES

Every GeonQuizScreen UI change MUST work with all 3 existing themes.

Check:

- Background
- Text
- Buttons
- Cards
- Borders
- Inputs
- Progress indicators
- Icons
- Modals/panels
- Correct-answer states
- Incorrect-answer states
- Hover/active states

Never introduce a hard-coded color that makes text or controls unreadable in another theme.

9. MOBILE UI

The game is primarily used on mobile.

Keep the existing layout responsive.

Check:

- Small screens
- Touch targets
- Text wrapping
- Button sizes
- Panels/modals
- Quiz answers
- Level controls
- Long questions
- Different screen widths

Do not create unnecessary scrolling or oversized UI.

Do not redesign the entire screen for a small change.

10. SAVE DATA

Protect existing localStorage/save data.

Before changing save logic:

1. Find the existing keys.
2. Find every important reference to them.
3. Understand the stored structure.
4. Extend it safely.
5. Preserve existing player data.
6. Add safe defaults for new values when necessary.
7. Test persistence after reload.

Never casually rename or delete existing save keys.

Do not create a second conflicting save system.

11. HTML / JS DEPENDENCIES

Before changing HTML:

- Search JavaScript for IDs/classes used by the screen.
- Check event listeners.
- Check querySelector/getElementById references.
- Check dynamically generated elements.
- Check data attributes.
- Check inline references if present.

Never remove an element just because it appears unused until the repository has been checked.

12. FEATURE IMPLEMENTATION

For any requested GeonQuizScreen feature:

1. Inspect current implementation.
2. Identify the smallest files that need changes.
3. Explain internally how the existing system connects.
4. Reuse existing functions/data when possible.
5. Implement only the requested feature.
6. Preserve existing behavior.
7. Test the affected flow.
8. Test reload/save behavior if applicable.
9. Test all 3 themes if UI was changed.
10. Review the final diff for accidental changes.

13. DO NOT GUESS

If the requested feature conflicts with the existing architecture:

Do not guess.

Inspect the code and determine the safest compatible approach.

If an important requirement cannot be implemented safely without changing another system, report the conflict briefly instead of silently breaking existing functionality.

14. TESTING

Before saying DONE:

- Check JavaScript syntax.
- Check for console errors when possible.
- Test the changed feature.
- Test normal quiz flow.
- Test the affected level/subject.
- Test reload if save data is involved.
- Test mobile layout.
- Test all 3 themes for UI changes.
- Confirm unrelated quiz features still work.
- Review the final diff.

Never claim something was tested if it was not actually tested.

15. GITHUB WORKFLOW

Work directly from the current repository when the environment supports it.

Before editing:

- Inspect the current branch and files.
- Check for existing user changes.
- Do not overwrite unrelated changes.

After editing:

- Review the diff.
- Keep changes focused.
- Use a clear commit message when committing is authorized.
- Never invent commit hashes.
- Never invent PR numbers.
- Never invent GitHub links.

16. SHORT RESPONSE ONLY

The user works mainly from a phone.

After completing the task:

DO NOT paste entire files.

DO NOT paste large code blocks.

DO NOT repeat this instruction file.

Use only:

DONE

Files changed:
[file names]

Commit/PR:
[real link if available]

Changes:
[2–5 short lines]

Tests:
[short result]

Notes:
[only if necessary]

If a real GitHub link exists, provide it.

If no real link exists, say so.

17. IMPORTANT

This file is a PORTABLE TASK SPECIFICATION.

Always combine it with:

https://github.com/yakuzat882-cmd/GeonGameHub.1/blob/main/.github/copilot-instructions.md

The master instructions control repository-wide rules.

This file controls GeonQuizScreen-specific work.

If the repository differs from information written in this file, inspect the repository and follow the CURRENT implementation.

CORE RULE

INSPECT FIRST.
PRESERVE EXISTING SYSTEMS.
CHANGE ONLY WHAT IS REQUESTED.
KEEP ALL 3 THEMES COMPATIBLE.
PROTECT QUESTION, LEVEL AND SAVE DATA.
TEST BEFORE CLAIMING DONE.
KEEP THE FINAL RESPONSE SHORT.
