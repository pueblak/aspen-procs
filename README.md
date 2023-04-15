# ASPEN PROCS Syntax Highlighting

This extension adds syntax highlighting for the ASPEN PROCS language.

## Features

Basic syntax highlighting for built-in keywords, comments, strings, constants, synonyms, and labels.

Supported Commands (KEY: `<id>` = optional; `<<id>>` = required):
- `:<<label>>`
- `C IC <<synonym>> <<value>> (<success>) [<failure>]`
- `C DC <<synonym>> <<value>> (<success>) [<failure>]`
- `/ DI (<row>,<col>) <<data_elements>> (<success>) [<failure>]`
- `/ RD (<row>,<col>) <<synonym>> <default> (<success>) [<failure>]`
- `/ CC (<<row>>,<<col>>)`
    - Alternative: `/ CC <<row>> <<col>>`
- `/ CL <start_line_no> <end_line_no>`
- `/ CS`
- `/ PS`
- `/ DL (<row>,<col>) <<data_elements>>`
- `G AG <<gda_address>> <<gda_data>> (<success>) [<failure>]`
- `L AL <<lda_address>> <<lda_data>> (<success>) [<failure>]`
- `S AS <<synonym>> <<value>> (<success>) [<failure>]`
- `S DS <<synonym>> (<success>) [<failure>]`
- `? <<arg1>> <<op>> <<arg2>> (<success>) [<failure>]`
    - `<<op>>` can be one of the following:
        - `EQ` - Equal to
        - `NE` - Not equal to
        - `LT` - Less than
        - `LE` - Less than or equal to
        - `GT` - Greater than
        - `GE` - Greater than or equal to
    - `<<arg1>>` and `<<arg2>>` can be a number, a synonym reference, or a string
- `$ <<filename>> <<op>> (<success>) [<failure>]`
    - `<<op>>` can be one of the following:
        - `N` - Create a new file
        - `A` - Append to an existing file (or create a new file if it doesn't exist)
- `F <<op>> <<filename>> (<success>) [<failure>]`
    - `<<op>>` can be one of the following:
        - `CR` - Create an empty file
        - `DL` - Delete a file
        - `EX` - Check if a file exists
- `& <$><<proc_id>> <AUTO|NO_HALT> [<failure>]`
- `# <<system_command>>`
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