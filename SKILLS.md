# AI Skills & Automation Guide - WebToApp

This file defines the available automations and specialized instructions for AI agents working on this project.

## 🛠️ Automated Workflows (Skills)

### 1. Build Debug APK (`debug-apk.yml`)
- **Trigger:** Manual (`workflow_dispatch`).
- **Purpose:** Generates a testable APK.
- **AI Guidance:** Use this to verify that the app compiles after significant UI or logic changes.

### 2. Quality Gate (`quality-gate.yml`)
- **Trigger:** Pull Requests to `main`.
- **Purpose:** Runs Android Lint to ensure code quality and style.
- **AI Guidance:** Always check lint results before merging features. If a new component is added, ensure it doesn't introduce accessibility or performance warnings.

### 3. Dependency Tracker (`dependency-submission.yml`)
- **Trigger:** Push to `main`.
- **Purpose:** Submits the dependency graph to GitHub for security monitoring (Dependabot).
- **AI Guidance:** When updating `libs.versions.toml`, this workflow ensures GitHub knows about the changes.

## 🤖 AI Execution Rules (Skills Enhancement)

### Gradle Mastery
- **No Wrapper:** AI must remember to use `setup-gradle` action in CI because `gradlew` is missing.
- **Dot Notation:** Access `libs` with dots only.
  - ✅ `libs.androidx.material3`
  - ❌ `libs.androidx-material3`

### UI Integrity
- **Compose Only:** Never suggest XML layouts.
- **Material 3 Expressive:** Use the latest Material 3 components and maintain the **Floating Header** navigation pattern.

### Testing Strategy
- **Manual Verification:** Since there's no automated emulator testing yet, AI should suggest manual verification points for the WebView (cache, JS, DOM storage).

## 🎯 How to use these "Skills"
When an AI agent is asked to "run quality checks" or "prepare a release", it should look at the workflows in `.github/workflows/` and ensure it follows the constraints defined in `AGENTS.md` and this `SKILLS.md` file.
