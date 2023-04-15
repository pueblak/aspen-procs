# Change Log

All notable changes to the "aspen-procs" extension will be documented in this file.


## [1.0.0] -- 2023-04-14

- Initial release

### [1.0.1] -- 2023-04-15

- Modified the names of some syntax patterns to change their color in the editor
- Fixed some issues with reserved synonyms not being highlighted correctly (more to be done)
- Added a LICENSE file to the repository

## [1.1.0] -- 2023-04-15
- Change the name of the extension to "aspen-procs" to avoid confusion with any other "procs" extensions
- Minor bugfix with numbers not being highlighted correctly when preceded by another number
- Minor bugfix with the `\ RD` command not highlighting synonym definitions correctly when the `<(row,col)>` option is used
- All numbers are now the same color, except in the case of the `<(row,col)>` option for the `\ RD` command
- Force comments to start at the beginning of a line (to allow for the wildcard character to be used)
- Disable bracket highlighting since nested brackets are not common in PROCS
- Swap the colors for synonym definitions and labels/transfers (just a personal preference)
- Added `ARGS_<num>` and `RETURN` to the list of reserved synonyms (note that these are not actually reserved, but they are commonly used as such)