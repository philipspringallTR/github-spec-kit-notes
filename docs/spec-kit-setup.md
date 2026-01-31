# 🚀 Cursor x GitHub Spec Kit: Team Setup Guide

**Date:** January 15, 2026  

This repository utilizes **Spec-Driven Development (SDD)**. This structured workflow ensures that the AI understands the **What**, **How**, and **Action Plan** before a single line of code is modified.

---

## 🛠️ Phase 1: Environment Setup
All team members must have **Git** and **UV** installed and globally accessible in their system PATH.

### 1. Install Dependencies (Windows/PowerShell)
```powershell
# Install Git
winget install --id Git.Git -e --source winget

# Install UV (Python/Tool Manager)
powershell -ExecutionPolicy ByPass -c "irm [https://astral.sh/uv/install.ps1](https://astral.sh/uv/install.ps1) | iex"
```

> **IMPORTANT:** Restart Cursor completely after running these commands so the editor recognizes the new system paths.

### 2. Initialize the Project
Run this in the project root to install the "Rulebook" and slash commands.
```powershell
uvx --from git+[https://github.com/github/spec-kit.git](https://github.com/github/spec-kit.git) specify init . --ai cursor-agent
```
* **Target AI:** Select `cursor-agent`.
* **Script Type:** Select `ps` (PowerShell).
* **Confirmation:** Type `y` to allow it to merge the `.specify` and `.cursor/rules` folders.

---

## 📚 Phase 2: Command Reference
Once set up, open a **New Agent** (`Ctrl + N`) in Cursor. These commands are now available via the `/` menu.

### Core Workflow Commands
| Command | Role | Why it's useful |
| :--- | :--- | :--- |
| **`/speckit.constitution`** | **The Law** | Establishes the tech stack and coding standards. It acts as a permanent guardrail for the AI. |
| **`/speckit.specify`** | **The Architect** | Defines the **What** and **Why**. It creates a `spec.md` focused on user needs. |
| **`/speckit.plan`** | **The Engineer** | Defines the **How**. It reads the Spec and Constitution to create a technical blueprint (`plan.md`). |
| **`/speckit.tasks`** | **The PM** | Breaks the Plan into a checklist (`tasks.md`) for small, safe, trackable changes. |

### Quality & Logic Commands
| Command | Role | Why it's useful |
| :--- | :--- | :--- |
| **`/speckit.analyze`** | **The Auditor** | **Run this after tasks.** It cross-checks the Spec, Plan, and Constitution to find errors before coding starts. |
| **`/speckit.clarify`** | **The Researcher** | If your request is vague, the AI will interview you with questions to fill in the gaps. |
| **`/speckit.implement`** | **The Worker** | Tells the Agent to begin executing the `tasks.md` list sequentially. |

---

## 🔄 Phase 3: The Daily "Standard Loop"
To add a new feature or fix a bug, follow this exact sequence:

1. **Set the Law:** Run `/speckit.constitution` (only needed once per project).
2. **Define Intent:** `/speckit.specify [feature name]` -> Review `spec.md`.
3. **Technical Design:** `/speckit.plan` -> Review `plan.md`.
4. **Task Breakdown:** `/speckit.tasks`.
5. **Audit:** `/speckit.analyze` (Ensure everything aligns with the Law).
6. **Build:** `/speckit.implement`.

---

## ⚠️ Troubleshooting
* **Slash commands missing?** You must be in a **New Agent** session (`Ctrl + N`).
* **"Git not found"?** Run `$env:Path += ";$env:USERPROFILE\.local\bin"` to force the path for the current session.

---
