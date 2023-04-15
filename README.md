# ASPEN PROCS Syntax Highlighting

This extension adds syntax highlighting for the ASPEN PROCS language.

## Features

Basic syntax highlighting for built-in keywords, comments, strings, constants, synonyms, and labels.

---
## Release Notes

Latest release notes are available in the [CHANGELOG](CHANGELOG.md).

## Known Issues

- The syntax highlighting for reserved synonyms is currently highlighting correctly everywhere except after the following commands, where instead they are highlighted as if they were user-defined synonyms:
    - `S AS`
    - `S DS`
    - `C IC`
    - `C DC`
    - `\ RD`