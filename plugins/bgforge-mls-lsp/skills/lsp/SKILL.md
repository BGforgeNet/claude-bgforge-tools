---
name: lsp
description: >
  Use when working with classic RPG modding files: Fallout SSL (.ssl, .h),
  WeiDU BAF (.baf, .slb), WeiDU D (.d), WeiDU TP2 (.tp2, .tpa, .tph, .tpp).
  Provides LSP code intelligence via bgforge-mls-server.
---

An LSP server is available for `.ssl`, `.h`, `.baf`, `.slb`, `.d`, `.tp2`, `.tpa`, `.tph`, `.tpp` files.

When first opening any of these files, call `LSP documentSymbol` in parallel with `Read` to warm up the server (it needs a few seconds to initialize).

Use LSP hover for documentation before relying on training data. Use LSP go-to-definition and find-references for navigation instead of grep. Check LSP diagnostics after edits.

Inlay hints show translations for corresponding placeholders: `@123` means translation line number 123 from `.msg` (SSL) or `.tra` (BAF/D/TP2) files.

## Feature matrix

| Feature           | SSL | BAF | D        | TP2      |
| ----------------- | --- | --- | -------- | -------- |
| Completion        | +   | +   | +        | +        |
| Hover             | +   | +   | +        | +        |
| Signature help    | +   |     |          |          |
| Go-to-definition  | +   |     | +        | +        |
| Formatting        | +   | +   | +        | +        |
| Document symbols  | +   |     | +        | +        |
| Workspace symbols | +   |     |          | +        |
| Rename            | +   |     | same file | same file |
| Inlay hints       | .msg | .tra | .tra    | .tra     |
