# Getting Started with Orixás Farcaster

Welcome! This guide will walk you through your first development cycle using the Orixás Farcaster agents. You'll learn how to leverage the unique dual-agent workflow to go from a simple idea to implemented code, safely and efficiently.

## Prerequisites

Before you begin, please ensure you have:
1.  **VS Code** installed.
2.  **GitHub Copilot Chat** enabled.
3.  The **Oxalá** and **Ogum** agents installed in your VS Code. If you haven't done this, please follow the instructions in our main [**README.md**](https://github.com/your-repo/orixas-farcaster/blob/main/README.md).

## The Divine Workflow: An Overview

The power of Orixás Farcaster lies in its separation of roles, just like in a professional development team.

* **Oxalá (The Consultant):** He is your **Architect**. You talk to him to brainstorm ideas, ask for code examples, and define *what* needs to be built.
* **Ogum (The Executor):** He is your **Engineer**. He takes the plans created by Oxalá and physically builds them, writing and modifying the files in your project.
* **The `IA_HANDOFF.md` file:** This is the **bridge** between them. It's a document where Oxalá writes down the approved tasks for Ogum to execute.

You **plan** with Oxalá, and Ogum **builds**. This ensures no code is ever written without a clear plan and your explicit approval.

---

## Your First Feature: A Step-by-Step Guide

Let's build a simple "Hello World" button component.

### Step 1: The Idea (Consult with Oxalá)

First, open the Copilot chat in VS Code and select the **Oxalá** agent. Your goal is to get a good code example and validate your idea.

**Your Prompt to Oxalá:**
> `@Oxala, I need to create a simple 'Hello World' button component for my Farcaster MiniApp. It should use React and Tailwind CSS. Can you give me the basic code for it?`

**Oxalá's Expected Response:**
> Of course. Here is a clean, simple implementation for a `HelloWorldButton` component using React and Tailwind CSS, as you requested.
>
> ```typescript
> // src/components/HelloWorldButton.tsx
> 'use client';
>
> import React from 'react';
>
> const HelloWorldButton = () => {
>   const handleClick = () => {
>     alert('Hello World from the Oracles!');
>   };
>
>   return (
>     <button
>       onClick={handleClick}
>       className="px-6 py-3 bg-blue-500 text-white font-bold rounded-full hover:bg-blue-600 transition-colors"
>     >
>       Say Hello
>     </button>
>   );
> };
>
> export default HelloWorldButton;
> ```
>
> This component is self-contained and uses a simple `alert` for the action. Does this align with what you had in mind?

### Step 2: The Handoff (Automated Task Creation)

You've reviewed the code with Oxalá and it's exactly what you want. Now, you instruct him to prepare the task for Ogum.

**Your Prompt to Oxalá:**
> `@Oxala, this is perfect. Please save this task to the IA_HANDOFF.md file for Ogum to implement.`

**Oxalá's Expected Response:**
> Understood. I will now add the task "Create the HelloWorldButton.tsx component as defined and add it to the main page" to the `## Pending Tasks` section of `docs/IA_HANDOFF.md`.
>
> *(He uses the `edit` tool to update the file)*
>
> The task has been successfully logged. You can now activate the Ogum agent to begin the implementation.

### Step 3: The Execution (Activate Ogum)

Now, switch to the **Ogum** agent in the Copilot chat. His job is to read the handoff file and execute the pending tasks.

**Your Prompt to Ogum:**
> `@Ogun, please start the next pending task from the handoff file.`

**Ogum's Expected Response:**
> Understood. Reading `docs/IA_HANDOFF.md`.
>
> The next pending task is: "Create the HelloWorldButton.tsx component as defined and add it to the main page."
>
> I will now proceed with the **Investigation Phase** to locate the relevant files.

### Step 4: The Investigation Plan ("May I look?")

Ogum will not touch any files without first getting your permission to look. He will present a plan for what he needs to read.

**Ogum's Expected Response:**
> **Investigation Plan:**
> 1. I need to list the files in `src/app/` to identify the main page component (likely `page.tsx`).
> 2. I need to check if a `src/components/` directory already exists.
>
> This is a read-only investigation. **Do you approve this plan?**

**Your Response:**
> `Yes, approved.`

### Step 5: The Execution Plan ("May I touch?")

After investigating, Ogum will present a detailed plan of exactly what he will create and modify.

**Ogum's Expected Response:**
> Investigation complete. The main page is `src/app/page.tsx`.
>
> **Execution Plan:**
> 1. **Create File:** `src/components/HelloWorldButton.tsx` with the specified React code.
> 2. **Modify File:** `src/app/page.tsx` to import and render the new `HelloWorldButton` component.
> 3. **Update Handoff:** Mark the task as "Completed" in `docs/IA_HANDOFF.md`.
>
> **Validation Plan:**
> 1. After implementation, I will run `npm run build` to ensure the project compiles without errors.
>
> **Do you approve this execution plan?**

**Your Response:**
> `Yes, go ahead.`

### Step 6: Task Complete

Ogum will now execute the plan, creating and modifying the files. His final message will confirm the completion and validation.

**Ogum's Expected Response:**
> Execution complete.
> - `src/components/HelloWorldButton.tsx` created.
> - `src/app/page.tsx` modified.
> - `docs/IA_HANDOFF.md` updated.
>
> Running validation...
> `npm run build`
>
> Build completed successfully. The task is done. To see the changes, please run `npm run dev` in your terminal.

---

Congratulations! You have successfully guided the Oracles through a full development cycle. You can now use this powerful and safe workflow for all your Farcaster MiniApp features.
