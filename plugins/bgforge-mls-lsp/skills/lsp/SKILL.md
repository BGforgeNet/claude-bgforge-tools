---
name: lsp
description: >
  Use when working with classic RPG modding files: Fallout SSL (.ssl, .h),
  WeiDU BAF (.baf, .slb), WeiDU D (.d), WeiDU TP2 (.tp2, .tpa, .tph, .tpp).
  Provides LSP code intelligence via bgforge-mls-server.
---

An LSP server is available for `.ssl`, `.h`, `.baf`, `.slb`, `.d`, `.tp2`, `.tpa`, `.tph`, `.tpp` files.

IMPORTANT: The LSP server IS installed and working for ALL these file types. Getting 0 results from documentSymbol or any other operation does NOT mean the server is missing or broken. Many modding files have no document symbols. The server also takes time to initialize, so if the first request fails or returns nothing, retry. NEVER conclude that the LSP is unavailable based on empty results. Always continue using LSP hover, go-to-definition, and other operations.

For SSL/D/TP2 files, call `LSP documentSymbol` in parallel with `Read` to warm up the server. For BAF files, read first, then use `LSP hover` on keywords found in the file.

Use LSP hover for documentation before relying on training data. Use LSP go-to-definition for navigation instead of grep (SSL/D/TP2 only).

Inlay hints show translations for corresponding placeholders: `@123` means translation line number 123 from `.msg` (SSL) or `.tra` (BAF/D/TP2) files.

## Feature matrix (Claude Code LSP operations)

| Operation        | SSL | BAF | D   | TP2 |
| ---------------- | --- | --- | --- | --- |
| Hover            | +   | +   | +   | +   |
| Go-to-definition | +   |     | +   | +   |
| Document symbols | +   |     | +   | +   |
