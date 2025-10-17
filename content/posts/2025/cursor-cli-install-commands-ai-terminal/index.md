---
title: "Cursor CLI: Install, core commands, and how to use it well"
slug: "cursor-cli-install-commands-ai-terminal"
summary: "You can pick up an AI coding session from where you left off, straight from the command line. Two tiny commands give you memory and automation: - Resume a prior thread with one line:   ```   cursor resume   ``` - Pipe responses to scripts or CI in clean JSON:   ```   cursor --print --output-format json   ```"
date: 2025-08-08
draft: false
---
![curor_cli](cursor-cli-og.png)
You can pick up an AI coding session from where you left off, straight from the command line. Two tiny commands give you memory and automation:
- Resume a prior thread with one line:
  ```
  cursor resume
  ```
- Pipe responses to scripts or CI in clean JSON:
  ```
  cursor --print --output-format json
  ```

<!--more-->

That combo makes the CLI feel less like a chatbot and more like a tool you can actually wire into your dev workflow.

### What Cursor CLI is in plain English:


- A terminal tool that brings Cursor’s AI agent into your shell.
- You keep the familiar chat-style help, but now you can list sessions, resume threads, and print structured output.
- It’s designed to work in any terminal so you can use it inside your editor, on a remote box, or in CI.

### Quick install

- Exact install command from the page:
  ```
  curl https://cursor.com/install -fsS | bash
  ```

- Binary name used in commands: `cursor`

### Core commands and flags you will actually use

- Resume your latest session:
  ```
  cursor resume
  ```
- List previous conversations:
  ```
  cursor ls
  ```
- Resume a specific thread:
  ```
  cursor --resume [thread id]
  ```
- Print output to stdout instead of entering an interactive flow:
  ```
  cursor [command] -p
  cursor [command] --print
  ```
- Choose your output format:
  ```
  --output-format [json|text]
  ```
- Example for scripting:
  ```
  cursor --print --output-format json
  ```

Tip: The JSON output is handy for CI steps, logging, or custom tooling that needs machine readable results.

### Config and project setup

- You can guide the agent with local configuration and rules:
  - `mcp.json` for MCP servers and tools
  - `.cursor/rules` directory to shape behavior and add context automatically

These files let you steer how the agent behaves and what tools it can use without touching every command.

### Highlights from the Cursor CLI page

- “Full control from your terminal.”
- “Review agent edits” and make changes right in the terminal.
- “Steer in real-time” as the agent works.
- “Set your own rules” using rules files, AGENTS.md, and MCP.

This all points to a model where your terminal is not just a place to paste prompts. It becomes a stable, configurable workspace with memory and tooling.

### Authentication and login

- The CLI docs and page do not list a dedicated login command on the pages referenced here.
- Expect sign in or token flow during first use based on your Cursor account, but the exact steps are not shown on these pages.

### Platform support, limits, pricing

- Supported OS or platform details are not specified on the pages referenced here.
- Limits and pricing are not listed on the CLI pages. Assume usage ties to your Cursor plan.

### Real-world ways to use it

- Fast code review loops
  - Stage changes, then ask the agent to review the diff. Print JSON for a CI check or stash the results in your logs.
- Long-running investigations
  - Use `cursor resume` to keep the same thread while you switch machines or contexts.
- Team rules baked into projects
  - Drop guidance in `.cursor/rules` and `mcp.json` so the agent follows your playbook automatically.

### What’s missing or to verify next

- No explicit auth command on the referenced pages
- No OS matrix or Windows specifics
- No pricing details
- If you are security-conscious, note that installation uses curl piped to bash

### Takeaways

- Install is one line and the binary is just `cursor`.
- You can resume threads, list sessions, and print JSON on demand, which makes it CI friendly.
- Local config with `mcp.json` and `.cursor/rules` lets you standardize how AI helps across your repo.
- The page leans into control and guidance, not just ad hoc prompting.

<!--
### Resources & References

- Primary Source: https://cursor.com/cli
- Additional Sources:
  - Using the CLI: https://docs.cursor.com/en/cli/using
  - Cursor docs (general): https://docs.cursor.com
  - Cursor docs repo: https://github.com/cursor/docs
- Key Terms/Concepts: Cursor CLI, resume threads, `--print`, `--output-format json`, MCP, `mcp.json`, `.cursor/rules`
- Related Topics: Cursor editor, Model Context Protocol, terminal-based AI agents, CI integration with AI tools
-->