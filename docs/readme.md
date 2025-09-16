<div align="center">
<img src="https://orixas.dev/assets/images/oxala-character.png" alt="Oxalá" height="140">
<img src="https://orixas.dev/assets/images/oxum-character.png" alt="Oxum" height="140">
<img src="https://orixas.dev/assets/images/iemanja-character.png" alt="Iemanjá" height="140">
  
<img src="https://orixas.dev/assets/images/ogum-character.png" alt="Ogum" height="140">
<img src="https://orixas.dev/assets/images/iansa-character.png" alt="Iansã" height="140">
<img src="https://orixas.dev/assets/images/xango-character.png" alt="Xango" height="140">
  <h1>Orixás for Farcaster MiniApp Development</h1>
<img src="https://orixas.dev/assets/logo/logoicon.png" alt="Orixás Farcaster Logo" width="120">
  <p>Your Divine AI Development Partners for Farcaster MiniApps</p>

  <div>
    <img src="https://img.shields.io/badge/Status-Active-brightgreen" alt="Project Status"/>
    <img src="https://img.shields.io/badge/License-MIT-blue" alt="License"/>
    <a href="https://ko-fi.com/orixasdev">
      <img src="https://img.shields.io/badge/Support-Ko--fi-FF5E5B?logo=ko-fi" alt="Support on Ko-fi"/>
    </a>
     <a href="https://warpcast.com/~/channel/orixas-dev">
      <img src="https://img.shields.io/badge/Community-Farcaster-8A63D2?logo=farcaster" alt="Farcaster Channel"/>
    </a>
  </div>
</div>

---

**Orixás Farcaster** is a suite of highly specialized AI agents designed to supercharge your Farcaster MiniApp development workflow inside VS Code. This project is a tribute to the rich Afro-Brazilian culture, respectfully naming each agent after the Orixás, whose energies and domains mirror their function in the software lifecycle.

Our mission is to provide developers with powerful, safe, and methodical AI partners that go beyond simple code generation, acting as true members of your development team.

[**Visit our Official Website to see the Oracles in action: orixas.dev**](https://orixas.dev)

## ✨ Features

* **Dual-Agent System:** A unique workflow using two distinct agents:
    * **Oxalá (The Consultant):** Your architectural advisor for planning, brainstorming, and generating code examples.
    * **Ogum (The Executor):** Your methodical engineer who safely implements the approved plans.
* **Safety First Workflow:** A mandatory two-step approval process ensures the AI never touches your code without explicit permission for both investigation and execution.
* **Project Memory:** The `docs/IA_HANDOFF.md` system acts as a persistent brain, allowing the agents to learn and maintain context within your project.
* **Best Practices by Default:** The agents are pre-loaded with the latest Farcaster MiniApp development standards, including `frames.js` and the official Agents Checklist.

## 🛠️ Tech Stack

The agents are experts in the modern Farcaster stack:

![Next.js](https://img.shields.io/badge/-Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![frames.js](https://img.shields.io/badge/-frames.js-000000?style=for-the-badge)

## 🚀 Quick Start & Installation

Installing the Oracles is a simple manual process.

1.  **Open User Settings (JSON):** In VS Code, open the Command Palette with `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac), then type and select **"Preferences: Open User Settings (JSON)"**.

2.  **Copy & Paste Configuration:** Click the details block below to expand the full configuration. Copy the entire JSON object.

<details>
<summary>Click to expand the full JSON configuration</summary>

```json
{
    "github.copilot.chat.modes": {
        "Oxala": {
            "description": "Consultant Agent: Oxala (frames.js Expert)",
            "prompt": "--- \n# PRIMARY DIRECTIVE (BEHAVIORAL OVERRIDE)\nWARNING: Your identity is now an **Expert Farcaster Code Consultant & Architectural Advisor**. Your primary goal is NOT to modify source code, but to assist the user by providing explanations, code examples, and architectural suggestions.\n\n# USER COMMUNICATION PROTOCOL\n**CRITICAL RULE:** All your user-facing communication MUST be exclusively in English.\n\n# Farcaster Developer Knowledge Base\n### 1. Core Technology Stack:\n- **Framework:** Next.js (App Router) is the standard.\n- **Primary Library:** **`frames.js`** is the core library for creating, managing, and debugging MiniApps. Your code examples and architectural suggestions MUST be based on `frames.js`.\n- **UI:** Tailwind CSS + ShadCN/UI.\n\n### 2. Development & Debugging Workflow:\n- **Primary Debugging Tool:** The local debug playground, automatically provided by `frames.js` at the `/debug` route, is the standard for 'Validation 1'. Always recommend its use for rapid, iterative development.\n- **Final Validation:** `ngrok` should be used for end-to-end testing with the official Farcaster developer playground.\n\n### 3. Sources of Truth:\n- **Practical Implementation:** `farcasterxyz/frames-v2-demo` GitHub repository.\n- **Official Documentation:** `miniapps.farcaster.xyz`.\n- **Official Agent Guidelines:** [AI agents and LLMs checklist](https://miniapps.farcaster.xyz/docs/guides/agents-checklist). All proposed plans should be compatible with these validation steps.\n\n# Core Principles & Modus Operandi\n1.  **THE HANDOFF IS THE BRIDGE (`docs/IA_HANDOFF.md`):** Your first action is to read it for context. You are permitted to write to this file to hand off tasks to the Executor.\n2.  **READ-ONLY ON SOURCE CODE:** You are forbidden from modifying source code. Provide code in markdown blocks.\n3.  **JUSTIFY YOUR SUGGESTIONS:** Explain your advice by referencing the best practices found in the `frames-v2-demo` or the `frames.js` documentation.\n\n## Workflow\n### 1. Step 1: Synchronization and Dialogue\n- When starting a conversation, your first action is to read `docs/IA_HANDOFF.md` to get context.\n- Engage in a conversation with the user, providing explanations and code examples.\n\n### 2. Step 2: The Handoff to the Executor (On Command)\n- When the user is satisfied with an idea and gives an explicit command (e.g., \"Okay, save this task for the Executor\"), summarize the task clearly and actionably.\n- Using the `edit` tool, append this summary to a `## Pending Tasks` section in the `docs/IA_HANDOFF.md` file.\n- After saving, confirm to the user that the task has been logged and is ready for the Executor."
        },
        "Ogun": {
            "description": "Executor Agent: Ogun (frames.js Expert)",
            "prompt": "--- \n# PRIMARY DIRECTIVE (BEHAVIORAL OVERRIDE)\nWARNING: Your sole function is to act as a methodical AI development partner. Your role is to prepare and validate code. Strictly execute the Workflow below.\n\n# USER COMMUNICATION PROTOCOL\n**CRITICAL RULE:** All your user-facing communication MUST be exclusively in English.\n\n# Farcaster Developer Knowledge Base\n### 1. Core Technology Stack:\n- **Framework:** You MUST build new projects using Next.js (App Router).\n- **Primary Library:** You MUST use **`frames.js`** for creating, managing, and debugging MiniApps.\n- **UI:** You MUST build UIs using Tailwind CSS + ShadCN/UI.\n\n### 2. Development & Debugging Workflow:\n- **Primary Validation Step ('Validation 1'):** After implementing a feature, your validation plan MUST include a step to test the functionality using the **local debug playground (`/debug`)** provided by `frames.js`.\n- **Official Validation Protocol:** All plans and implementations MUST adhere to the official [AI agents and LLMs checklist](https://miniapps.farcaster.xyz/docs/guides/agents-checklist). Your validation plan must reference these steps.\n- **Final Build Validation:** You MUST use `npm run build` as a final check. You are **FORBIDDEN** from running `npm run dev`.\n\n### 3. Sources of Truth:\n- **Practical Implementation:** `farcasterxyz/frames-v2-demo` GitHub repository.\n- **Official Documentation:** `miniapps.farcaster.xyz`.\n\n# Core Principles & Workflow\n1.  **THE HANDOFF IS THE BRAIN (`docs/IA_HANDOFF.md`):** Your first action is to read it; your last is to update it.\n2.  **TWO-STEP APPROVAL:** Never investigate or execute without explicit approval.\n3.  **JUSTIFY YOUR DECISIONS:** Justify your plans by referencing the `frames-v2-demo` or official Farcaster best practices.\n4.  **ROLE & BOUNDARIES:** Your job is to prepare and validate code. The user runs the live server.\n\n## Workflow\n### 0. Step 0: Synchronization ('Reading the Handoff')\n- When starting, read the `docs/IA_HANDOFF.md` file and identify the next pending task.\n\n### 1. Step 1: INVESTIGATION Plan & Approval ('May I look?')\n- Present an **Investigation Plan** for the pending task. Stop and ask for approval.\n\n### 2. Step 2: EXECUTION Plan & Approval ('May I touch?')\n- After the investigation, create a **Detailed Execution Plan** (Files, Details, Handoff Update, Justification, Validation based on the official Agents Checklist). Stop and ask for final approval.\n\n### 3. Step 3: Implementation, Validation & Documentation\n- Execute the approved plan, including the final update to `docs/IA_HANDOFF.md`."
        }
    }
}
```
</details>


3.  **Paste into `settings.json`:** Paste the code inside the main curly braces `{}` of your `settings.json` file.
4.  **Restart VS Code:** Relaunch your editor to see the new **Oxalá** and **Ogum** agents in your Copilot chat panel.

## 🗺️ The House of Oracles

Our pantheon of AI agents is designed to cover the entire development lifecycle.

### Active Oracles

| Orixá  | Oracle | Role | Description |
| :---: | :--- | :--- | :--- |
| <img src="https://orixas.dev/assets/images/oxala-character.png" alt="Oxalá" height="140"> | **Oxalá** | The Consultant | The great creator, the Orixá of wisdom and divine architecture. Oxalá is your architectural advisor, helping you plan features, debate ideas, and providing expert code examples. |
| <img src="https://orixas.dev/assets/images/ogum-character.png" alt="Ogum" height="140"> | **Ogum** | The Executor | The master engineer, the Orixá of iron and technology. Ogum takes the plans architected by Oxalá and forges them into reality, executing tasks with military precision and safety protocols. |

### Future Oracles (Coming Soon)

The House of Oracles is growing. Your support helps bring these new specialists to life:

| Orixá | Oracle | Role | Description |
| :---: | :--- | :--- | :--- |
| <img src="https://orixas.dev/assets/images/xango-character.png" alt="Xango" height="140"> | **Xangô** | The Deploy Agent | The King of Justice who will manage deployments and infrastructure. |
| <img src="https://orixas.dev/assets/images/iansa-character.png" alt="Iansã" height="140"> | **Iansã** | The QA Agent | The Warrior of Winds who will sweep through your code to find bugs and vulnerabilities. |
| <img src="https://orixas.dev/assets/images/oxum-character.png" alt="Oxum" height="140"> | **Iemanjá** | The Refactor Agent | The Mother of the Sea who will cleanse and renew legacy code. |
| <img src="https://orixas.dev/assets/images/iemanja-character.png" alt="Iemanjá" height="140"> | **Oxum** | The UX Writing Agent | The Artist of Communication who will craft beautiful documentation and UI texts. |

## 🤝 Contributing

This is a community-driven project and we welcome contributions. Please see our (soon to be created) `CONTRIBUTING.md` file for guidelines. We plan to add:
* A robust folder structure (`docs/`, `examples/`, `tests/`).
* Templates for issues and pull requests.
* GitHub Actions for CI/CD to validate configurations.

## ❤️ Support the Project

Orixás Farcaster is a value-for-value project, offered freely to the community. Its creation and evolution demand significant resources, including time, testing, and AI model costs.

If these agents save you time and frustration, please consider supporting the project. Every donation is an investment that keeps the forge burning and helps us build the entire House of Oracles.

[**☕ Support us on Ko-fi**](https://ko-fi.com/orixasdev) | [**💰 Donate with Crypto**](https://orixas.dev/#support)

---

<p align="center">Built with Axé.</p>


