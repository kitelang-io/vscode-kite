# Kite Language — VS Code extension

Syntax highlighting, bracket/comment handling, and snippets for the
[Kite](https://github.com/kitelang-io) programming language (`.kite`).

## Install (local)

No build step — this is a declarative (grammar + config) extension.

**Option A — symlink into your extensions folder:**

```sh
git clone https://github.com/kitelang-io/vscode-kite.git
ln -s "$(pwd)/vscode-kite" ~/.vscode/extensions/kite-language-0.1.0
```

(For VS Code Insiders use `~/.vscode-insiders/extensions/`.)
Then reload VS Code (`Cmd/Ctrl+Shift+P` → *Developer: Reload Window*).

**Option B — package a `.vsix`:**

```sh
npm install -g @vscode/vsce
vsce package
code --install-extension kite-language-0.1.0.vsix
```

## Verify

Open any `.kite` file.
To inspect the scope under the cursor (useful when tuning colors or a theme),
run *Developer: Inspect Editor Tokens and Scopes* from the command palette.

## Notes / limitations

- Highlighting is lexical (TextMate), so it is heuristic: any capitalized
  identifier is colored as a type, and any lowercase identifier immediately
  before `(` as a function call. This matches Kite convention but is not a
  parser.
- `type` is a contextual (soft) keyword — it is a plain identifier in the
  lexer, highlighted here for readability of `trait` associated types.

## License

Licensed under the [Apache License 2.0](LICENSE).
