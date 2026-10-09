---
name: mdv
description: Open a Markdown file in Nicoleta's browser with the mdv CLI, rendered like GitHub, with Mermaid diagrams she can pan and zoom. Use whenever she asks to open, view, preview, show or read a .md file, to see the diagrams in one, or mentions mdv. Do not use it on your own initiative.
user-invocable: true
metadata:
  argument-hint: <file.md> [-w] [-b browser]
---

# mdv

`mdv` renders one Markdown file as a GitHub-style page in a browser.
Mermaid code blocks become diagrams that can be panned, zoomed and expanded to the full window.
The source lives in `~/Dev/personal/mdv`.

Use it when Nicoleta wants to look at a Markdown file rather than have you summarize it: "open the plan", "show me the diagram in X.md", "preview this", "mdv the README".

## Current guidance lives in the CLI

Flags in this file may go stale.
Get the source of truth from the script:

```
mdv --help
```

## How to use it

- Pass the path to the file; a relative path resolves from the current directory.
- Without flags, it opens in the system default browser and exits at once.
- `-b <browser>` opens in a named browser: `safari`, `chrome`, `firefox`, `edge`, `brave`, `arc`, or any macOS app name.
  Pass it only when she names a browser.
- `-w` serves the file on `127.0.0.1` and re-renders the page on every save, keeping the scroll position.
  It runs until stopped, so start it as a background command and tell her it is running.
  Use it when she will keep editing the file, or when you are about to edit a file she is looking at.
- Only one file per call; run it again for each extra file.
- After opening, report the file in one line. Do not describe the rendered content unless asked.

## Rules

- Open files only when she asks to see them.
  Writing a Markdown file is not a request to open it.
- Do not write a Markdown file just to have something to open.
- Diagrams need valid Mermaid syntax.
  A broken block renders as a syntax-error diagram in place, so fix the source rather than retrying.
- The page loads its libraries from public CDNs, so it needs internet on first load.
