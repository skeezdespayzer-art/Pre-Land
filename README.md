# Pre-Land

A pre-landing page project.

---

## VS Code & GitHub Copilot — Using Claude Models

### Why is Claude Opus not available in "local" mode?

**Claude models (including Claude 3 Opus, Claude 3.5 Sonnet, etc.) are cloud-based API models provided by Anthropic.** They require a network connection to Anthropic's servers and cannot be downloaded or run locally on your machine.

VS Code's **local inference mode** (via GitHub Copilot or extensions like Continue.dev) only supports **open-source models** that can be fully downloaded and run on your own hardware — for example, models served through [Ollama](https://ollama.com/) (Llama 3, Mistral, Phi-3, etc.).

### How to use Claude in VS Code

To use a Claude model in VS Code you must use **cloud mode** (not local mode):

1. Make sure [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) is installed and you are signed in.
2. Open Copilot Chat and click the model picker dropdown.
3. Select a Claude model (e.g. `claude-3-5-sonnet` or `claude-3-opus`) — these are available when connected to the internet.

A `.vscode/settings.json` is included in this repository to configure the recommended default Copilot model and enable session persistence.

### About "Claude Opus 4.6"

As of this writing, Anthropic's available model versions in GitHub Copilot are:
- `claude-3-5-sonnet` (Claude 3.5 Sonnet — fast, high quality, recommended)
- `claude-3-opus` (Claude 3 Opus — most powerful)

"Claude Opus 4.6" is not a released model version. If you are looking for the most capable Claude model, choose **Claude 3 Opus** or **Claude 3.5 Sonnet** from the Copilot model picker.

---

### Why are Copilot Chat sessions not saved?

VS Code Copilot Chat automatically saves conversation history per workspace. However, sessions **will not persist** in two common situations:

1. **Invalid model identifier** — If a session was started with an unrecognized model (e.g. `claude opus 4.6`), VS Code cannot restore that session on the next launch because the model ID stored in the session data does not match any available model. The session appears lost.

2. **Not signed in to GitHub Copilot** — Saved sessions are tied to your authenticated account. If you are signed out, VS Code cannot retrieve the history.

#### How to fix session persistence

- Use only valid, cloud-based model identifiers such as `claude-3-5-sonnet` or `claude-3-opus`. The `.vscode/settings.json` in this repository already sets the correct default.
- Ensure you are signed in: open the Accounts menu in the VS Code status bar and verify your GitHub Copilot subscription is active.
- Optionally, keep VS Code's local history enabled (see `.vscode/settings.json`).

After switching to a valid model, new sessions will be saved and restored correctly on every VS Code restart.
