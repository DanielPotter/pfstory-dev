## 2026.06.15 (DanielPotter)
Features:
- Added a button to create a plugin notebook page. It's currently in the notepad page menu. This may change in the future as it doesn't make sense here.

## 2026.06.14 (DanielPotter)
Features:
- Added a notebook-based plugin system to allow for dynamic instructions. I'm mostly using this to prototype narrative sequencing, but I plan to document and develop this feature more to allow for custom automation and story handling.

Enhancements:
- Added support for using `//##PerchanceCode##// to mark a notebook page as Perchance code. This will simplify things moving forward and the old uncommented header will be unsupported once I make it easier to flag a page as Perchance code.

Fix:
- Fixed shortcut prompt text not clearing after it is used, causing it to influence the story longer than expected.
- Fixed app notebook not persisting after import if the page is reloaded without displaying the app notebook first.

## 2026.06.11 (DanielPotter)
Enhancements:
- Added rudimentary syntax highlighting for notebook pages that contain Perchance code.

Fix:
- Fixed the story arc text always being included in the AI context.
- Fixed notebook not saving when content is cut or pasted.

## 2026.06.10 (DanielPotter)
Features:
- Added an undo button to reverse a manual bible section update.

Enhancements:
- An ellipsis will now be inserted for removed dashes in dialog.
- Lines with a colon will no longer be bold unless it is followed by a space or a new line. This will prevent times from being partially bold.

## 2026.06.03 (DanielPotter)
Fix:
- Bible section templates being included in the AI context.

## 2026.06.01 (DanielPotter)
Features:
- Added an option to customize the templates used to generate bible sections.
- Added a button to update the current bible section using events since the last update.
- Added a button to regenerate the name of the current story.
- Added Perchance list support for shortcuts to use.
  - There is no UI for this yet. Just add `##PerchanceCode##` to the top of a notebook page and it will be evaluated like a Perchance list. You can then reference one of the lists in the insertion or prompt text of a shortcut.

Fix:
- Improved story continuation so that it wont output # Ambient Outro immediately.
- Regenerating story after continuing the story inline now adds the newly generated story to the end of the last paragraph as expected.

## 2026.03.31
Features:
- Added "Erotica" Genre - By request

Fix:
- UI fixes, Typos.

## 2026.03.26
Features:
- Added AI Prompt field to shortcuts, this allows you to add data that wont be saved permanently to the story, but is loaded when the shortcut is used. useful for story mechanics to help AI remember what it's supposed to do.
- UI fixes

Removed:
- Removed Feedback and Comments, Added note to message in the discord thread for support.

## 2026.03.25
Features:
- Added "new story" prompt to help show settings before starting new stories

Fix:
- various ui fixes

## 2026.03.24
Fix:
- Story Bible Code cleanup (leak fix attempt)

## 2026.03.23
Features:
- Implement Custom Genre/Sub-Genre
- UI Fixes

## 2026.03.20-4
Fix:
- Suggestions load fix

## 2026.03.20-3
Features:
- Implemented caching for a few functions for improved performance

## 2026.03.20-2
Features:
- Added custom texteditor
- Implemented better thought design (thoughts look like `This now`)

## 2026.03.20-1
Features:
- Added 'Magical Realism' Genre
- UI Cleanup
- Re-designed Info Section (Included Changelog)

## 2026.03.19
Features:
- Added Global Settings for Save file (by request)

Fix:
- Improvements to ai prompts

## 2026.03.18
Features:
- Added Naming Conventions for new characters

Enhancements:
- Reworked Difficulty/Dice to be more relevant when set (Only for user actions)
- Sorted dropdowns

Fix:
-  Restructured story bible for AI Prompt to reduce tokens
- Various UI fixes

## 2026.03.17-2
Feature: 
- Added Custom writing style under story settings

## 2026.03.17-1
Fix:
- Fixed bible access during generation
- fixed sotry switching/creation during generation

## 2026.03.13
Features:
- Added Story Bible Auto Update Option

Enhancements:
- Various UI Improvements
- Minor AI prompt tweaks

## 2026.03.11-2
Features: 
- Added Game Mode
- Added Dice Roll
## 2026-03-11-1
Features:
- Updated UI Design

Fix:
- Fixed several bugs

## Before March 2026
Whole bunch of stuff XD
Didn't create changelog until now :)