## 2026.23.07 (Daniel Potter)
Fix:
- Fixed changes made to the story bible being ignored. This has been a long-standing bug in pfstory.

## 2026.22.07 (Daniel Potter)
Enhancements:
- Added the ability for plugins to get other plugins by ID. A plugin's ID will default to the plugin's name with spaces removed.

Fix:
- Improved styling for quoted text so that inch measurements in the story don't interfere with how dialog is styled.
- Fixed inconsistency with how comments and async functions were styled.

## 2026.07.07 (DanielPotter)
Enhancements:
- Improved raw access to the generator for plugins by exposing the root Perchance node. Search for `HINT: Raw Access for Plugins` in the Perchance code to learn more.
- Updated the generator description.

## 2026.06.27 (DanielPotter)
Fix:
- Swapped the text editor from `pftexteditor` to `text-editor-plugin-v1` so that Markdown isn't rendered inline. Markdown format decorators (`*`, `>`, `#`, etc.) are no longer hidden. Inline rendering is cool and may return, but it would be optional.

## 2026.06.25 (DanielPotter)
Enhancements:
- Revamped plugin management so that plugins are only reloaded when they are edited. Previously, all plugins would be reloaded if any were modified.
- Added the `storyLoaded` hook.

Fix:
- Fixed edits that are made during story generation being reverted when generation stops due to the paragraph limiter. You can now edit the story while it's being generated, just like in ai-rpg!

## 2026.06.20 (DanielPotter)
Enhancements:
- Adjusted plugin property casing for consistency. The old casing will still be respected but are now deprecated.
- `storyGenerationFinished` hook: When the story generation ends due to the end of a paragraph, `data.stopReason` now equals `paragraph` instead of `user`.
- Simplified the plugin template and add a link to the plugin documentation.
- Added raw access to the generator for plugins. This will not be documented, but exists for those who like hacking.

Fix:
- Fixed the button for deleting the "what happens next text" not always appearing or disappearing. It is now hidden when the text is submitted and unhidden when filled by a shortcut.
- Fixed the writing style tooltip getting cut off on narrow screens (like on mobile devices). It is now centered.

## 2026.06.17 (DanielPotter)
Features:
- Added two more plugin hooks:
  - `continueStory(opts)`: Called right after the generate story button is pressed. You can set `opts.continueInline` to force a generation to continue a paragraph.
  - `getMessagesWithSummaryReplacements(messages)`: Called before the function with the same name returns. You can use this to modify the story given to the AI.

## 2026.06.15 (DanielPotter)
Features:
- Added a button to create a plugin notebook page. It's currently in the notepad page menu. This may change in the future as it doesn't make sense here.
- Added a new plugin hook: `getDynamicContext(lines)`. Any content added to the lines array will be added to the AI prompt after the overview but before the story so far. This is a good place to put information that the AI should know about, but doesn't need to drive what happens next.

Enhancements:
- Allow Perchance code to import generators.

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