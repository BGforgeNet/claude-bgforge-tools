# BGforge Claude Code Plugins

Claude Code plugin marketplace for Infinity Engine and classic Fallout modding languages.

## bgforge-mls-lsp

Code intelligence for Fallout SSL, WeiDU (BAF/D/TP2), and related modding languages. Provides completion, hover, go-to-definition, diagnostics, formatting, symbols, rename, and inlay hints.

**Supported languages:**

| Language    | Extensions                     |
| ----------- | ------------------------------ |
| Fallout SSL | `.ssl`, `.h`                   |
| WeiDU BAF   | `.baf`, `.slb`                 |
| WeiDU D     | `.d`                           |
| WeiDU TP2   | `.tp2`, `.tpa`, `.tph`, `.tpp` |

Not all features are available for all languages. BAF has the smallest feature set (completion, hover, formatting, inlay hints). SSL and D have the richest.

## Installation

1. Install the language server:
   ```bash
   npm install -g @bgforge/mls-server
   ```

2. Add the marketplace:
   ```
   /plugin marketplace add BGforgeNet/claude-bgforge-tools
   ```

3. Install the plugin:
   ```
   /plugin install bgforge-mls-lsp@bgforge-tools
   ```

4. Exit and relaunch `claude` (LSP servers require a restart).

To verify, ask Claude about a symbol in a `.ssl`, `.baf`, `.d`, or `.tp2` file. If it uses LSP tools (hover, go-to-definition) instead of grepping, the plugin is working.

## Troubleshooting

- **"Executable not found in $PATH"** - install the server: `npm install -g @bgforge/mls-server`
- **"No LSP server available"** - restart Claude Code after installing the plugin
- **Server not starting** - verify with `bgforge-mls-server --stdio` (should hang waiting for input; Ctrl+C to exit)

## Links

- [VSCode extension](https://marketplace.visualstudio.com/items?itemName=BGforge.bgforge-mls) (full-featured client)
- [Server npm package](https://www.npmjs.com/package/@bgforge/mls-server)
- [Source code](https://github.com/BGforgeNet/VScode-BGforge-MLS)
- [Issue tracker](https://github.com/BGforgeNet/VScode-BGforge-MLS/issues)
- [Editor setup guides](https://github.com/BGforgeNet/VScode-BGforge-MLS/blob/master/docs/editors/README.md) (neovim, emacs, helix, zed, kate, sublime, jetbrains, geany, notepad++)
