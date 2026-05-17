# Project Instructions - WebToApp

This project is a modern Android WebView application using Jetpack Compose and Material 3 Expressive.

## 🛠️ Build & Development
- **No Gradlew:** The project does not include the Gradle wrapper. Always use the system `gradle` command or the `setup-gradle` action in CI.
- **Gradle Syntax:** In `.gradle.kts` files, access the Version Catalog (`libs`) using dot notation for all parts (e.g., `libs.androidx.ui.graphics` instead of `libs.androidx-ui-graphics`).
- **JDK 21:** Ensure the environment is set to Java 21.

## 🤖 AI Coordination
- Refer to `AGENTS.md` for detailed architectural constraints and UI patterns.
- Keep components minimalist and follow the **Floating Header** pattern.
- Always update `AGENTS.md` if a significant architectural change or "lesson learned" occurs to prevent future AI agents from repeating mistakes.
