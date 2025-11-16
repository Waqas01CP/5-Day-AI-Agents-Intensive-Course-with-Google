# Google & Kaggle 5-Day AI Agents Intensive - Day 1 Projects

This repository contains my completed work, personal experiments, and key learnings from Day 1 of the "5-Day AI Agents Intensive" course offered by Google and Kaggle.

**Course Attribution:** This work is based on the official course materials provided by Google and Kaggle. The original codelabs can be found as part of the course content.

---

## 🚀 Day 1 Learning Objectives

Day 1 focused on the foundational principles of AI Agent architecture and development. The key concepts covered and applied in these projects include:

*   **The Core Anatomy of an Agent:** Understanding the roles of the Model (Brain), Tools (Hands), and Orchestration Layer (Nervous System).
*   **The "Think, Act, Observe" Loop:** The fundamental operational cycle of an agent.
*   **The Taxonomy of Agentic Systems:** The different levels of agent capability, from simple tool-users to collaborative multi-agent systems.
*   **Agent Development Kit (ADK):** Hands-on experience building agents using Google's open-source framework.
*   **Multi-Agent Workflow Patterns:** Implementing and combining Sequential, Parallel, and Loop agents to solve complex problems.

---

## 📂 Project 1: `day-1a-from-prompt-to-action.ipynb`

This project covers the basics of creating a single, tool-enabled AI agent.

### Key Activities:
*   Built a simple agent powered by the Gemini 1.5 Flash model.
*   Gave the agent its "Hands" by equipping it with the `google_search` tool to access real-time information.
*   Learned to run the agent and interpret its output using the ADK's `InMemoryRunner`.

### ✨ My Personal Experiment: The Task-Oriented Expert Agent

To go beyond the lab, I designed a `refined_root_agent` with an enhanced persona.

*   **Goal:** To create a more sophisticated agent that could act as a domain expert on any given topic.
*   **Implementation:** I wrote a more detailed system prompt (`instruction`) that directed the agent to adopt an expert persona, synthesize a comprehensive plan, and provide a forward-looking forecast.
*   **Outcome:** The agent successfully generated a detailed and high-quality roadmap for becoming an expert in "Context Engineering and AI Agents," demonstrating the powerful impact of a well-crafted agent instruction.

> [Link to the Experiment: Refined Root Agent](https://nbviewer.org/github/Waqas01CP/5-Day-AI-Agents-Intensive-Course-with-Google/blob/main/Day-1/day-1a-from-prompt-to-action.ipynb#2.6-Changing-the-description-and-instruction-of-the-Agent)

---

## 📂 Project 2: `day-1b-agent-architectures.ipynb`

This project scaled up from a single agent to a collaborative multi-agent system, demonstrating how to orchestrate a team of specialists.

### Key Activities:
*   Learned the core multi-agent patterns in ADK: `SequentialAgent`, `ParallelAgent`, and `LoopAgent`.
*   Understood how to pass information ("state") between agents using `output_key` and prompt placeholders.

### ✨ My Capstone Project: The Final Year Project Roadmap Generator

> [Link to the Project Section](day-1b-agent-architectures.ipynb#Section-6:-Personal-Implementation)

Instead of a small experiment, I designed and built a complete, end-to-end multi-agent system to solve a complex, real-world problem.

*   **Goal:** To create a system that takes a student's high-level project idea and generates a detailed, refined, and practical Final Year Project (FYP) roadmap.
*   **Architecture:** I designed a master pipeline using a `SequentialAgent` that combined all three workflow patterns:
    1.  **Phase 1 (Parallel):** A `ParallelAgent` managed a team of three specialist researchers (`TechBackgroundResearcher`, `ExistingSolutionsResearcher`, `ToolsAndTechResearcher`) that gathered information concurrently.
    2.  **Phase 2 (Sequential Step):** A `RoadmapDraftingAgent` synthesized the research from all three specialists into a single, cohesive first draft.
    3.  **Phase 3 (Loop):** A `LoopAgent` managed a refinement cycle where a `CriticAgent` provided feedback on the draft and a `RefinerAgent` incorporated the feedback, iteratively improving the roadmap until it was "APPROVED."
*   **Outcome:** The system successfully produced a high-quality, multi-page project roadmap for an "AI Career Counselor" application. The project demonstrated a strong grasp of complex agent orchestration and the ability to produce a valuable, tangible output.
