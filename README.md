<div align="center">
    <img src="./media/logo_small.webp" alt="Spec Kit Logo"/>
    <h1>🌱 Spec Kit</h1>
    <h3><em>Build high-quality software faster.</em></h3>
</div>

<p align="center">
    <strong>An open source toolkit that allows you to focus on product scenarios and predictable outcomes instead of vibe coding every piece from scratch.</strong>
</p>

<p align="center">
    <a href="https://github.com/github/spec-kit/actions/workflows/release.yml"><img src="https://github.com/github/spec-kit/actions/workflows/release.yml/badge.svg" alt="Release"/></a>
    <a href="https://github.com/github/spec-kit/stargazers"><img src="https://img.shields.io/github/stars/github/spec-kit?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/github/spec-kit/blob/main/LICENSE"><img src="https://img.shields.io/github/license/github/spec-kit" alt="License"/></a>
    <a href="https://github.github.io/spec-kit/"><img src="https://img.shields.io/badge/docs-GitHub_Pages-blue" alt="Documentation"/></a>
</p>

---

## Table of Contents

- [🤔 What is Spec-Driven Development?](#-what-is-spec-driven-development)
- [⚡ Get Started](#-get-started)
- [📽️ Video Overview](#️-video-overview)
- [🤖 Supported AI Agents](#-supported-ai-agents)
- [🔧 Specify CLI Reference](#-specify-cli-reference)
- [📚 Core Philosophy](#-core-philosophy)
- [🌟 Development Phases](#-development-phases)
- [🎯 Experimental Goals](#-experimental-goals)
- [🔧 Prerequisites](#-prerequisites)
- [📖 Learn More](#-learn-more)
- [📋 Detailed Process](#-detailed-process)
- [🔍 Troubleshooting](#-troubleshooting)
- [👥 Maintainers](#-maintainers)
- [💬 Support](#-support)
- [🙏 Acknowledgements](#-acknowledgements)
- [📄 License](#-license)

## 🤔 What is Spec-Driven Development?

Spec-Driven Development **flips the script** on traditional software development. For decades, code has been king — specifications were just scaffolding we built and discarded once the "real work" of coding began. Spec-Driven Development changes this: **specifications become executable**, directly generating working implementations rather than just guiding them.

## ⚡ Get Started

This guide describes the lightweight, MVP-focused workflow.

### 1. Install the CLI

Install the tool once using `uv`. This will make the `specify` command available system-wide.
```bash
# Replace a-sazonov/speckit-mvp with your fork's URL if you have one
uv tool install specify-cli --from git+https://github.com/a-sazonov/speckit-mvp.git
```
To upgrade, run the same command again with `--force`.

### 2. Initialize Your Project

Navigate to your projects directory and run the `init` command. It will create a new folder with all the necessary templates.
```bash
# Go to your development folder
cd ~/Documents/Projects

# Create the project
specify init my-new-project
```

### 3. Start the Manual Workflow

This tool prepares a project for a conversational, manual workflow with an AI assistant like Gemini CLI or Claude.

1.  Navigate into your new project folder:
    ```bash
    cd my-new-project
    ```
2.  Create a brief file (e.g., `brief.md`) describing your project.
3.  Launch your AI assistant (e.g., `gemini`).
4.  Give the assistant its first instruction to start the process:
    ```
    Let's start. Read the instructions from `./.specify/templates/commands/specify.md` and my brief from `./brief.md`, then create a draft of spec.md.
    ```
The assistant will then guide you through the three stages: creating the `spec.md`, `plan.md`, and `tasks.md` files.

For detailed step-by-step instructions, see our [comprehensive guide](./spec-driven.md).

## 📽️ Video Overview

Want to see Spec Kit in action? Watch our [video overview](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)!

[![Spec Kit video header](/media/spec-kit-video-header.jpg)](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)

## 🔧 Specify CLI Reference

The `specify` command-line tool is used to initialize a new MVP project.

### Commands

| Command | Description                                          |
|---------|------------------------------------------------------|
| `init`  | Initialize a new MVP project from the bundled template. |
| `check` | Checks for the installation of `git`.                  |

### `init` Examples

```bash
# Create a new project in a new directory
specify init my-project

# Create a project in the current directory
specify init .

# Create a project without initializing a git repository
specify init my-project --no-git
```

---

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

## 👥 Maintainers

- Den Delimarsky ([@localden](https://github.com/localden))
- John Lam ([@jflam](https://github.com/jflam))

## 💬 Support

For support, please open a [GitHub issue](https://github.com/github/spec-kit/issues/new). We welcome bug reports, feature requests, and questions about using Spec-Driven Development.

## 🙏 Acknowledgements

This project is heavily influenced by and based on the work and research of [John Lam](https://github.com/jflam).

## 📄 License

This project is licensed under the terms of the MIT open source license. Please refer to the [LICENSE](./LICENSE) file for the full terms.
