# Challenge 1: Build a Copilot Studio Agent with Computer Use on Windows 365 (Draft)

**[Home](../../README.md)**

> ⚠️ **Draft** — This challenge is a work in progress. Content, tasks, and success criteria may change before the Academy runs.

## Introduction

**Windows 365 for Agents** powers Cloud PC pools that agents can use to interact with Windows applications and websites through mouse and keyboard actions, including software without an API.

In **Microsoft Copilot Studio**, the **Computer use** tool interprets screenshots and performs actions on a Windows desktop to complete a task. In this challenge, you will build an agent, give it one small task, and observe its execution.

For this challenge, the **Windows 365 for Agents pool has already been prepared for you by the organizers**. Your job is to build the agent that uses it.

## Challenge

Use the **Power Platform environment** and **Cloud PC pool** identified by the organizers. Replace `[n]` with your team number.

### 1. Create your agent

- Sign in to [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/).
- Select the organizer-provided environment and create an agent named **`AGT-P[n]-CUA`**.
- Add a short description of the task the agent will perform.

### 2. Configure Computer use

- Add the **Computer use** tool and configure its name, description, and task instructions.
- Select the **prepared Cloud PC pool** as the target machine. Use the connection and authentication method approved by the organizers; do not create another pool.
- Define **one** small task, for example:
  - Open **Microsoft Edge**, navigate to `https://learn.microsoft.com`, search for **Windows 365**, and return the first result's title and URL.
  - **Or:** Open **Notepad**, type a short lab note, and save it as `AGT-P[n]-CUA.txt` on the desktop.
- Add a safety instruction: **Do not modify system settings, install software, access other attendees' files, or delete files you did not create. Stop and report unexpected prompts or errors.**
- Where available, configure the tool's **Access control** settings to allow only the websites and applications required for your task. Do not rely on instructions alone to restrict access.

### 3. Test and refine

- Save the tool and select **Test** to review its action log and machine preview.
- Verify the actual result: open the returned page or check the saved note, rather than relying only on the agent's completion message.
- If the task fails, review the actions, refine the instructions, and test again. Use **Stop testing** to stop unexpected actions.
- Trigger the task from the agent's **test chat** and confirm that it invokes Computer use and returns the result.

### 4. Publish and try the agent

- Publish the agent and make it available in **Microsoft 365 Copilot**, using the channel and sharing instructions provided by the organizers.
- Start a chat with the published agent and repeat your task.

> **Note:** The Windows 365 for Agents Cloud PC pool is **shared** with other attendees. Keep your tasks short and clean up any files you create.

## Success Criteria

- **`AGT-P[n]-CUA`** uses the prepared Cloud PC pool through the **Computer use** tool.
- The action log and machine preview show the task running, and the actual output matches the instructions.
- The agent returns the task result in chat without modifying unrelated files or settings.
- The published agent is accessible and completes the task from **Microsoft 365 Copilot**.

## 💡 Pro Tips 💡

> **1.** Start with **one very small task** (open one app, do one thing). Computer Use gets slow and error-prone fast if you give it a long chain of steps in a single prompt.

> **2.** Be explicit in your instructions: name the app, name the button, name the field. The agent reasons over what it sees, so unambiguous language beats clever prompts.

> **3.** Use only **non-sensitive lab data**. Never put passwords or secrets in agent instructions or chat.

## Organizer Validation Before Release

- Confirm the environment, pool name, attendee permissions, approved connection method, and available Computer use model.
- Validate tenant policies, regional availability, and capacity or billing requirements for the lab.
- Test both sample tasks and the Microsoft 365 Copilot publishing/sharing workflow with an attendee account.

## Learning Resources

- [Microsoft Copilot Studio – overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- [Create and deploy an agent](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-get-started)
- [Automate web and desktop apps with Computer use](https://learn.microsoft.com/en-us/microsoft-copilot-studio/computer-use)
- [Use Cloud PC pools for Computer use runs (preview)](https://learn.microsoft.com/en-us/microsoft-copilot-studio/use-cloud-pc-pool)
