# Advanced Usage: Building a Transaction Frame

Now that you're familiar with the basic workflow, let's tackle a more advanced, real-world scenario: creating a **Transaction Frame** that allows users to mint an NFT directly from the Farcaster feed.

This guide will showcase how to leverage the Oracles' deep knowledge of the `frames.js` library and its transaction lifecycle.

## Goal: Create an NFT Minting MiniApp

Our goal is to build a simple MiniApp that displays an NFT and has a "Mint" button. When a user clicks "Mint", it will prompt them to sign a transaction with their connected wallet.

### Step 1: Architecting the Transaction Logic (with Oxalá)

A transaction frame requires backend logic to prepare the transaction data for the Farcaster client. This is a perfect task for Oxalá, our architectural consultant.

**Your Prompt to Oxalá:**
> `@Oxala, I need to create a Transaction Frame for minting an NFT on the Base Sepolia testnet. Can you provide the backend code for a \`frames.js\` route that prepares a simple mint transaction? I have a basic ERC-721 smart contract already deployed.`

**Oxalá's Expected Response:**
> An excellent choice. Transaction Frames are a powerful feature. Based on the `frames.js` documentation, the correct approach is to create a route that returns a `FrameTransactionResponse`.
>
> Here is a well-structured example for your API route. You will need to replace the placeholder values with your actual contract details.
>
> ```typescript
> // app/frames/tx/route.ts
> import { Button } from "frames.js/next";
> import { frames } from "../frames";
> import { transaction } from "frames.js/core";
> import { abi } from "./abi"; // Assuming your contract ABI is here
> import { parseEther } from "viem";
>
> const handleRequest = frames(async (ctx) => {
>   if (ctx.message?.transactionId) {
>     return {
>       image: (
>         <div tw="flex flex-col">
>           <div tw="flex">Transaction submitted!</div>
>           <div tw="flex">TX ID: {ctx.message.transactionId.slice(0, 10)}...</div>
>         </div>
>       ),
>       buttons: [
>         <Button
>           action="link"
>           target={`https://sepolia.basescan.org/tx/${ctx.message.transactionId}`}
>         >
>           View on Etherscan
>         </Button>,
>       ],
>     };
>   }
>
>   return {
>     image: <div tw="flex">Click Mint to get your NFT!</div>,
>     buttons: [
>       <Button
>         action="tx"
>         target="/frames/txdata" // This is the endpoint that prepares the transaction
>         post_url="/frames/tx" // URL to return to after the transaction is sent
>       >
>         Mint
>       </Button>,
>     ],
>   };
> });
>
> export const GET = handleRequest;
> export const POST = handleRequest;
> ```
>
> Notice the `target` property on the button points to a separate route, `/frames/txdata`. This is the best practice for security and clarity. That route will be responsible for preparing and returning the transaction data. Does this architectural approach make sense for your project?

### Step 2: Handoff to Ogum

The plan is solid. Now, let's hand it over to the engineer.

**Your Prompt to Oxalá:**
> `@Oxala, this architecture is perfect. Please create a handoff for Ogum to implement this NFT minting frame, including the main frame route and the separate \`txdata\` route.`

**Oxalá's Expected Response:**
> Understood. I will add the task to `docs/IA_HANDOFF.md` for Ogum to implement the two required API routes (`/frames/tx` and `/frames/txdata`) for the NFT minting MiniApp.
>
> The task has been logged. You may now activate the Ogum agent.

### Step 3: Execution with Ogum

Activate Ogum and give him the green light.

**Your Prompt to Ogum:**
> `@Ogun, please begin the next task from the handoff file.`

**Ogum's Expected Response (after Investigation & Approval):**
> Investigation complete. I have identified the `app/frames` directory.
>
> **Execution Plan:**
> 1.  **Create File:** `app/frames/tx/route.ts` with the main frame logic.
> 2.  **Create File:** `app/frames/tx/abi.ts` with a placeholder for the contract ABI.
> 3.  **Create File:** `app/frames/txdata/route.ts` with the transaction data preparation logic.
> 4.  **Update Handoff:** Mark the task as "Completed" in `docs/IA_HANDOFF.md`.
>
> **Validation Plan:**
> 1.  After implementation, I will run `npm run build` to ensure the project compiles without type errors.
> 2.  I will also remind you to test the transaction flow in the `/debug` local playground.
>
> **Do you approve this execution plan?**

### Step 4: Validation in the Local Playground

Once Ogum has finished, he will remind you to test. This is where the local debug environment shines.

1.  Run your project locally with `npm run dev`.
2.  Open `http://localhost:3000/debug` in your browser.
3.  Navigate to your new frame's URL (e.g., `/frames/tx`).
4.  In the debug panel, you can:
    * Click the "Mint" button.
    * Inspect the `Frame Action` payload that is sent to `/frames/txdata`.
    * See the `FrameTransactionResponse` that your backend returns, all without needing a real wallet or `ngrok`.

This advanced workflow demonstrates how the Oracles can handle complex, protocol-specific tasks by combining Oxalá's architectural knowledge with Ogum's safe and methodical execution, allowing you to build powerful MiniApps faster and with greater confidence.
