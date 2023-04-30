# ASPEN PROCS Syntax Highlighting

This extension adds syntax highlighting for the ASPEN PROCS language. Dark theme is highly recommended.

## Features

Basic syntax highlighting for built-in keywords, comments, strings, constants, synonyms, and labels. Please note that although the language allows for the use of unquoted strings, this extension does not support them. Therefore, for the sake of readability, it is recommended that all strings be enclosed in quotes.

Supported Commands (KEY: `<id>` = required; `<<id>>` = optional):

-   `:<label>`
-   `C IC <synonym> <value> (<<success>>) [<<failure>>]`
-   `C DC <synonym> <value> (<<success>>) [<<failure>>]`
-   `/ DI (<<row>>,<<col>>) <data_elements> (<<success>>) [<<failure>>]`
-   `/ RD (<<row>>,<<col>>) <synonym> <<default>> (<<success>>) [<<failure>>]`
-   `/ CC (<row>,<col>)`
    -   Alternative: `/ CC <row> <col>`
-   `/ CL <<start_line_no>> <<end_line_no>>`
-   `/ CS`
-   `/ PS`
-   `/ DL (<<row>>,<<col>>) <data_elements>`
-   `G AG <gda_address><<:length>> <gda_data> (<<success>>) [<<failure>>]`
-   `L AL <lda_address><<:length>> <lda_data> (<<success>>) [<<failure>>]`
-   `S AS <synonym> <value> (<<success>>) [<<failure>>]`
-   `S DS <synonym> (<<success>>) [<<failure>>]`
-   `? <arg1> <op> <arg2> (<<success>>) [<<failure>>]`
    -   `<op>` can be one of the following:
        -   `EQ` - Equal to
        -   `NE` - Not equal to
        -   `LT` - Less than
        -   `LE` - Less than or equal to
        -   `GT` - Greater than
        -   `GE` - Greater than or equal to
    -   `<arg1>` and `<arg2>` can be a number, a synonym reference, or a string
-   `$ <filename> <op> (<<success>>) [<<failure>>]`
    -   `<op>` can be one of the following:
        -   `N` - Create a new file
        -   `A` - Append to an existing file (or create a new file if it doesn't exist)
-   `F <op> <filename> (<<success>>) [<<failure>>]`
    -   `<op>` can be one of the following:
        -   `CR` - Create an empty file
        -   `DL` - Delete a file
        -   `EX` - Check if a file exists
-   `& <<$>><proc_id> <<AUTO|NO_HALT>> [<<failure>>]`
-   `# <system_command>`

All literals above are considered keywords and will be highlighted as such. The following are also considered keywords and will be highlighted as such:

`LDA$$$`, `ASPEN_HOME`, `AUTHNO`, `COBOL`, `COBOLPGM`, `COBOL_SUFFIX`, `COBOL_TAIL`, `COL`, `DATE`, `DEOP`, `EOPMESS`, `LINKDATE`, `LINKTIME`, `MENUHEAD`, `MAINMENU`, `NEXTMENU`, `MODE`, `OS`, `PATH`, `PROCDUMP`, `PROMPT_VAL`, `RMRC`, `ROW`, `RUNPATH`, `ST_DIR`, `START`, `SYSRC`, `TERMNO`, `TIME`, `USERID`, `USERTERM`, `ARGS_<index>`, `RETURN`

Other Supported Features:

-   Synonym referencing in the form of `@<SYNONYM>` or `@<SYNONYM>.`
-   Synonym subscripting in the following forms:
    -   `@<SYNONYM>(<index>,<length>)`
    -   `@<SYNONYM>(L,<length>)`
    -   `@<SYNONYM>(R,<index>)`

---

## Release Notes

Latest release notes are available in the [CHANGELOG](CHANGELOG.md).

## Known Issues

-   **Just because it gets highlighted doesn't mean it's valid syntax. This extension does not validate syntax.**
-   Transfer statements using multiple synonyms have inconsistent highlighting on the text between those synonyms
