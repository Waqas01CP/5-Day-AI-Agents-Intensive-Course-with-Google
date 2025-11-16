# Google & Kaggle 5-Day AI Agents Intensive - Day 1 Projects

This repository contains my completed work, personal experiments, and key learnings from Day 1 of the "5-Day AI Agents Intensive" course offered by Google and Kaggle.

**Course Attribution:** This work is based on the official course materials provided by Google and Kaggle. The original codelabs can be found as part of the course content.

---

## 📚 Conceptual Learnings (from Whitepaper & Podcast)

This section provides a comprehensive checklist of the theoretical concepts covered in the Day 1 whitepaper and supporting materials.

*   **The Fundamental Paradigm Shift**
    *   From Passive, Predictive AI to Active, Autonomous Agents.
    *   The developer's role evolving from "Bricklayer" to "Director."

*   **Core Agent Architecture**
    *   **Model (The "Brain"):** The reasoning engine and its primary role in context window curation.
    *   **Tools (The "Hands"):** Mechanisms for action and information retrieval (RAG, NL2SQL, Code Execution, HITL).
    *   **Orchestration Layer (The "Nervous System"):** The engine running the "Think, Act, Observe" loop, managing planning, memory, and state.
    *   **Deployment (The "Body and Legs"):** The infrastructure needed to run agents in production.

*   **Agent Operations & Behavior**
    *   **The 5-Step Agentic Problem-Solving Process:** Get Mission -> Scan Scene -> Think -> Act -> Observe & Iterate.
    *   **The ReAct Framework:** The blending of Reasoning and Acting.
    *   **Context Engineering:** The art of curating the perfect context to guide the LM.

*   **A Taxonomy of Agentic Systems**
    *   Level 0: Core Reasoning System
    *   Level 1: Connected Problem-Solver
    *   Level 2: Strategic Problem-Solver (and Context Engineering)
    *   Level 3: Collaborative Multi-Agent System
    *   Level 4: Self-Evolving System (and Meta-Reasoning)

*   **Multi-Agent Design Patterns**
    *   **Coordinator Pattern:** An LLM-based orchestrator dynamically decides which specialist agent to call.
    *   **Sequential Pattern:** A deterministic pipeline for tasks where a strict order matters.
    *   **Parallel Pattern:** For running independent tasks concurrently to improve speed.
    *   **Loop Pattern:** An iterative refinement cycle for tasks requiring quality control and feedback.

*   **Production Readiness (Agent Ops)**
    *   The shift from pass/fail testing to quality evaluation using an "LM as Judge."
    *   The importance of KPIs and Metrics-Driven Development.
    *   Debugging complex agent behavior using OpenTelemetry Traces.
    *   Creating a "Closed Loop" system by incorporating human feedback into evaluation datasets.

*   **Security, Governance, and Interoperability**
    *   **The Trust Trade-Off:** Balancing an agent's utility with security risks.
    *   **Defense-in-Depth:** Combining deterministic guardrails with AI-based guard models.
    *   **Agent Identity:** The concept of an agent as a new class of "principal" requiring a verifiable identity (e.g., via SPIFFE).
    *   **Agent Governance:** Using a central control plane to manage "Agent Sprawl."
    *   **Interoperability:** Patterns for Agent-to-Human (Live Mode) and Agent-to-Agent (A2A Protocol) communication.

*   **Agent Evolution and Learning**
    *   Understanding agent "aging" and the need for adaptation in dynamic environments.
    *   The mechanisms for learning from runtime experience (HITL feedback) and external signals.
    *   The concept of an "Agent Gym" for safe, offline optimization and testing.

*   **Agent Commerce**
    *   Protocols for enabling secure, auditable agentic transactions (Agent Payments Protocol - AP2).
    *   Mechanisms for frictionless, machine-to-machine micropayments (x402).

*   **Advanced Agent Examples**
    *   Analysis of complex, collaborative multi-agent systems (e.g., Google Co-Scientist).
    *   Understanding evolutionary algorithms in agents for optimization (e.g., the AlphaEvolve case study).

---

## 💡 Key Insights & Deeper Dives

This section highlights personal insights and analyses that emerged from a deeper investigation of the course materials and hands-on experimentation.

*   **AlphaEvolve's Mechanism is Evolutionary, Not Just Sequential:** A deeper analysis of the AlphaEvolve agent revealed that its power lies in a population-based evolutionary algorithm, not a simple deterministic loop. Within each iterative cycle, it employs a "branching and pruning" strategy: generating a wide population of code variations, scoring them against a fitness function, and promoting only the most successful candidates. This insight clarifies that its ability to find novel solutions comes from parallel exploration, not linear progression.

*   **Synthesizing Theory with Expert Practice:** I synthesized key insights from the Day 1 Livestream to bridge the gap between formal documentation and the practical wisdom of industry experts. Key takeaways included the architectural advice to "start simple and layer complexity," the strategic principle that the most effective agents are often the most proactive and least interactive, and the introduction of advanced patterns like the "Agent Broker" for dynamic team management.

*   **The Gap Between Instruction and Capability:** A critical takeaway from my "Roadmap Generator" project was observing an agent's limitations in practice. Despite instructing the `ExistingSolutionsResearcher` to "provide a score," it was unable to fulfill this quantitative task without a specific tool. This highlighted the crucial role of the agent architect: success requires not just providing clear instructions, but also equipping the agent with the precise capabilities (e.g., a `FunctionTool` for calculation) needed to execute those instructions faithfully.

---

## 📂 Project 1: `day-1a-from-prompt-to-action.ipynb`

This project covers the basics of creating a single, tool-enabled AI agent.

### Key Activities:
*   Built a simple agent powered by the Gemini 2.5 Flash Lite model.
*   Gave the agent its "Hands" by equipping it with the `google_search` tool to access real-time information.
*   Learned to run the agent and interpret its output using the ADK's `InMemoryRunner`.

### ✨ My Personal Experiment: The Task-Oriented Expert Agent

To go beyond the lab, I designed a `refined_root_agent` with an enhanced persona.

*   **Goal:** To create a more sophisticated agent that could act as a domain expert on any given topic.
*   **Implementation:** I wrote a more detailed system prompt (`instruction`) that directed the agent to adopt an expert persona, synthesize a comprehensive plan, and provide a forward-looking forecast.
*   **Outcome:** The agent successfully generated a detailed and high-quality roadmap for becoming an expert in "Context Engineering and AI Agents," demonstrating the powerful impact of a well-crafted agent instruction.

[Link to the Experiment: Refined Root Agent](https://nbviewer.org/github/Waqas01CP/5-Day-AI-Agents-Intensive-Course-with-Google/blob/main/Day-1/day-1a-from-prompt-to-action.ipynb#2.6-Changing-the-description-and-instruction-of-the-Agent)

---

## 📂 Project 2: `day-1b-agent-architectures.ipynb`

This project scaled up from a single agent to a collaborative multi-agent system, demonstrating how to orchestrate a team of specialists.

### Key Activities:
*   Learned the core multi-agent patterns in ADK: `SequentialAgent`, `ParallelAgent`, and `LoopAgent`.
*   Understood how to pass information ("state") between agents using `output_key` and prompt placeholders.

### ✨ My Capstone Project: The Final Year Project Roadmap Generator

[Link to the Project Section of Implementation of Level 3 Agentic System](https://nbviewer.org/github/Waqas01CP/5-Day-AI-Agents-Intensive-Course-with-Google/blob/main/Day-1/day-1b-agent-architectures.ipynb#Section-6:-Personal-Implementation)

Instead of a small experiment, I designed and built a complete, end-to-end multi-agent system to solve a complex, real-world problem.

*   **Goal:** To create a system that takes a student's high-level project idea and generates a detailed, refined, and practical Final Year Project (FYP) roadmap.
*   **Architecture:** I designed a master pipeline using a `SequentialAgent` that combined all three workflow patterns:
    1.  **Phase 1 (Parallel):** A `ParallelAgent` managed a team of three specialist researchers (`TechBackgroundResearcher`, `ExistingSolutionsResearcher`, `ToolsAndTechResearcher`) that gathered information concurrently.
    2.  **Phase 2 (Sequential Step):** A `RoadmapDraftingAgent` synthesized the research from all three specialists into a single, cohesive first draft.
    3.  **Phase 3 (Loop):** A `LoopAgent` managed a refinement cycle where a `CriticAgent` provided feedback on the draft and a `RefinerAgent` incorporated the feedback, iteratively improving the roadmap until it was "APPROVED."
*   **Outcome:** The system successfully produced a high-quality, multi-page project roadmap for an "AI Career Counselor" application. The project demonstrated a strong grasp of complex agent orchestration and the ability to produce a valuable, tangible output.
