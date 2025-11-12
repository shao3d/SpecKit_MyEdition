<div align="center">
    <h1>🌱 Spec Kit MVP</h1>
    <h3><em>Build high-quality software faster.</em></h3>
</div>

<p align="center">
    <strong>A lightweight toolkit for rapid spec-driven MVP development.</strong>
</p>

<p align="center">
    <a href="https://github.com/shao3d/SpecKit_MVPedition/blob/main/LICENSE"><img src="https://img.shields.io/github/license/shao3d/SpecKit_MVPedition" alt="License"/></a>
    <a href="https://github.com/shao3d/SpecKit_MVPedition/stargazers"><img src="https://img.shields.io/github/stars/shao3d/SpecKit_MVPedition?style=social" alt="GitHub stars"/></a>
</p>

---

## Prerequisites

- Python 3.11 or higher
- [uv](https://docs.astral.sh/uv/) package manager

Install uv:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## 🤔 What is Spec-Driven MVP Development?

Spec-Driven MVP Development **flips the script** on traditional MVP development. For decades, code has been king — specifications were just scaffolding we built and discarded once the "real work" of coding began. Spec-Driven MVP Development changes this: **specifications become executable**, directly generating working MVP implementations rather than just guiding them.

**This toolkit focuses on lightweight, rapid MVP documentation** - perfect for startups, prototypes, and teams that need to move fast without getting bogged down in enterprise-level documentation overhead.

### 🎯 The Constitution: Practical Rules for MVP Success

Every project initialized with Spec Kit includes a `Constitution.md` file containing practical development rules based on three core principles:

- **KISS (Keep It Simple, Stupid):** Always choose the simplest solution that works
- **DRY (Don't Repeat Yourself):** Avoid duplicating business logic
- **YAGNI (You Ain't Gonna Need It):** Don't build features you might need "someday"

**The constitution isn't just philosophy — it's a practical checklist with 10 concrete rules** covering architecture, dependencies, data management, and testing. AI assistants automatically reference these rules when generating technical plans and tasks, ensuring your MVP stays lean and maintainable.

## ⚡ Get Started

This guide describes the lightweight, MVP-focused workflow.

### 1. Install the CLI

Install the tool once using `uv`. This will make the `specify` command available system-wide.
```bash
uv tool install specify-cli --from git+https://github.com/shao3d/SpecKit_MVPedition.git
```
To upgrade:
```bash
uv tool install specify-cli --from git+https://github.com/shao3d/SpecKit_MVPedition.git --force
```

### 2. Initialize Your Project

Navigate to your projects directory and run the `init` command. It will create a new folder with all the necessary templates, including your project's **Constitution.md** with practical MVP development rules.
```bash
# Go to your development folder
cd ~/Documents/Projects

# Create the project
specify init my-new-project
```

**What gets created:**
- 📋 `Constitution.md` - Your project's practical development rules
- 📁 `.specify/templates/` - AI command templates for spec-driven development
- 🗂️ Template files for `spec.md`, `plan.md`, and `tasks.md`
- 📂 Git repository (optional)

### 3. Start the Manual Workflow

This tool prepares a project for a conversational, manual workflow with an AI assistant like Claude Code, Codex, Gemini CLI, etc.

1. Go to the project folder:
    ```bash
    cd my-new-project
    ```

2. Put the `brief.md` file of your new project in the project folder

3. Launch your AI agent (e.g., Claude Code, Codex, Gemini CLI, etc)

4. Start the process with a prompt like:
    ```
    Let's start. Read the instructions from specify.md and my project  brief.md and
      we'll interactively create a draft of spec.md.
    ```

The AI agent will then guide you through the three stages: creating the `spec.md`, `plan.md`, and `tasks.md` files.

### 🤖 How AI Assistants Use Your Constitution

Your project's `Constitution.md` isn't just for humans — AI assistants automatically reference it during development:

- **When creating technical plans (`plan.md`)**: AI reads the Constitution and ensures all architectural decisions and technology choices comply with the practical rules
- **When generating tasks (`tasks.md`)**: AI verifies that the proposed implementation steps don't violate the KISS, DRY, and YAGNI principles

This ensures your MVP stays lean, maintainable, and focused on rapid delivery without unnecessary complexity.

## 📋 MVP Development Principles

### The Constitution Rules

Your project's `Constitution.md` contains 10 practical rules organized into four categories:

#### 🏗️ Architecture & Code
1. **No premature abstractions** - Start simple, refactor to patterns only when you have a second use case
2. **Prefer standard tools** - Use built-in language/framework features before adding libraries
3. **Configuration in code** - Hardcode values initially, avoid complex config systems
4. **Single responsibility functions** - Keep functions short and focused

#### 📦 Dependency Management
5. **Minimal external libraries** - Add dependencies only if they save days, not hours
6. **Choose proven solutions** - Prefer popular, well-maintained libraries over experimental ones

#### 💾 Data & State
7. **Simple data schema** - Start with flat structures, avoid complex relationships initially
8. **Forward-only migrations** - Write one-time scripts instead of complex migration systems

#### 🧪 Pragmatic Testing
9. **Test the main path** - Focus on integration tests for key user scenarios, not 100% coverage
10. **Use mocks sparingly** - Prefer real test dependencies over extensive mocking

### Pre-commit Checklist
Before committing changes, ask yourself:
- [ ] Can I make this simpler? (KISS)
- [ ] Am I duplicating logic elsewhere? (DRY)
- [ ] Do I really need this feature right now? (YAGNI)

## 🔧 Specify CLI Reference

The `specify` command-line tool is used to initialize a new MVP project.

### Commands

| Command | Description                                                        |
|---------|--------------------------------------------------------------------|
| `init`  | Initialize a new MVP project from the bundled lightweight template. |
| `check` | Checks for the installation of `git`.                             |

### `init` Examples

```bash
# Create a new project in a new directory
specify init my-project

# Create a project in the current directory
specify init .

# Create a project without initializing a git repository
specify init my-project --no-git
```

## 🔍 Troubleshooting

### Git Credential Manager on Linux

If you're having issues with Git authentication on Linux, you can install Git Credential Manager:

```bash
#!/usr/bin/env bash
set -e
echo "Downloading Git Credential Manager v2.6.1..."
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.1/gcm-linux_amd64.2.6.1.deb
echo "Installing Git Credential Manager..."
sudo dpkg -i gcm-linux_amd64.2.6.1.deb
echo "Configuring Git to use GCM..."
git config --global credential.helper manager
echo "Cleaning up..."
rm gcm-linux_amd64.2.6.1.deb
```

## 👥 Maintainer

- [shao3d](https://github.com/shao3d)

## 💬 Support

For support, please open a [GitHub issue](https://github.com/shao3d/SpecKit_MVPedition/issues/new). We welcome bug reports, feature requests, and questions about using Spec-Driven MVP Development.

## 🙏 Attribution & Acknowledgments

This project is inspired by and builds upon the original **[Spec Kit](https://github.com/github/spec-kit)** by GitHub.

### Original Spec Kit
- **Repository:** [github/spec-kit](https://github.com/github/spec-kit)
- **Creator:** GitHub, Inc.
- **License:** MIT License

### This MVP Edition
SpecKit_MVPedition is a modernized, lightweight version that:
- Simplifies the original enterprise-level Spec Kit for rapid MVP development
- Optimizes for startups, prototypes, and fast-moving teams
- Maintains the core philosophy of spec-driven development while reducing complexity

**I'am deeply grateful to the original GitHub Spec Kit team for creating such an innovative approach to specification-driven development. Their work laid the foundation for this streamlined MVP edition.**

This project maintains the same MIT license spirit as the original, ensuring open access to the spec-driven development methodology.

## 📄 License

This project is licensed under the terms of the MIT open source license. Please refer to the [LICENSE](./LICENSE) file for the full terms.