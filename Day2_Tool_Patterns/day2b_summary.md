Day 2B — Tool Patterns & Best Practices (Agent Summary)

In Day 2B, I built two powerful real-world agent patterns:

🌐 1. MCP-Powered Agent (External Tools)

I built an agent that connects to an external MCP server (Model Context Protocol) using:

McpToolset(...)


This allows the agent to use community-built tools without writing any API code.

What the agent does:

Launches an external MCP server

Calls tools like getTinyImage

Retrieves base64 images

Displays real images inside the notebook

Why this matters:

MCP lets agents interact with:

GitHub

Slack

Google Maps

Databases

Kaggle

ANY MCP-compatible service

All without writing custom integrations.

This is real enterprise-grade extensibility.

⏳ 2. Shipping Coordinator Agent (Long-Running Operations)

I built a shipping agent that can pause, ask for approval, wait, and resume — the exact pattern used in real financial, compliance, and enterprise workflows.

The agent’s behavior:
✔ Small order (≤5 containers)

Auto-approved instantly.

✔ Large order (>5 containers)

Tool pauses workflow

Sends a special event: adk_request_confirmation

Agent waits for human decision

Workflow resumes using the SAME invocation_id

Agent finishes the process (approve or reject)

Key technical features:

ToolContext.request_confirmation()

ResumabilityConfig(is_resumable=True)

App wrapper

SessionService

Event handling

Resume via invocation_id

This allows multi-step workflows that last minutes, hours, or days.

🚀 TL;DR (Ultra Short Version)

Day 2B taught me how to build agents that can:

✔ Connect to external systems using MCP

(GitHub, Slack, Maps, Kaggle, etc.)

✔ Pause and resume workflows with human approval

(Critical for real-world tasks like payments, shipping, compliance)

✔ Maintain state across multi-step processes

(Using App, Runner, SessionService, and invocation IDs)

These are the exact patterns used in production AI agent systems.
