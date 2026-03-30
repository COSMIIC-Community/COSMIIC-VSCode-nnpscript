# nnpscript VS Code Extension

Syntax highlighting for `.nnpscript` files, ported from Notepad++ User Defined Language (UDL) XML.

---

## Build .vsix package file

Requires Node.js:

```bash
npm install -g @vscode/vsce
cd nnpscript-vscode
vsce package
# produces nnpscript-1.0.0.vsix
```

---

## Install `.vsix` file in VS Code:

```
Extensions panel (Ctrl+Shift+X) → ··· menu → Install from VSIX…
```

Or via the command line:

```bash
code --install-extension nnpscript-1.0.0.vsix
```

---

## Color mapping from Notepad++ UDL

| NP++ Style      | Color     | VS Code Scope                         |
|-----------------|-----------|---------------------------------------|
| LINE COMMENTS   | `#008000` green, italic | `comment.line.percent`      |
| COMMENTS        | `#FF80FF` pink          | `comment.block`             |
| KEYWORDS1       | `#00A8A8` teal, bold    | `storage.type`              |
| KEYWORDS2       | `#0000FF` blue, bold    | `keyword.control.mnemonic`  |
| KEYWORDS3       | `#0000FF` blue, bold    | `support.function.log`      |
| OPERATORS       | `#0000FF` blue          | `keyword.operator`          |
| NUMBERS         | `#000000` black         | `constant.numeric`          |
| DELIMITERS1/2   | `#8000FF` purple        | `string.quoted.double`      |
| DELIMITERS3     | `#FF8000` orange, bold  | `string.other.exclamation`  |
| DELIMITERS7     | `#800040` dark magenta, italic | `meta.block`         |

---

## Files in this extension

```
nnpscript-vscode/
├── package.json                          # Extension manifest
├── language-configuration.json           # Comment toggling, bracket matching
├── syntaxes/
│   └── nnpscript.tmLanguage.json         # TextMate grammar (tokenization rules)
└── themes/
    └── nnpscript-light-color-theme.json  # Color theme matching your NP++ UDL
```
