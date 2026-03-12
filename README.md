# Pre-Land

A pre-landing page project.

---

## VS Code & Cline — Using Claude Opus 4.6

This project is developed using the [Cline](https://marketplace.visualstudio.com/items?itemName=saoudrizwan.claude-dev) extension for VS Code with **Claude Opus 4.6** as the active model.

Claude Opus 4.6 is a real, cloud-based Anthropic model available in the Cline extension's model picker. It requires an active Anthropic API key and an internet connection.

### Why are Cline sessions not saved?

Cline stores every task (conversation) in VS Code's **extension global storage** — not inside the workspace folder. History is shared across all workspaces and persists as long as VS Code global storage is intact.

Sessions appear to be lost in these situations:

1. **Cline history panel is not visible** — Click the clock/history icon at the top of the Cline sidebar to open the task history list.

2. **Global storage was cleared** — Reinstalling VS Code, resetting its storage, or running "Developer: Clear Storage" removes all saved Cline tasks permanently.

3. **API provider or model ID mismatch** — If the model ID stored in a saved task no longer matches the currently configured model, Cline may fail to resume that task. Keeping a consistent `cline.apiModelId` in `.vscode/settings.json` prevents this.

4. **Incomplete task** — A task that was interrupted before any AI response is not always saved. Tasks with at least one completed message exchange are always written to history.

### How to fix session persistence

1. Open the Cline sidebar panel in VS Code and click the **history (clock) icon** to see all saved tasks.
2. Ensure your Anthropic API key is entered and valid in the Cline extension settings.
3. Keep the model ID consistent — this repository's `.vscode/settings.json` sets `cline.apiModelId` to `claude-opus-4-6` so every workspace session uses the same model.
4. Do not run "Clear Storage" or reinstall VS Code unless you have exported your history first.
