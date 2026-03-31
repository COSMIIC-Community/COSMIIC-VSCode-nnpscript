# nnpscript VS Code Extension

Syntax highlighting for `.nnpscript` files, ported from Notepad++ User Defined Language (UDL) XML.

Colors are applied via `configurationDefaults` in `package.json` so they work consistently across all VS Code themes without requiring the user to set a specific theme.

---

## Build .vsix package file

Requires Node.js:

```bash
npm install -g @vscode/vsce
cd COSMIIC-nnpscript-VSCode
vsce package
# produces versioned nnpscript-X.X.X.vsix
```

This repository also automatically builds a `.vsix` artifact by GitHub Actions on every push or pull request to `main`. Download it from the **Actions** tab → latest workflow run → **nnpscript-vsix** artifact.

---

## Install `.vsix` file in VS Code

Select the Extensions panel from the VS Code sidebar (Ctrl+Shift+X). Click the triple dot "···" menu in the top right corner. Click Install from VSIX…

Or via the command line:

```bash
code --install-extension nnpscript-1.0.3.vsix
```

---

## Syntax features

| Token | Example | Description |
| --- | --- | --- |
| Comments | `% this is a comment` | Lines starting with `%` |
| Keywords1 (types) | `uint16`, `stack`, `const` | Type / storage keywords |
| Keywords2 (mnemonics) | `MOV`, `ADD`, `BEQ` | Instruction mnemonics |
| Keywords3 (logging) | `log`, `timelog` | Logging functions |
| Operators | `=`, `(`, `)`, `>`, `\|`, `^` | Operators |
| Numbers | `42`, `3.14`, `0xFF` | Integer, float, and hex literals |
| Strings (double-quoted) | `"label"` | Double-quoted strings |
| Strings (exclamation) | `!message!` | Exclamation-delimited strings |
| Blocks | `{ ... }` | Curly-brace blocks |
| OD index | `N7:1F57.3` | Object Dictionary node:index.subindex references |              |

---

## Files in this extension

```
COSMIIC-nnpscript-VSCode/
├── package.json                          # Extension manifest & token color customizations
├── language-configuration.json           # Comment toggling, bracket matching
├── syntaxes/
│   └── nnpscript.tmLanguage.json         # TextMate grammar (tokenization rules)
└── .github/workflows/
    └── build-vsix.yml                    # CI: builds .vsix artifact on push/PR to main
```
