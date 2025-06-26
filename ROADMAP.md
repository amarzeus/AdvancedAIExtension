🗺️ Project Roadmap: Advanced VS Code AI Extension with OpenRouter Integration
This roadmap outlines the planned phases and key features for the development of your Advanced VS Code AI Extension, moving from core functionality to more advanced and competitive capabilities. The timeline is conceptual and will be refined during detailed planning.
Phase 1: Alpha Release (Core Functionality - MVP)
Goal: Establish the foundational AI interaction, secure API key handling, and the core value proposition of unconstrained free-tier OpenRouter usage.
Estimated Timeline: Weeks 1-4
Key Features:
 * Core AI Interaction:
   * Direct integration with OpenRouter API.
   * Support for primary free-tier OpenRouter models (e.g., DeepSeek R1).
   * Basic input methods: selected text, entire file content.
   * Display AI responses (e.g., in a new tab, output panel).
 * API Key Management:
   * Secure storage and retrieval of OpenRouter API keys using VS Code SecretStorage API.
 * Unconstrained Free-Tier Access:
   * Implementation of client-side logic to avoid artificial rate limits for free models.
   * Basic real-time token usage display (for transparency).
 * Basic Context Awareness:
   * Ability to send selected text and optionally the entire current file as context.
 * Initial User Interface:
   * Basic commands accessible via VS Code Command Palette.
   * Minimal settings panel for API key configuration.
Phase 2: Beta Release (Enhanced Customization & Workflow Integration)
Goal: Introduce key differentiation through advanced customization, deeper workflow integration, and basic performance optimizations.
Estimated Timeline: Weeks 5-10
Key Features:
 * User-Defined Usage Controls:
   * Configuration settings for users to define their own soft rate limits.
   * Visual indicators/notifications for self-defined limit status.
 * Intelligent Local Caching:
   * Implementation of response caching for frequently requested prompts/contexts.
   * Configurable cache invalidation (TTL) and clear cache options.
 * Advanced Prompt Management:
   * UI for creating, editing, and managing custom prompt templates.
   * Support for basic placeholders in templates ({{selected_code}}, {{file_content}}).
   * Ability to save prompt templates as project files.
 * Improved Workflow Integration:
   * Workspace editing capabilities (applying AI changes directly with diff previews).
   * Basic terminal command execution with explicit user approval.
 * Contextual Enhancements:
   * Configuration for dynamic context inclusion rules (e.g., glob patterns for directories/file types).
 * Error Handling & Feedback:
   * Robust error handling for API calls.
   * Clearer user feedback and notification system.
Phase 3: Version 1.0 (Competitive Advantage & Refinement)
Goal: Achieve a robust, highly competitive product with advanced features, polished UX, and strong codebase health.
Estimated Timeline: Weeks 11-16
Key Features:
 * Multi-Model Capabilities:
   * Configurable multi-model fallback strategy.
   * Side-by-side comparison view for responses from multiple models.
 * Advanced AI Personas:
   * UI for defining and switching between custom AI "personas."
   * Persisting personas as version-controlled files.
 * Proactive AI Suggestions:
   * Initial implementation of AI providing suggestions based on linter errors, active file changes, or open issues.
 * Codebase-Aware Assistance:
   * (Stretch) Integration with a local semantic code search or language server protocol for more intelligent context gathering.
 * Enhanced Documentation & Onboarding:
   * Comprehensive user documentation, tutorials, and guides.
   * Improved first-run experience for new users.
 * Performance & Stability:
   * Further performance optimizations (e.g., offloading heavy tasks to web workers).
   * Extensive testing and bug fixes.
 * Telemetry (Opt-in):
   * (Optional, strictly opt-in) Basic, anonymous usage telemetry to understand feature adoption and performance.
Phase 4: Future Enhancements (Post-V1.0)
Goal: Explore advanced capabilities and deeper integrations based on user feedback and evolving AI landscape.
Estimated Timeline: Ongoing
Potential Features:
 * Automated Code Review & Refactoring:
   * Integrate with Git for AI-powered pull request reviews.
   * Advanced multi-file refactoring capabilities.
 * Test Generation & Maintenance:
   * AI-generated unit and integration tests.
   * Assistance in updating tests when source code changes.
 * Documentation Generation:
   * Automated generation of inline comments, function docstrings, or README content.
 * Browser Interaction/Debugging:
   * (If applicable to user needs) Integration with headless browser for UI/UX debugging assistance.
 * Offline/Local Model Support:
   * Integration with local LLM serving tools (e.g., Ollama, LM Studio) for fully offline AI capabilities.
 * Team Collaboration Features:
   * Sharing custom prompts, personas, and configurations across development teams.
 * More Advanced AI Techniques:
   * Exploration of techniques like RAG (Retrieval Augmented Generation) for enterprise knowledge bases.
