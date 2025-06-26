# Product Requirements Document (PRD): Advanced VS Code AI Extension with OpenRouter Integration

## 1. Introduction

* **1.1 Product Vision:** To empower developers with a self-hosted, highly customizable, and unconstrained AI assistant within VS Code, leveraging OpenRouter's truly unlimited free-tier models without artificial subscription barriers, and offering advanced features for context-aware code generation, refactoring, and workflow automation.
* **1.2 Goals:**
    * Provide genuinely unlimited AI assistance for free-tier OpenRouter models.
    * Offer superior customization for prompts, context, and AI personas.
    * Improve developer productivity through intelligent code suggestions, refactoring, and automation.
    * Ensure secure handling of API keys and user data.
    * Foster transparency in AI usage and actions.
* **1.3 Target Audience:** Software developers, engineers, and teams utilizing VS Code who seek enhanced AI assistance without restrictive usage quotas, preferring open and customizable solutions.

## 2. Features and Functionality (High-Level)

* **2.1 Core AI Interaction:**
    * Direct integration with OpenRouter API (configurable endpoint).
    * Support for multiple AI models available via OpenRouter (especially free-tier models like DeepSeek R1).
    * Secure storage and retrieval of OpenRouter API keys using VS Code SecretStorage API.
* **2.2 Usage Control and Transparency:**
    * **User-Defined Rate Limiting:** Allow users to set their own advisory rate limits (e.g., requests per minute/hour) for API calls, enforced client-side.
    * **Local Caching:** Intelligent caching of AI responses to reduce redundant API calls and improve performance. Configurable cache invalidation (TTL) for cached responses.
    * Real-time token and cost tracking for API usage (if paid models are used).
* **2.3 Context Awareness:**
    * Dynamic context injection from selected code, open files, and specified project directories (e.g., via glob patterns).
    * Semantic code search integration to provide highly relevant codebase context.
* **2.4 Customization:**
    * Advanced prompt templating with dynamic placeholders.
    * User-definable AI personas with specific instructions and preferred coding styles.
    * Ability to store prompts and personas as version-controlled project files.
* **2.5 Workflow Integration:**
    * Direct file manipulation (read/write/diff) within the VS Code workspace.
    * Terminal command execution with user approval.
    * Proactive AI suggestions based on current coding context, linter errors, or issue tracking.
* **2.6 Multi-Model Capabilities:**
    * Configurable multi-model fallback in case of primary model failure or actual OpenRouter rate limits.
    * Side-by-side comparison of responses from multiple models.

## 3. Detailed Features and User Stories

* **3.1 Core AI Agent:**
    * **User Story:** As a developer, I want to input a code snippet or natural language prompt and receive AI-generated code, explanations, or refactoring suggestions directly in VS Code, so I can speed up my development.
    * **Requirements:**
        * Ability to send selected text, entire file content, or custom input to the AI.
        * Display AI responses in a clear, readable format within VS Code (e.g., diff view, new file, inline suggestion).
        * Support for markdown rendering in AI responses.
* **3.2 Unlimited Free-Tier Access & Custom Limits:**
    * **User Story:** As a developer, I want to use OpenRouter's free-tier models without being artificially limited by the extension, so I can maximize my usage without incurring unexpected costs or hitting arbitrary caps.
    * **User Story:** As a developer, I want to define my own soft usage limits for AI requests, so I can manage my API consumption proactively and avoid hitting provider-side rate limits.
    * **Requirements:**
        * Configuration setting for OpenRouter API base URL and API key.
        * Configuration settings for user-defined request thresholds (e.g., X requests per Y time unit).
        * Visual indicators/notifications when approaching or exceeding self-defined limits.
        * Local caching mechanism for AI responses (configurable storage size/TTL).
* **3.3 Smart Contextualization:**
    * **User Story:** As a developer, I want the AI to automatically consider relevant parts of my project (e.g., related files, common utility functions) when generating code, so the suggestions are more accurate and integrated.
    * **Requirements:**
        * Configuration for context inclusion rules (e.g., include all `.ts` files in `src/utils`, include `package.json`).
        * Integration with VS Code's file system API to read specified context files.
        * (Stretch) Integration with a local semantic code search library to find related code based on AST/symbols.
* **3.4 Custom Prompts and Personas:**
    * **User Story:** As a developer, I want to create and save custom prompt templates for common coding tasks, so I can consistently get specific types of AI assistance.
    * **User Story:** As a developer, I want to define different AI "personas" (e.g., "Senior Architect," "QA Tester") with specific instructions, so the AI's responses align with different roles or focuses.
    * **Requirements:**
        * UI for creating, editing, and managing prompt templates.
        * Support for placeholders in templates (e.g., `{{selected_code}}`, `{{file_path}}`).
        * UI for defining and switching between AI personas.
        * Ability to import/export prompt templates and personas (e.g., JSON or YAML files).
* **3.5 Advanced Workflow Features:**
    * **User Story:** As a developer, I want the AI to propose and execute refactoring changes across multiple files, and show me a clear diff, so I can review and apply them easily.
    * **User Story:** As a developer, I want the AI to generate unit tests for my code, so I can quickly ensure coverage.
    * **User Story:** As a developer, I want the AI to assist with debugging by analyzing error logs and suggesting fixes, so I can resolve issues faster.
    * **Requirements:**
        * Workspace editing capabilities (applying changes with diff previews).
        * Terminal execution with explicit user approval for commands.
        * Integration with VS Code's diagnostic API for error analysis.
        * (Stretch) Basic Git integration for staging/committing AI-generated changes.
* **3.6 Security and Data Handling:**
    * **User Story:** As a developer, I want my API keys and sensitive data to be stored securely, so I don't have to worry about exposure.
    * **Requirements:**
        * Exclusive use of `vscode.SecretStorage` for API key persistence.
        * Data minimization: Only send necessary data to external APIs.
        * Clear privacy policy/disclaimer within the extension regarding data transmission.

## 4. Non-Functional Requirements

* **4.1 Performance:**
    * Fast response times for AI interactions (leveraging caching and efficient API calls).
    * Minimal impact on VS Code editor performance and responsiveness.
* **4.2 Security:**
    * Adherence to VS Code security best practices for extensions.
    * Protection against common vulnerabilities (e.g., injection, unauthorized access).
    * Secure network communication (HTTPS).
* **4.3 Scalability:**
    * Designed to handle a high volume of local requests (client-side rate limiting, caching).
    * Resilient to external API rate limits (with fallback strategies).
* **4.4 Usability:**
    * Intuitive user interface and smooth workflow integration.
    * Clear error messages and user feedback.
    * Comprehensive documentation and onboarding guides.
* **4.5 Maintainability:**
    * Well-structured and modular codebase.
    * Clear separation of concerns (UI, API interaction, logic).
    * Automated tests for core functionalities.

## 5. Technical Considerations (Architectural Notes)

* **Extension Host vs. Webview:** Considerations for running heavy AI processing in web workers or dedicated processes to avoid blocking the UI thread.
* **API Client Library:** Choice of HTTP client library (e.g., `axios`, `node-fetch`).
* **State Management:** How the extension's state (settings, cached responses) will be managed.
* **Testing Strategy:** Unit, integration, and end-to-end tests for the extension.
* **Deployment:** VS Code Marketplace publishing considerations.
