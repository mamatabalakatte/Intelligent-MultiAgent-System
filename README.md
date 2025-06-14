
Intelligent Multi-Agent System (IMAS)

A modular AI system built using Google ADK that dynamically plans and routes user goals through multiple intelligent agents. The system uses public APIs like SpaceX and OpenWeatherMap to enrich each agent's output—collaboratively achieving the final goal.

---

 Project Overview

This system simulates real-world intelligent decision-making. Given a user goal like:  
“Will the next SpaceX launch be delayed?”
The system will:
1. Use a Planner Agent to break the goal into subtasks
2. Route tasks to individual Enrichment Agents:
   - `launchAgent`: fetches next launch
   - `weatherAgent`: fetches weather at launch site
   - `delayAgent`: predicts delay based on weather
3. Iterate if any result is missing or unclear
4. Return a final decision (with reasoning)

---
  Agent Roles

| Agent         | Description                                     |
|---------------|-------------------------------------------------|
| `planner.ts`  | Parses user goal, defines execution sequence    |
| `launchAgent` | Fetches next launch data via SpaceX API        |
| `weatherAgent`| Pulls weather data for the launch location      |
| `delayAgent`  | Analyzes if launch might be delayed             |

---

🗺️ System Flow

```mermaid
graph TD
  A[User Goal] --> B[Planner Agent]
  B --> C[Launch Agent]
  C --> D[Weather Agent]
  D --> E[Delay Analyzer]
  E --> F[Final Output]
