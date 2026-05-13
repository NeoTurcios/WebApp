# AI Agent Context - WebToApp

This file provides context for AI assistants (like Gemini CLI, Cursor, etc.) to understand the architecture and constraints of this project.

## Project Identity
- **Name:** WebToApp
- **Type:** Android Application (WebView-based)
- **Tech Stack:** Kotlin, Jetpack Compose, Material 3 Expressive, OpenJDK 21.

## Architectural Constraints
- **Language:** Strictly Kotlin. No Java files allowed.
- **Source Layout:** Follows the modern standard: `src/main/kotlin/` instead of `src/main/java/`.
- **UI:** Exclusively Jetpack Compose. No XML layouts for UI.
- **Theming:** Material 3 with dynamic color support and dark/light mode manual toggle in a floating header.
- **WebView:** Must have JS enabled and proper caching.

## Customization Map
- **URL:** Managed in `MainActivity.kt` -> `MainScreen`.
- **Package:** `app/build.gradle.kts` (`applicationId`) and directory structure.
- **Resources:** `app/src/main/res/`.

## Workflow
- **Builds:** Automated via GitHub Actions (`.github/workflows/`).
- **Target SDK:** 35 (latest stable).
- **Min SDK:** 24.

## Guidelines for AI
1. When adding features, ensure they align with the **minimalist** and **modern** aesthetic.
2. Maintain the **Floating Header** pattern for navigation or settings.
3. Always use **Kotlin DSL** for Gradle files (`.gradle.kts`).
4. Ensure all new components are documented in `README.md` if they require user configuration.
