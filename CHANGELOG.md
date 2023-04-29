# Change Log

All notable changes to the "aspen-procs" extension will be documented in this file.

### [1.0.0] -- 2023-04-14

-   Initial release

### [1.0.1] -- 2023-04-15

-   Modified the names of some syntax patterns to change their color in the editor
-   Fixed some issues with reserved synonyms not being highlighted correctly (more to be done)
-   Added a LICENSE file to the repository

### [1.1.0] -- 2023-04-15

-   Change the name of the extension to "aspen-procs" to avoid confusion with any other "procs" extensions
-   Minor bugfix with numbers not being highlighted correctly when preceded by another number
-   Minor bugfix with the `\ RD` command not highlighting synonym definitions correctly when the `<(row,col)>` option is used
-   All numbers are now the same color, except in the case of the `<(row,col)>` option for the `\ RD` command
-   Force comments to start at the beginning of a line (to allow for the wildcard character to be used)
-   Disable bracket highlighting since nested brackets are not common in PROCS
-   Swap the colors for synonym definitions and labels/transfers (just a personal preference)
-   Added `ARGS_<num>` and `RETURN` to the list of reserved synonyms (note that these are not actually reserved, but they are commonly used as such)

### [1.1.1] -- 2023-04-15

-   Update syntax highlighting for transfer commands to allow for synyonm references
    -   Note that in order to allow this, any text that appears _between_ two synonym references is highlighted as if it were an unconditional transfer
    -   Synonyms referenced within a transfer must begin with an `@` symbol and end with a `.` symbol
    -   All text that is adjacent to a bracket symbol is highlighted as the correct color for a conditional transfer
    -   Example A: `? 5 GT 7 [MOVE_@SOURCE._TO_@DEST._EXEC]`
        -   `[MOVE_` and `_EXEC]` are highlighted red to indicate a failure condition
        -   `@SOURCE.` and `@DEST.` are highlighted blue to indicate a synonym reference
        -   `_TO_` is highlighted cyan to indicate plain text
    -   Example B: `? 5 GT 3 (RETURN_@DIFF.)`
        -   `(RETURN_` and `)` are highlighted green to indicate a success condition
        -   `@DIFF.` is highlighted blue to indicate a synonym reference
-   Allow for the use of `*` as a wildcard character outside of comments and strings
-   Add more details to the README file

### [1.2.0] -- 2023-04-16

-   Fixed known issue with reserved synonyms not being highlighted correctly when used after certain commands
    -   In order to do this, one of the regex patterns became significantly longer, so this may be modified in the future
-   Add `AUTO` and `NO_HALT` to the list of keywords
-   Fixed highlighting for GDA references when adjacent to a bracket symbol or string
-   All `.` symbols are now highlighted blue (except within comments and quoted) since they are most often used to delimit synonyms
    -   This does mean that the `.` symbol is highlighted blue when used in an unquoted string (such as in `/ DI .`), so it will be up to the user to put quotes around the string if they want to avoid this
-   Fixed an issue with comments being highlighted a different color when beginning with `**` instead of `*`

### [1.2.1] -- 2023-04-27

-   Synonyms and labels now allow `.` and `-` characters in their names
-   Limit all labels to 10 characters or fewer
    -   This is due to the internal workings of PROCS. Labels with more than 10 characters may fail to be recognized
    -   Labels that are 11 characters or greater will be highlighted red to warn the user of this issue
-   Failure transfer statements now allow `,` characters, allowing for a list of failure transfers

### [1.3.0] -- 2023-04-28

-   Add support for the escape symbol `^`
    -   These get highlighted yellow to make them stand out
-   Remove `.` as an allowed symbol in synonym names
    -   Only labels should have been allowed to use `.` in the first place
-   Fix highlighting errors involving the `$` symbol
-   Rewrote syntax highlighting logic for `S AS`
    -   Now uses the "captures" feature to make highlighting more accurate
    -   The first three words `S AS <synonym>` are highlighted yellow to indicate a synonym definition (this may be removed in the future)
-   Also rewrote syntax highlighting logic for `S DS`, `C IC`, `C DC`, and `/ RD` commands
    -   Now uses the "captures" feature to make highlighting more accurate
    -   This should fix the issue with the `(<<row>>,<<col>>)` option for the `\ RD` command being highlighted a different color
-   Add support for negative numbers
    -   Negative numbers are NOT allowed as `<row>`, `<col>`, `<index>`, or `<length>` values in any commands
    -   Negative numbers ARE allowed as `<data_elements>`, `<value>`, `<arg1>`, `<arg2>`, `<lda_data>`, and `<gda_data>` values in any commands
    -   I have not had great success with using negative numbers in PROCS, but supposedly they are allowed, so they will be highlighted as well
