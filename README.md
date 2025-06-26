# 🚀 Advanced AI Assistant for VS Code: Unconstrained & Customizable

## Free your AI workflow directly within your editor!

This VS Code extension redefines how developers interact with AI, providing a powerful, self-hosted, and truly unconstrained AI assistant. Unlike other tools that impose artificial usage limits even on free models, our extension directly integrates with [OpenRouter](https://openrouter.ai/)'s API to leverage genuinely unlimited free-tier models (like DeepSeek R1) without any hidden subscription barriers.

Empower your coding with intelligent, context-aware assistance, deep customization, and complete transparency over your AI interactions.

---

## ✨ Key Features

* **Truly Unlimited Free-Tier Usage:** Connect directly to OpenRouter's API and utilize free-tier models (e.g., DeepSeek R1) without arbitrary hourly or daily request limits imposed by the extension.
* **Self-Hosted Control:** Run the extension locally with your own API keys, giving you full control over your AI environment and data.
* **User-Defined Usage Controls:** Set and manage *your own* soft usage limits for AI requests directly within the extension, ensuring proactive API consumption management.
* **Intelligent Local Caching:** Reduce redundant API calls and speed up repetitive tasks with smart caching of AI responses, configurable by you.
* **Advanced Context Awareness:**
    * **Dynamic Context Injection:** Automatically include relevant project files, directories, or specific code structures (e.g., functions, classes) as context for AI prompts.
    * **Semantic Codebase Search:** (Future) Leverage semantic understanding to provide the AI with highly pertinent code snippets from across your entire workspace.
* **Customizable Prompts & AI Personas:**
    * **Rich Prompt Templating:** Create, save, and share sophisticated prompt templates with dynamic placeholders for tailored AI interactions.
    * **Personalized AI Behavior:** Define custom AI "personas" (e.g., "Senior Architect," "QA Tester") with specific instructions and preferred coding styles for diverse assistance.
    * Store your custom prompts and personas as version-controlled project files.
* **Seamless Workflow Integration:**
    * **Direct File Manipulation:** Apply AI-generated code changes directly to your workspace with clear diff previews, eliminating copy-pasting.
    * **Terminal Command Execution:** Allow the AI to suggest and execute terminal commands (with your explicit approval) for tasks like package installation or test runs.
    * **Proactive Suggestions:** Get intelligent AI suggestions based on your current coding context, linter errors, or active development tasks.
* **Multi-Model Flexibility:**
    * Configure fallback models to automatically retry requests if your primary model fails or hits an actual provider-side limit.
    * (Future) Compare responses from multiple AI models side-by-side to choose the best output.
* **Robust Security & Privacy:** Your API keys are securely stored using VS Code's built-in SecretStorage API. Data minimization practices ensure only necessary information is sent to external APIs.

---

## 🚀 Why This Extension?

* **Break Free from Artificial Limits:** Experience truly unlimited AI assistance for free models, unlike other extensions that lock essential functionality behind paywalls.
* **Developer-Centric Design:** Built by developers, for developers, with a focus on practical utility, deep integration, and empowering customization.
* **Privacy & Control:** Your data stays local, and your API keys are secure. You control the AI's behavior, not the other way around.
* **Accelerate Your Workflow:** Automate repetitive tasks, get instant code suggestions, refactor with ease, and debug faster with an intelligent partner by your side.

---

## 🛠️ Getting Started

### Prerequisites

* [Visual Studio Code](https://code.visualstudio.com/) (Version 1.80.0 or higher recommended)
* An [OpenRouter.ai](https://openrouter.ai/) account and an API key (no billing information needed for free-tier models).

### Installation

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/amarzeus/AdvancedAIExtension.git
    cd AdvancedAIExtension
    ```
2.  **Install Dependencies:**
    ```bash
    npm install
    # or yarn install
    ```
3.  **Open in VS Code:**
    ```bash
    code .
    ```
4.  **Run the Extension in Debug Mode:**
    * Press `F5` in VS Code. This will open a new VS Code window with your extension running.

### Configuration

1.  **Set your OpenRouter API Key:**
    * Open VS Code Settings (`Ctrl+,` or `Cmd+,`).
    * Search for "AI Extension" (or your chosen extension name).
    * Locate the setting for "OpenRouter API Key" and paste your key. This will be securely stored using `SecretStorage`.
2.  **Configure Custom Limits & Caching:**
    * Explore settings related to "Usage Limits" and "Local Cache" to set your preferences.
3.  **Define Contextual Rules:**
    * Create a `.vscode/your-extension.json` file in your project root to specify files or patterns for automatic context inclusion (example coming soon!).

---

## 💡 Usage

Once installed and configured, you can start interacting with the AI assistant:

1.  **Access Commands:** Open the VS Code Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`) and search for commands starting with "AI:".
2.  **Select Text:** Highlight a block of code and use a command like "AI: Explain Selected Code" or "AI: Refactor Selected Code."
3.  **Open Contextual Chat:** Use a command like "AI: Open Project Chat" to interact with the AI about your entire project.
4.  **Terminal Interaction:** When the AI proposes a terminal command, a prompt will appear for your approval before execution.

*(More detailed usage instructions and examples will be added soon!)*

---

## 🔒 Security & Privacy

We are committed to protecting your data and privacy.

* [span_0](start_span)Your OpenRouter API key is stored locally and encrypted using VS Code's built-in [SecretStorage API](https://code.visualstudio.com/api/references/vscode-api#SecretStorage)[span_0](end_span).
* We adhere to a data minimization principle: only the necessary context directly related to your prompt is sent to the OpenRouter API.
* This extension is open-source, allowing for full transparency and community auditing of its security practices.

---

## 🤝 Contributing

We welcome contributions from the community! If you're interested in improving this extension, please check out our [Contributing Guidelines](CONTRIBUTING.md) (coming soon) and feel free to open issues or pull requests.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

*(© 2025 Amar's Organization. All rights reserved.)*
