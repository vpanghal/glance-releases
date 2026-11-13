# Glance

**Your models. Your knowledge. Agents that get work done.**

Build AI agents that write code, answer questions, research a topic, or automate
recurring work. Glance brings your models, data sources, tools, evaluations, and
agent activity into one desktop workspace.

Start with one agent and a task. Add knowledge, connect tools, and build a team
of specialist agents as your needs grow.

**[Download Glance for Mac](https://github.com/vpanghal/glance-releases/releases)**
· [What's new in 0.6.0](https://github.com/vpanghal/glance-releases/releases/tag/v0.6.0)
· [Get started](#try-your-first-agent)

## Watch the Glance demo

Start in a local workspace, then connect a provider, register a model, publish
a coding agent, and ask it to explain a repository.

https://github.com/user-attachments/assets/8c8f35bf-7118-4678-a9f0-d4c7a1730bdb

### Watch the browser agent demo

https://github.com/user-attachments/assets/dbf34f25-ab62-43a9-aa6a-3b34beb6bd31

## Agents

Create the agent you need by combining a model, instructions, skills, and access
to the right sources and tools. Use the same workspace for different kinds of
agents:

| Build an agent for | Put it to work |
| --- | --- |
| Coding | Explore a repository, edit files, run commands and tests, and review changes in the workspace. |
| Q&A | Answer questions across connected documents, with source citations you can open beside the conversation. |
| Research | Search connected knowledge and the web, compare findings, and draft a report. |
| Task automation | Use connected tools and APIs, work on remote hosts, and schedule recurring tasks. |

Give each agent reusable skills and instructions, select its capabilities, and
set guardrails and budgets. Delegate work to specialist subagents and follow
their tasks and progress together. Chat, files, terminals, diffs, and previews
keep the work close to the conversation.

### Agent harness: choose your model

Glance's agent harness brings model calls, tools, and task execution together.
Choose the model that fits each agent and manage providers in one place:

- **OpenAI, Anthropic Claude, Google Gemini, and Azure OpenAI.**
- **More provider choices:** Mistral, xAI, Groq, Cerebras, MiniMax, OpenRouter,
  Vercel AI Gateway, and Kimi For Coding.
- **Your own models:** connect compatible endpoints served by Ollama, vLLM,
  LM Studio, LiteLLM, or another OpenAI-compatible service.

Use provider API keys or supported account connections, including ChatGPT/Codex
OAuth. Configure model profiles, reasoning options, and usage limits for the
task. Available capabilities depend on the selected model and endpoint.

## Source Connectors

**Give your agents the context to do useful work.** Connect the documents,
repositories, and data you already use, then choose what each agent can access.

- **Files and documents:** direct uploads, Google Drive, Microsoft OneDrive,
  and SharePoint.
- **Engineering knowledge:** GitHub, Jira Cloud and Data Center, and Confluence
  Cloud and Data Center.
- **Cloud storage:** Amazon S3 and Azure Blob Storage.
- **Structured data:** read-only analysis with DuckDB and SQLite connectors.
- **Live research:** web search through Exa or Parallel, plus HTTP access with
  domain controls.

Search across connected knowledge, inspect source documents, and follow sync
and indexing progress from Glance.

## Eval

**Measure quality as you improve your agents.** Turn representative tasks into
repeatable evaluations and compare results when you change an agent or model.

- Create or import evaluation datasets, define criteria, and publish dataset
  versions for repeatable experiments.
- Score results with checks such as exact matching and regular expressions,
  or use an LLM judge for criteria that need interpretation.
- Compare runs against a baseline and inspect individual results to understand
  where performance changed.
- Evaluate sampled production runs and turn selected examples into offline
  test cases.

## Connect Agent

**Put your agents where the work happens.** Connect conversations, tools, and
execution environments around each agent.

- **Slack:** bring agents into channels and direct messages, using Socket Mode
  or webhooks.
- **MCP tools:** connect Model Context Protocol servers, select the tools an
  agent may use, and configure approval requirements.
- **Local and remote workspaces:** run commands on your computer or connect
  Remote Hosts through SSH and Kubernetes setup flows.
- **Schedules:** run recurring tasks so agents can help with ongoing work.

## Monitor Agent

**See what happened, understand the result, and know what needs attention.**

- Follow agent activity, delegated tasks, and conversations in one workspace.
- Inspect a run's trajectory, including model interactions, tool calls,
  results, and errors.
- Track evaluation pass rates, run and tool success, duration, and token
  usage. Break results down by agent, version, model, tool, or person.
- Export traces to Langfuse, LangSmith, Braintrust, or a compatible
  OpenTelemetry endpoint.

## Try your first agent

1. **Install Glance** using the steps below, then add a model under
   **Agents → Models**.
2. **Give it a purpose.** Create an agent, choose the model, and write a short
   instruction describing what you want it to do.
3. **Add context and tools.** Connect a document source for Q&A, or enable
   workspace capabilities and choose a project folder for coding.
4. **Start a conversation.** Try “Explain this project and how to run its
   tests” or “Summarize these documents and cite the sources.” Open the activity
   view to follow the work, then use Eval to test it on more examples.

## System requirements

- Apple Silicon Mac
- macOS 13 or newer
- Approximately 3 GiB for the application, plus space for updates and optional
  on-device model downloads

Current builds require a Developer ID signature and Apple notarization/stapling.
Do not bypass Gatekeeper for an unexpected signature or notarization failure.

## Install

1. Download the DMG and its `.sha256` file from
   [Releases](https://github.com/vpanghal/glance-releases/releases). Read that
   release's installation notes before upgrading an existing installation.
2. In Terminal, `cd` to the download directory and run `shasum -a 256 -c`
   against the downloaded `.sha256` file.
3. Open the DMG and drag the single `Glance.app` into Applications.

Glance, Lander, the normalizer helper and Code Mode worker are contained in that
one application bundle; terminal hosting runs inside Lander. Nothing is installed
as a separate service or application. Optional models are downloaded only after
your authorization and are not bundled in the application.

Updater-capable installations offer signed in-place updates with explicit
restart consent. The release ZIP contains the entire signed/stapled application,
not a frontend-only patch. `update-manifest.json` and its detached Ed25519
signature authorize the exact ZIP using the public key embedded in your installed
app. `beta-mac.yml` or `latest-mac.yml` accompanies each release for updater
interoperability. Do not replace the trusted key with a downloaded key or install
an expired/tampered update. Older installations without updater support, and
installations affected by a signing-key rotation, require a new DMG install.

## Included in the app

The Apple Silicon app includes the local Lander backend, the browser-accessible
Glance UI, isolated browser surfaces, microphone dictation, embedded terminal hosting,
normalization, and contained Code Mode execution. The Reason-ModernColBERT model is
distributed under CC-BY-NC-4.0; downstream use remains subject to its bundled
license.

This repository contains public binary releases of Glance. Atlas source code is
not published here.

For security reporting, see [SECURITY.md](SECURITY.md).
