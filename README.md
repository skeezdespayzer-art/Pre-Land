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

A `.vscode/settings.json` is included in this repository to configure the recommended default Copilot model.

### About "Claude Opus 4.6"

As of this writing, Anthropic's available model versions in GitHub Copilot are:
- `claude-3-5-sonnet` (Claude 3.5 Sonnet — fast, high quality, recommended)
- `claude-3-opus` (Claude 3 Opus — most powerful)

"Claude Opus 4.6" is not a released model version. If you are looking for the most capable Claude model, choose **Claude 3 Opus** or **Claude 3.5 Sonnet** from the Copilot model picker.
