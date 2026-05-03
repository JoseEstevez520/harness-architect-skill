<p align="center">
  <a href="https://github.com/JoseEstevez520/harness-architect-skill">
    <img src="https://img.shields.io/badge/repo-JoseEstevez520/harness--architect--skill-blue?logo=github" alt="GitHub" />
  </a>
  <img src="https://img.shields.io/badge/status-active-brightgreen" alt="Status" />
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License" />
  <img src="https://img.shields.io/badge/version-1.0.0-purple" alt="Version" />
</p>

# Agentic Harness Standard (AHS)

> A modular infrastructure framework for building agent-legible software environments. Implements deterministic validation, persistent state, and custom harness engineering.

**AHS** is a minimalist framework that shifts human effort from writing code to designing environments where AI agents can operate with maximum autonomy, reliability, and continuity across sessions.

### 🚀 Compatible Platforms
Designed to work seamlessly with any agentic environment, including:
- **CLI Agents:** Claude Code, OpenCode, Aider.
- **IDE Extensions:** Windsurf, Cursor, Cline, Roo Code.
- **Custom Agents:** Antigravity and any agent with shell/tool access.


---

## Table of Contents

- [The Formula](#the-formula)
- [Core Components](#core-components)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage Modes](#usage-modes)
- [Project Structure](#project-structure)
- [Guiding Principles](#guiding-principles)
- [License](#license)

---

## The Formula

A reliable autonomous agent is defined by:

$$\text{Agent} = \text{Model} + \text{Harness}$$

The **Harness** provides the three pillars an agent needs to operate without technical drift:

| Pillar | Purpose | Implementation |
|--------|---------|---------------|
| **Constraints (Rules)** | Define boundaries and patterns | `rules/patterns.md` |
| **Feedback Loops (Hooks)** | Real-time validation on every action | `hooks/PostToolUse` |
| **Institutional Memory (State)** | Persist decisions across sessions | `.agent/` directory |

---

## Core Components

| Component | Description |
|-----------|-------------|
| **`AGENTS.md`** | Technical contract and entry point for all agents — the first file every agent reads. |
| **`hooks/`** | Self-executing validation scripts (e.g., `PostToolUse`) registered via `settings.json`. |
| **`rules/`** | Architectural and coding constraints that define allowable patterns. |
| **`skills/`** | Procedural capabilities for domain-specific tasks (e.g., `/debug`, `/lint`). |
| **`.agent/`** | Persistent state directory with `LOG.md` (session history) and `CONTEXT.md` (architecture map). |

---

## Features

- **Agent-Legible by Design** — Every file follows a convention that agents can parse and act upon without ambiguity.
- **Deterministic Validation** — Shell-based hooks provide objective pass/fail checks, eliminating subjective agent self-assessment.
- **Zero Amnesia** — All critical decisions are logged in `.agent/LOG.md`, ensuring seamless handoff between agent sessions.
- **Self-Evolving** — The `harness-architect-skill/` meta-skill allows the harness to audit and improve itself over time.
- **Framework Agnostic** — Works with any language, stack, or agent platform.

---

## Getting Started

### Prerequisites

- An AI agent platform that supports custom skills and hooks.
- (Optional) Git for version control and hook registration.

### Installation

1. Clone the repository or copy `harness-architect-skill/` into your agent's skills path:

   ```
   git clone https://github.com/JoseEstevez520/harness-architect-skill.git
   ```

2. Invoke the skill:

   ```
   Use harness-architect to initialize a new harness.
   ```

   Or for an existing project:

   ```
   Use harness-architect to optimize this project's harness based on [description].
   ```

3. The skill will generate the full harness structure, register hooks, and log initialization in `.agent/LOG.md`.

### 💡 Usage Example

**Scenario:** You want to initialize a new project with a robust agentic structure.

> **User:** "Activate the `harness-architect` skill to initialize a new Node.js API project following the AHS standard."
>
> **Agent:** "Analyzing requirements... Generating `AGENTS.md`, configuring validation hooks in `/hooks`, and creating design rules in `rules/patterns.md`. The environment is now **Agent-Legible**."


---

## Usage Modes

### Scaffold Mode

Generates a complete, production-ready harness for a new project with all core components preconfigured:

- `AGENTS.md` with setup, build, and test commands.
- Boilerplate `hooks/PostToolUse` for architecture validation.
- Empty `rules/patterns.md` ready for custom constraints.
- Standard skills like `/debug` for troubleshooting.
- Initialized `.agent/LOG.md` and `.agent/CONTEXT.md`.

### Optimization Mode

Analyzes an existing project description, tech stack, or codebase to design a customized harness:

1. **Analysis** — Identifies critical architectural requirements, naming conventions, and common failure points.
2. **Custom Rules** — Designs `rules/patterns.md` specific to the project (e.g., React patterns, API security constraints).
3. **Tailored Hooks** — Writes `hooks/PostToolUse` logic that validates the project's specific design system.
4. **Context Mapping** — Populates `.agent/CONTEXT.md` with a high-level overview of the system design.

---

## Project Structure

```
agentic-harness-blueprint/
├── AGENTS.md                # Agent entry point
├── README.md                # This file
├── settings.json            # Hook registration and agent config
├── .agent/                  # Persistent state
│   ├── CONTEXT.md           # Architecture map
│   └── LOG.md               # Decision history
├── harness-architect-skill/ # Meta-skill for self-modification
│   └── SKILL.md
├── hooks/                   # Validation layer
│   └── PostToolUse
├── rules/                   # Constraint layer
│   └── patterns.md
└── skills/                  # Capability layer
    └── debug/
        └── SKILL.md
```

---

## Guiding Principles

- **Simplicity Scales** — Every rule must solve a recurring friction point. If it doesn't, it doesn't belong.
- **Deterministic Truth** — Shell-based verification always beats agent self-assessment.
- **Zero Amnesia** — No critical decision is left undocumented. Continuity is enforced by design.
- **Handoff Ready** — A new agent must be able to take over the project by reading `.agent/` alone.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
