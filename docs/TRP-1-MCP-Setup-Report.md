# TRP-1: MCP Setup Challenge Report

## 1. Overview
This document records my work completing the TRP-1 MCP Setup Challenge.  
The goal was to configure a modern IDE with MCP tooling, define effective agent rules, and reflect on how rules shape AI behavior.

---

## 2. Task 1 – MCP Setup

### What I Did
- Selected VS Code as my IDE.
- Ensured GitHub Copilot and GitHub Copilot Chat are installed.
- Configured the Tenx MCP Analysis server using a hosted HTTP MCP endpoint.
- Started the MCP server and proceeded to GitHub OAuth in VS Code.

### Configuration
- MCP server URL: https://mcppulse.10academy.org/proxy
- IDE: VS Code
- Device: Windows

### Result
- Configuration present in .vscode/mcp.json.
- MCP server started in VS Code with GitHub OAuth completed.
- Tools appear in Copilot Chat (Agent mode tools list).

### Notes
- During setup, GitHub’s default MCP server failed to start on Windows.
- This did not affect the Tenx MCP Analysis server.
- The Tenx MCP tools (log_passage_time_trigger, log_performance_outlier_trigger) were exposed to the Copilot Agent and logging operated as expected.

---

## 3. Task 2 – Agent Rules Configuration

### What I Did
- Reviewed best-practice guidance (planning-first, approval gates, minimal diffs).
- Created a structured copilot-instructions.md file.
- Emphasized planning-first behavior, approval gates, and minimal diffs.

### What Worked
- Planning-first rules significantly improved agent correctness.
- Explicit “ask when unsure” rules reduced hallucinated assumptions.
- Diff-based guidance reduced unnecessary file rewrites.

### What Didn’t Work
- Attempted npm-based install of @tenx-ai/mcp-server failed with 404 (not required for hosted MCP).
- Early rules were too brief to guide agent behavior consistently.

---

## 4. Insights Gained

- Rules strongly influence how an AI agent reasons, not just what it outputs.
- Clear constraints produce more predictable and trustworthy behavior.
- Agent rules act like a shared mental model between human and AI.
- Small wording changes (e.g., “wait for approval”) dramatically alter outcomes.

---

## 5. Conclusion
This exercise demonstrated the importance of intentional environment setup, disciplined agent guidance, and reflective iteration when working with AI-assisted development.
