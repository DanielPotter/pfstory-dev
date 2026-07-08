# pfstory-dev

pfstory-dev is a development and tracking repository for a Perchance-hosted RPG and story generator based on the pfstory fork at https://perchance.org/pfstory-fork.

## Overview

This repository is not a standalone application. It exists to preserve, refine, and document the generator behavior used by the hosted Perchance experience. Most work here is aimed at improving the generator inside the Perchance environment rather than building a separate local app.

## What this repository contains

- Source used by the hosted generator
- Development notes, change history, and iteration logs
- Documentation for plugin-based customization and extension

## Highlights

The hosted generator includes features such as:

- Multi-story management with save, load, duplicate, folders, pinning, and search
- Persistent per-story notebooks and story bibles with auto-updates
- Auto-backups, restore support, and backup pruning
- AI generation controls such as Continue, Regenerate, Regen Last, and Stop
- Token-length warnings and dice-based randomness for game-like variability
- Import and export options including file, URL, encrypted export, and temporary links
- Shareable story snapshot links
- Custom music, background visuals, themes, and shortcut tools
- Media hooks for audiobook and image generation
- Inline editing of story text and generated content

## What this fork improves

This fork builds on the base experience with a stronger emphasis on extensibility, story shaping, and generation control:

- Notebook-based plugins with hooks, shortcuts, and raw generator access for automation and experimentation
- A more flexible story bible workflow, including custom templates, auto-update controls, undo support, and safer editing during generation
- More reliable generation behavior with paragraph-aware continuation, smoother stop and regenerate flows, and better handling of inline edits

## Running and previewing

This project is intended to run inside the Perchance environment. There are no standalone local scripts in this repository that will launch the full generator outside that hosted context.

## Documentation

- [docs/plugins.md](docs/plugins.md) for plugin authoring guidance

## Contributing

Contributions are welcome when they improve templates, documentation, or development notes in a focused and useful way. If you want to suggest a change, open an issue or submit a pull request.

## Acknowledgements

Credit goes to @iyruk on the Perchance Discord for the generator work behind pfstory, which itself builds on the original ai-rpg generator.

## Contact

For questions, ideas, or feedback, please open an issue in this repository.

