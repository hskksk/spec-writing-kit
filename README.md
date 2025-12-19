<div align="center">
    <img src="./media/logo_large.webp" alt="Spec Writing Kit Logo" width="200" height="200"/>
    <h1>🖋️ Spec Writing Kit</h1>
    <h3><em>Structure your writing, faster.</em></h3>
</div>

<p align="center">
    <strong>An open source toolkit that applies spec-driven principles to all forms of writing—from blog posts to books—systematizing your creative process for high-quality, consistent content.</strong>
</p>

<p align="center">
    <a href="https://github.com/hskksk/spec-writing-kit/actions/workflows/release.yml"><img src="https://github.com/hskksk/spec-writing-kit/actions/workflows/release.yml/badge.svg" alt="Release"/></a>
    <a href="https://github.com/hskksk/spec-writing-kit/stargazers"><img src="https://img.shields.io/github/stars/hskksk/spec-writing-kit?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/hskksk/spec-writing-kit/blob/main/LICENSE"><img src="https://img.shields.io/github/license/hskksk/spec-writing-kit" alt="License"/></a>
    <a href="https://hskksk.github.io/spec-writing-kit/"><img src="https://img.shields.io/badge/docs-GitHub_Pages-blue" alt="Documentation"/></a>
</p>

---

## Table of Contents

- [🤔 What is Spec-Driven Writing?](#-what-is-spec-driven-writing)
- [⚡ Get Started](#-get-started)
- [✍️ The Writing Process](#️-the-writing-process)
- [🤖 Supported AI Agents](#-supported-ai-agents)
- [🔧 CLI Reference](#-cli-reference)
- [📚 Core Philosophy](#-core-philosophy)
- [🔧 Prerequisites](#-prerequisites)
- [👥 Maintainers](#-maintainers)
- [💬 Support](#-support)
- [📄 License](#-license)

## 🤔 What is Spec-Driven Writing?

**Spec-Driven Writing** adapts the principles of Spec-Driven Development to the world of content creation. Instead of treating outlines and notes as disposable artifacts, this methodology turns them into a structured, executable framework. Your writing plan becomes a clear roadmap that an AI agent can follow to research, draft, and compose high-quality content, ensuring your initial vision is precisely realized.

## ⚡ Get Started

### 1. Install WritKit CLI

Choose your preferred installation method:

#### Option 1: Persistent Installation (Recommended)

```bash
uv tool install writekit-cli --from git+https://github.com/hskksk/spec-writing-kit.git
```

*Note: The package name and source URL will be updated once this fork is established as its own project.*

Then use the tool directly:

```bash
# Create new project
writekit init <PROJECT_NAME>

# Or initialize in an existing directory
writekit init . --ai claude
```

#### Option 2: One-time Usage

```bash
uvx --from git+https://github.com/hskksk/spec-writing-kit.git specify init <PROJECT_NAME>
```

### 2. Begin the Writing Process

Launch your AI assistant in the project directory. The `/writekit.*` commands will be available to guide you through the writing lifecycle. See [The Writing Process](#️-the-writing-process) below for details.

## ✍️ The Writing Process

Follow these steps to move from an idea to a finished piece of writing.

### 1. Define Your Constitution

Use **`/writekit.constitution`** to set the foundational principles for your content. This defines the tone, style, target audience, and ethical guidelines.

```bash
/writekit.constitution Create a formal, authoritative tone for a technical audience. The writing should be in the third person and cite all sources.
```

### 2. Specify Your Content

Use **`/writekit.specify`** to outline *what* you want to write. Detail the topic, key arguments, goals, and what to exclude.

```bash
/writekit.specify Write a blog post explaining the benefits of Spec-Driven Writing. Cover its origins in software development, the core steps of the process, and its advantages for technical writers.
```

### 3. Plan the Structure

Use **`/writekit.plan`** to design *how* you will write it. This includes the content structure, section-by-section breakdown, and where to use media like diagrams or code snippets.

```bash
/writekit.plan Structure the blog post with an introduction, a section for each of the 6 process steps, a comparison table, and a concluding summary.
```

### 4. Conduct Research

Use **`/writekit.research`** to gather facts, data, and supporting evidence for your arguments.

```bash
/writekit.research Find studies or articles on the impact of structured methodologies on writing quality and efficiency.
```

### 5. Break Down into Tasks

Use **`/writekit.tasks`** to create a detailed, actionable checklist for the entire writing process.

```bash
/writekit.tasks
```

### 6. Write the Content

Use **`/writekit.write`** to execute the writing plan and generate the final content based on the previous steps.

```bash
/writekit.write
```

## 🤖 Supported AI Agents

| Agent                                                                                | Support | Notes                                                                                                                                     |
| ------------------------------------------------------------------------------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [Qoder CLI](https://qoder.com/cli)                                                   | ✅      |                                                                                                                                           |
| [Amazon Q Developer CLI](https://aws.amazon.com/developer/learning/q-developer-cli/) | ⚠️      | Amazon Q Developer CLI [does not support](https://github.com/aws/amazon-q-developer-cli/issues/3064) custom arguments for slash commands. |
| [Amp](https://ampcode.com/)                                                          | ✅      |                                                                                                                                           |
| [Auggie CLI](https://docs.augmentcode.com/cli/overview)                              | ✅      |                                                                                                                                           |
| [Claude Code](https://www.anthropic.com/claude-code)                                 | ✅      |                                                                                                                                           |
| [CodeBuddy CLI](https://www.codebuddy.ai/cli)                                        | ✅      |                                                                                                                                           |
| [Codex CLI](https://github.com/openai/codex)                                         | ✅      |                                                                                                                                           |
| [Cursor](https://cursor.sh/)                                                         | ✅      |                                                                                                                                           |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli)                            | ✅      |                                                                                                                                           |
| [GitHub Copilot](https://code.visualstudio.com/)                                     | ✅      |                                                                                                                                           |
| [IBM Bob](https://www.ibm.com/products/bob)                                          | ✅      | IDE-based agent with slash command support                                                                                                |
| [Jules](https://jules.google.com/)                                                   | ✅      |                                                                                                                                           |
| [Kilo Code](https://github.com/Kilo-Org/kilocode)                                    | ✅      |                                                                                                                                           |
| [opencode](https://opencode.ai/)                                                     | ✅      |                                                                                                                                           |
| [Qwen Code](https://github.com/QwenLM/qwen-code)                                     | ✅      |                                                                                                                                           |
| [Roo Code](https://roocode.com/)                                                     | ✅      |                                                                                                                                           |
| [SHAI (OVHcloud)](https://github.com/ovh/shai)                                       | ✅      |                                                                                                                                           |
| [Windsurf](https://windsurf.com/)                                                    | ✅      |                                                                                                                                           |

## 🔧 CLI Reference

The `writekit` command supports the following options.

### `writekit` Commands

| Command | Description                                      |
| ------- | ------------------------------------------------ |
| `init`  | Initialize a new Spec Writing Kit project.       |
| `check` | Check for installed AI agent tools.              |

### Available Slash Commands

After running `writekit init`, your AI agent will have access to these slash commands for structured writing:

| Command                  | Description                                            |
| ------------------------ | ------------------------------------------------------ |
| `/writekit.constitution` | Create or update the writing principles and style guide. |
| `/writekit.specify`      | Define the content's topic, scope, and objectives.     |
| `/writekit.plan`         | Create a detailed structural plan for the content.     |
| `/writekit.research`     | Conduct research to gather information and sources.    |
| `/writekit.tasks`        | Generate actionable writing tasks from the plan.       |
| `/writekit.write`        | Execute the writing tasks to produce the final draft.  |

## 📚 Core Philosophy

Spec-Driven Writing is a structured process that emphasizes:

- **Intent-driven creation**, where the *what* and *why* are defined before the *how*.
- **Structured planning**, using clear principles and outlines to guide the creative process.
- **Multi-step refinement** rather than one-shot generation from a single prompt.
- **AI collaboration**, leveraging AI for research, drafting, and execution based on a human-defined plan.

## 🔧 Prerequisites

- **Linux/macOS/Windows**
- A [Supported AI Agent](#-supported-ai-agents).
- [uv](https://docs.astral.sh/uv/) for package management.
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

## 👥 Maintainers

This project is currently maintained by the forking user. Original project maintainers:

- Den Delimarsky ([@localden](https://github.com/localden))
- John Lam ([@jflam](https://github.com/jflam))

## 💬 Support

For support, please open a GitHub issue in this repository.

## 🙏 Acknowledgements

This project is a fork of and heavily influenced by the work and research of [John Lam](https://github.com/jflam) and [Den Delimarsky](https://github.com/localden) on the original `spec-kit`.

## 📄 License

This project is licensed under the terms of the MIT open source license. Please refer to the [LICENSE](./LICENSE) file for the full terms.
