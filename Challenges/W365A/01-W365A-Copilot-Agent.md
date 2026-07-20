# Challenge 1: Build a Copilot Studio Agent with Computer Use on Windows 365 (Draft)

**[Home](../../README.md)**

> ⚠️ **Draft** — This challenge is a work in progress. Content, tasks, and success criteria may change before the Academy runs.

## Introduction

**Windows 365 for Agents** provides dedicated Cloud PCs that autonomous AI agents can sign in to and drive like a human user — clicking, typing, launching apps, and interacting with legacy line-of-business software that has no API.

In **Microsoft Copilot Studio**, you can build an agent that uses the **Computer Use (CUA)** capability. Instead of calling an API, the agent takes screenshots of a Windows desktop, reasons about what it sees, and performs mouse and keyboard actions on a Cloud PC to complete a task.

For this challenge, the **Windows 365 for Agents pool has already been prepared for you by the organizers**. Your job is to build the agent that uses it.

## Challenge

Create a Copilot Studio agent that uses **Computer Use** on the pre-provisioned Windows 365 for Agents Cloud PC to complete a simple task.

- Sign in to [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/).
- Create a **new agent**:
  - Name: **AGT-P[count]-CUA**
  - Description: Short description of what the agent will do.
- Add the **Computer Use** capability and target the **pre-provisioned Windows 365 for Agents pool**.
- Define a simple task for the agent to perform on the Cloud PC desktop, for example:
  - Open **Microsoft Edge**, navigate to `https://learn.microsoft.com`, search for **"Windows 365"** and read back the first result title.
  - **Or:** Open **Notepad**, type a short note, and save it to the desktop.
- **Test the agent** from the Copilot Studio test pane and watch it operate the Cloud PC.
- **Publish the agent** and try it from the Microsoft 365 Copilot chat.

> **Note:** The Windows 365 for Agents Cloud PC pool is **shared** with other attendees. Keep your tasks short and clean up any files you create.

## Success Criteria

- Your agent exists in Copilot Studio with the name **AGT-P[count]-CUA**.
- The Computer Use capability is enabled and connected to the prepared Windows 365 for Agents pool.
- You can trigger the agent and observe it performing actions on the Cloud PC (screenshots or live view in the test pane).
- The agent successfully completes the defined task and returns a result to the chat.
- The agent is **published** and reachable from Microsoft 365 Copilot.

## 💡 Pro Tipps 💡

> **1.** Start with **one very small task** (open one app, do one thing). Computer Use gets slow and error-prone fast if you give it a long chain of steps in a single prompt.

> **2.** Be explicit in your instructions: name the app, name the button, name the field. The agent reasons over what it sees, so unambiguous language beats clever prompts.

> **3.** Always add a **safety instruction** to your agent (e.g. *"Do not modify system settings, do not install software, do not delete files you did not create."*) — the agent has a real desktop session.

## Learning Resources

- [Microsoft Copilot Studio – overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- [Create and manage agents in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-create-edit-topics)
- [Computer Use in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/)
- [Windows 365 documentation](https://learn.microsoft.com/en-us/windows-365/)
