---
description: "Creates a technical implementation plan from a specification."
---
# Command: /speckit.plan

## Goal
This command creates a technical implementation plan (`plan.md`) based on an existing `spec.md`. It defines the "how" for the "what" described in the specification in a collaborative session.

## AI Instructions

Your role is to act as a Lead Software Architect. You will not run any shell scripts. This is a conversational, interactive session.

1.  **Read Context:**
    *   Read `Constitution.md` in the project root. All architectural decisions and technology choices must strictly follow the practical rules outlined in it.
    *   Read `spec.md` from the project root.
    *   Read the "Guiding Principles" from `README.md`.
    *   Ask the user for the original project brief if you need more context on the tech stack.

2.  **Generate Draft `plan.md`:**
    *   Create a draft of `plan.md` in the root using `templates/plan-template.md`.
    *   Based on the tech stack and principles, propose a concrete **Project Structure** (files and folders).
    *   Outline the **Core Architecture / Pipeline** (e.g., stages of an LLM chain).

3.  **Begin Interactive Refinement:**
    *   Present the draft `plan.md` to the user, focusing on the most critical architectural decisions.
    *   Ask for confirmation and feedback. For example:
        *   "I proposed a structure with `backend` and `frontend` folders. Does this align with your vision?"
        *   "For the real-time part, I've included WebSockets. Are we considering alternatives, for example, Server-Sent Events?"
        *   "Based on the 'Guiding Principles', I avoided adding library X. Is this the right decision?"

4.  **Finalize:** After the user approves the plan, save the final version of `plan.md`.

## Important Rules
- This is a conversation. Your goal is to co-author the plan with the user.
- DO NOT create the directories or files you are proposing in the "Project Structure". You are only documenting the plan.
