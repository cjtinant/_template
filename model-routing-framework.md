# Model Decision Tree & Workflow Routing Framework

This framework provides a triage-based approach for manual model routing within
**Positron**. By aligning tasks with specific model architectures, you can
maximize deep reasoning, maintain natural human alignment, and prevent rapid
token depletion.

---

## 🛠️ The Core Ecosystem

```text
               [ Incoming Task ]
                       │
         ┌─────────────┼─────────────┐
         ▼             ▼             ▼
  [ High-Horizon ]  [ Execution ] [ Human-Facing ]
  [  & Architecture ] [ & Automation] [   & Empathy   ]
         │             │             │
         ▼             ▼             ▼
    [ Fable 5 ]   [ Sonnet 5 ]  [ GPT-5.5 ]
         │                           │
         └─────────────┬─────────────┘
                       ▼
            ( Massive Datasets? )
                       │  Yes
                       ▼
               [ Gemini 3.1 Pro ]
```

---

## 🧭 Triage Matrix

### 1. Sonnet 5 • The Execution Engine

- **Role**: Default gateway and primary workhorse.
- **When to use**: Continuous code expansion, data parsing, standard system
  scripting, and tool/terminal automations.
- **Routing Signal**: Keep this as your **baseline active tab** in Positron.
  Route 60–70% of standard workflows here first.

### 2. Fable 5 • The Strategic Planner

- **Role**: Deep reasoning and structural architect.
- **When to use**: Root-cause analysis, complex logical debugging,
  macro-architecture design, and multi-file code mapping.
- **Routing Signal**: Escalate to Fable only when the **cost of failure is
  high** or when Sonnet hits a hard logical wall.

### 3. GPT-5.5 • The Front-End Diplomat

- **Role**: Human alignment, nuance, and emotional interpretation.
- **When to use**: Drafting high-stakes client communication, analyzing user
  experience/feedback, interpreting soft-skill problems, and interactive
  sessions.
- **Routing Signal**: Use whenever a task requires high **interpersonal
  negotiation** or empathetic tone calibration.

### 4. Gemini 3.1 Pro • The Context Vault

- **Role**: High-volume repository and document ingestion.
- **When to use**: Cross-referencing thousands of pages of logs, multi-hour
  media/session analysis, or deep archival codebase research.
- **Routing Signal**: Trigger Gemini **strictly by payload size**, reserving it
  for files or workspaces that exceed Sonnet's context ceiling to protect your
  token allotment. If you
