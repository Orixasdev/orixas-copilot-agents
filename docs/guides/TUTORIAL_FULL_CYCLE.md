# 🚀 Tutorial: From Idea to Frame with the Orixás

> ### _A complete guide to building a Farcaster MiniApp using the divine workflow._
>
> `Est. Time: 25 minutes` `Difficulty: Intermediate`

---

## Introduction

Welcome, developer. This tutorial will guide you through the entire lifecycle of creating a simple Farcaster MiniApp—a community poll frame—using the unique, powerful workflow of the **Orixás Copilot Agents**.

You will learn how to:
1.  **Consult with Oxalá 🕊️** to transform a vague idea into a robust technical plan.
2.  **Command Ogum ⚔️** to execute that plan with precision, writing the necessary code.

By the end, you will have a functional Farcaster frame and a deep understanding of how our agents work in harmony.

### Prerequisites

Before you begin, please ensure you have:
* Node.js v18 or later installed.
* A basic understanding of Farcaster, Frames, and React.
* The Orixás Copilot Agents CLI installed and configured.

---

## Chapter 1: The Divine Plan (Consulting Oxalá 🕊️)

Every great creation begins with a clear vision. Our first step is to consult the Architect Agent, Oxalá, to help us design our poll frame. We will simulate the conversation to demonstrate his capabilities.

#### **Step 1: The Initial Spark**

We start with a simple, high-level prompt.

> **Your Prompt:**
> "Oxalá, I want to build a Farcaster frame that lets users vote in a poll. The topic is 'Which agent should be developed next: Xangô or Iansã?'"

#### **Step 2: The Clarifying Questions**

Oxalá doesn't just give answers; he seeks clarity. He might respond with questions to refine the plan.

> **Oxalá's Response (Simulated):**
> "An excellent initiative. To create a proper plan, please consider the following:
> 1.  How will votes be stored? On-chain, or off-chain in a simple database like Vercel KV?
> 2.  What should the frame display *after* a user has voted? Should it show the current results?
> 3.  What is the initial state of the frame before any interaction?"

#### **Step 3: The Final Specification**

After providing answers (let's assume we chose off-chain storage for simplicity), Oxalá will generate the final technical specification. This is the sacred text we will hand to Ogum.

> **Your Prompt:**
> "Let's use Vercel KV for storage. After voting, the frame should update to show the current vote percentages. The initial frame should present the question and the two voting options."

> **Oxalá's Final Plan (Simulated):**
> ```json
> {
>   "projectName": "orixas-poll-frame",
>   "coreFeatures": [
>     "Display an initial frame with a question and two buttons as voting options.",
>     "On button press, record the vote in a Vercel KV store.",
>     "Display a results frame showing the percentage of votes for each option."
>   ],
>   "dataModel": {
>     "storage": "Vercel KV",
>     "keys": {
>       "xango_votes": "A number representing total votes for Xangô.",
>       "iansa_votes": "A number representing total votes for Iansã."
>     }
>   },
>   "frameLogic": {
>     "initial_frame": "/api/poll (GET)",
>     "voting_action": "/api/poll (POST)"
>   },
>   "fileStructure": [
>     "app/api/poll/[[...routes]]/route.ts",
>     "app/api/poll/image.tsx"
>   ]
> }
> ```

With this divine plan in hand, we are ready to enter the forge.

---

## Chapter 2: The Forge of Creation (Commanding Ogum ⚔️)

Now, we bring Oxalá's specification to Ogum, the Executor Agent. Ogum's purpose is to turn plans into flawless code.

#### **Step 1: Project Scaffolding**

First, we command Ogum to set up the project structure.

> **Your Prompt:**
> "Ogum, using the specification from Oxalá, scaffold a new Next.js project with frames.js for the 'orixas-poll-frame'."

Ogum will execute this, creating the boilerplate and installing the necessary dependencies.

#### **Step 2: Implementing the Core Logic**

Next, we ask him to write the main application logic based on the file structure defined by Oxalá.

> **Your Prompt:**
> "Ogum, create the file `app/api/poll/[[...routes]]/route.ts` and implement the frame logic from the plan. Use Vercel KV for storage."

Ogum will generate the following code, applying his two-step safety protocol (investigate, then execute upon approval).

> **Generated Code (`route.ts`):**
> ```typescript
> import { Button } from "frames.js/next";
> import { frames } from "../frames";
> import { kv } from "@vercel/kv";
> 
> const handler = frames(async (ctx) => {
>   // Retrieve current votes, defaulting to 0 if null
>   const xangoVotes = (await kv.get<number>("xango_votes")) ?? 0;
>   const iansaVotes = (await kv.get<number>("iansa_votes")) ?? 0;
>   const totalVotes = xangoVotes + iansaVotes;
> 
>   // Handle the voting action from a button press
>   if (ctx.message?.buttonIndex) {
>     if (ctx.message.buttonIndex === 1) {
>       await kv.incr("xango_votes");
>     } else if (ctx.message.buttonIndex === 2) {
>       await kv.incr("iansa_votes");
>     }
>     // After voting, show the results frame
>     return {
>       image: `${process.env.NEXT_PUBLIC_HOST}/api/poll/image?total=${totalVotes + 1}`,
>       buttons: [
>         <Button action="post" target="/">View on Orixas.dev</Button>,
>       ],
>     };
>   }
> 
>   // This is the initial frame state
>   return {
>     image: `${process.env.NEXT_PUBLIC_HOST}/api/poll/image?total=${totalVotes}`,
>     buttons: [
>       <Button action="post" target="/api/poll">Vote for Xangô</Button>,
>       <Button action="post" target="/api/poll">Vote for Iansã</Button>,
>     ],
>   };
> });
> 
> export const GET = handler;
> export const POST = handler;
> ```

#### **Step 3: Generating the Image**

Finally, we need the visual component of our frame.

> **Your Prompt:**
> "Ogum, create the file `app/api/poll/image.tsx` to render the poll results. It should show the percentages dynamically."

> **Generated Code (`image.tsx`):**
> ```tsx
> import { kv } from "@vercel/kv";
> 
> export default async function Image({ searchParams }: { searchParams: { total: string } }) {
>   const totalVotes = parseInt(searchParams.total ?? "0");
>   
>   const xangoVotes = (await kv.get<number>("xango_votes")) ?? 0;
>   const iansaVotes = (await kv.get<number>("iansa_votes")) ?? 0;
> 
>   const xangoPercentage = totalVotes > 0 ? ((xangoVotes / totalVotes) * 100).toFixed(0) : 50;
>   const iansaPercentage = totalVotes > 0 ? ((iansaVotes / totalVotes) * 100).toFixed(0) : 50;
> 
>   return (
>     <div style={{ display: 'flex', width: '100%', height: '100%', backgroundColor: 'black', color: 'white', alignItems: 'center', justifyContent: 'center', flexDirection: 'column' }}>
>       <h2>Next Orixá? (Total Votes: {totalVotes})</h2>
>       <div style={{ display: 'flex', width: '80%', justifyContent: 'space-around', fontSize: '24px' }}>
>         <span>⚖️ Xangô: {xangoPercentage}%</span>
>         <span>🌪️ Iansã: {iansaPercentage}%</span>
>       </div>
>     </div>
>   );
> }
> ```

---

## Chapter 3: The Path Forward

Congratulations! You have successfully created a Farcaster poll frame by channeling the distinct powers of Oxalá and Ogum. You've experienced the divine workflow: from pure strategy to flawless execution.

**What's next?**

* **Testing:** You could now ask Ogum to write unit tests for your logic.
* **Deployment:** Once **Xangô ⚖️** is released, the next step would be simple: `"Xangô, deploy this project to Vercel."`

You are now ready to build your own MiniApps with the Orixás. May your creations be strong and your paths open. Axé!
