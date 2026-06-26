This generator support plugins. To add a plugin, simply create a new notebook page and write `//##PerchanceCode##//` as the first line.

**Plugin template:**
```
//##PerchanceCode##//
$output = [__plugin]

__plugin
  name = My Plugin
  enabled = [true]
  isPlugin = [true]
  apiVersion = 1
  init(api) =>
    window.api = api;
  // hooks
  // shortcutLists = [$root]
```

## Plugin Members

- **name** (string): Display name of the plugin.
- **enabled** (boolean, optional): Whether the plugin is active. Defaults to `true`.
- **isPlugin** (boolean): Must be set to `true` to identify this as a plugin.
- **apiVersion** (number): API version the plugin targets. Currently `1`.
- **init(api)** (function, optional): Called when the plugin loads. Receives the API object for plugin interactions.
- **deinit()** (function, optional): Called when the plugin unloads or when generator code changes.
- **hooks** (object, optional): Contains hook functions that respond to story generation events.
- **shortcutLists** (list, optional): A list of lists to expose for shortcuts. Use `[$root]` to expose all lists.

**Shortcut lists example:**
```
__pluginWithAllLists
  isPlugin = [true]
  shortcutLists = [$root] // This will expose all top-level lists from this page.

__pluginWithSpecificLists
  isPlugin = [true]
  shortcutLists
    // You can put lists directly under shortcutLists
    color
      red
      green
      blue
    // Or you can reference them.
    temperature = [temperature]

temperature
  freezing
  cold
  hot
  scalding
```

## Plugin API

The `api` object passed to `init(api)` provides access to core generator functions:

### Notepad Functions

- **notepad.getScope()** - Gets the active scope selected in the notepad.
- **notepad.setScope(scope)** - Sets the active scope in the notepad.
- **notepad.getDataForScope(scope)** - Retrieves data for a specific scope.
- **notepad.setDataForScope(scope, data)** - Stores data for a specific scope.
- **notepad.getTab(tabId, scope)** - Gets a tab by ID within a scope.
- **notepad.getTabByName(name, scope)** - Gets a tab by name within a scope.
- **notepad.addTab(name, opts)** - Creates a new tab. Options include `scope` and `content`.
- **notepad.requestAppNotebookSave()** - Saves the app notebook. Required after making changes to app notebook pages.

### Plugin Functions

- **plugins.list()** - Gets all loaded plugins.
- **plugins.getEnabled()** - Gets only the loaded plugins that are enabled.

### Story Functions

- **story.requestSave()** - Saves the current story and story notebook. Required after making changes to story notebook pages.
- **story.getPreprocessedStoryText()** - Gets the current story with summary substitutions applied.
- **story.getStorySoFar()** - Gets the raw story text without preprocessing.
- **story.setStorySoFar(content)** - Sets the raw story text.

## Plugin Hooks

Hook functions allow plugins to respond to specific events in the story generation lifecycle. All hooks are optional.

- **continueStory(opts)** - Called right after the generate story button is pressed. Set `opts.continueInline = true` to force a generation to continue a paragraph instead of starting a new one.
- **getMessagesWithSummaryReplacements(messages)** - Called before the function with the same name returns. Modify the `messages` array to alter the story given to the AI.
- **getDynamicContext(lines)** - Called during prompt generation. Add content to the `lines` array to inject information into the AI prompt after the overview but before the story so far.
- **getExtraInstructionsForConsequencesOfAction(lines)** - Called when generating consequences of an action. Add instruction lines to guide the AI response.
- **getExtraInstructionsForContinueWithoutTask(lines)** - Called when continuing the story without an active task. Add instruction lines to guide the AI response.
- **getExtraInstructions(lines)** - Called for all generation scenarios. Add instruction lines that should apply to both action consequences and continue without task.
- **storyGenerationFinished(data)** - Called after the AI finishes generating story content. Use this to perform post-generation processing or logging.
- **storyLoaded(storyData)** - Called when a story has finished loading. This occurs both on initial load and when a story is selected in the Stories panel.
