<p align="center">
  <a href="https://sigmashake.com">
    <img src="https://docs.sigmashake.com/img/hero.png" alt="SigmaShake — AI Agent Guardrails" width="900"/>
  </a>
</p>

<h1 align="center">@sigmashake/ssg</h1>

<p align="center">
  <strong>AI Agent Guardrails.</strong> Sub-2ms governance for every AI agent. Local-first. Zero tokens.
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/@sigmashake/ssg"><img src="https://img.shields.io/npm/v/@sigmashake/ssg?color=CB3837&logo=npm" alt="npm version"/></a>
  <a href="https://www.npmjs.com/package/@sigmashake/ssg"><img src="https://img.shields.io/npm/dm/@sigmashake/ssg?color=CB3837" alt="npm downloads"/></a>
  <a href="https://pypi.org/project/sigmashake/"><img src="https://img.shields.io/pypi/v/sigmashake?color=3776AB&logo=pypi&logoColor=white" alt="PyPI"/></a>
  <a href="https://github.com/sigmashakeinc/ssg/pkgs/container/ssg"><img src="https://img.shields.io/badge/ghcr.io-sigmashakeinc%2Fssg-0db7ed?logo=docker&logoColor=white" alt="Docker"/></a>
  <a href="https://github.com/sigmashakeinc/ssg/releases"><img src="https://img.shields.io/github/v/release/sigmashakeinc/ssg?logo=github" alt="GitHub release"/></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-proprietary-red" alt="License: Proprietary"/></a>
  <a href="https://docs.sigmashake.com"><img src="https://img.shields.io/badge/docs-docs.sigmashake.com-4a9eff?logo=readthedocs&logoColor=white" alt="Docs"/></a>
  <a href="https://discord.gg/ghWA8Xhs4T"><img src="https://img.shields.io/badge/discord-join-5865F2?logo=discord&logoColor=white" alt="Discord"/></a>
</p>

<p align="center">
  <a href="#install">Install</a> ·
  <a href="#quick-start">Quick start</a> ·
  <a href="#see-it-in-action">Demos</a> ·
  <a href="#documentation">Docs</a> ·
  <a href="https://discord.gg/ghWA8Xhs4T">Discord</a>
</p>

---

## What is ssg?

`ssg` is SigmaShake's AI agent governance CLI. It evaluates every tool call your AI agent is about to make against a set of local rules — blocking dangerous operations, asking for approval on risky ones, and recording everything to a queryable audit log. It runs locally in sub-2 milliseconds, spends zero AI tokens on governance, and works with every major AI client: **Claude Code**, **Cursor**, **GitHub Copilot**, **Codex**, **Gemini**, **Antigravity**, and **Pi**.

## See it in action

### 🛡️ Real-time approval dashboard

A local dashboard at `http://localhost:5599` shows pending approvals, blocked commands, and a live audit stream.

![ssg approval dashboard — rule evaluation in action](https://docs.sigmashake.com/img/demos/eval-demo.gif)

### 🌍 Community rules hub

Pull curated rulesets from [`hub.sigmashake.com`](https://hub.sigmashake.com) — covering bash, secrets, SQL, Docker, Kubernetes, Python, React, Terraform, and more.

![ssg hub — searching and installing rulesets](https://docs.sigmashake.com/img/demos/hub-demo.gif)

> 🎥 [Watch the full dashboard tour](https://docs.sigmashake.com/img/demos/dashboard_demo.webm) (WebM, 208 KB) · or read the [dashboard docs](https://docs.sigmashake.com/dashboard).

## Why teams pick ssg

- 🏠 **Local-first evaluation** — no outbound AI calls; zero tokens spent on governance
- ⚡ **Sub-2ms rule eval** — faster than the network call it gates
- 🧩 **Works everywhere** — Claude Code, Cursor, Copilot, Codex, Gemini, Antigravity, Pi
- 🔍 **Queryable audit trail** — every decision stored locally; searchable from the CLI
- 🌐 **Hub rulesets** — 20+ curated packs authored by the community
- 🏢 **Fleet-ready** — SSO, org policies, and SIEM forwarding for enterprise deployments

## Install

```bash
npm install -g @sigmashake/ssg
ssg --help
```

### Every channel

| Channel | Install |
|---------|---------|
| npm | `npm install -g @sigmashake/ssg` |
| PyPI | `pip install sigmashake` |
| Homebrew | `brew install sigmashakeinc/tap/ssg` |
| winget | `winget install SigmaShake.SSG` |
| Docker (OS-agnostic) | `docker run --rm -i ghcr.io/sigmashakeinc/ssg:latest eval < call.json` |

The Docker image at `ghcr.io/sigmashakeinc/ssg` is also the install path for musl distros (Alpine, Chimera) and hosts running glibc < 2.24. See the [Docker guide](https://docs.sigmashake.com/intro) for usage.

## Quick start

```bash
ssg init       # install adapters + local config for every supported AI client
ssg setup      # guided ruleset selection
ssg serve      # start the local approval dashboard at localhost:5599
```

Evaluate a single tool call from the shell:

```bash
echo '{"tool":"Bash","input":{"command":"rm -rf /"}}' | ssg eval
```

Wire `ssg` into just one client:

```bash
ssg init --client=claude-code    # or: cursor | copilot | codex | gemini | antigravity | pi
```

## Documentation

Full reference and guides at **[docs.sigmashake.com](https://docs.sigmashake.com)**.

| Get started | Integrate |
|---|---|
| 🚀 [Getting started](https://docs.sigmashake.com/getting-started) | 🔌 [MCP server](https://docs.sigmashake.com/mcp) |
| ⚡ [Intro](https://docs.sigmashake.com/intro) | 🤖 [Claude Code](https://docs.sigmashake.com/claude-code-integration) |
| 📺 [Dashboard](https://docs.sigmashake.com/dashboard) | 🧩 [Every adapter](https://docs.sigmashake.com/adapters) |

| Author rules | Operate |
|---|---|
| 📝 [Rule syntax](https://docs.sigmashake.com/rule-syntax) | 💻 [CLI reference](https://docs.sigmashake.com/cli) |
| 🌍 [Hub guide](https://docs.sigmashake.com/hub) | 🏗️ [Architecture](https://docs.sigmashake.com/architecture) |
| 📦 [Publishing rulesets](https://docs.sigmashake.com/publishing) | 🏢 [Enterprise fleet](https://docs.sigmashake.com/fleet-mcp-setup) |

## Supported AI clients

`ssg init` configures, out of the box:

<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-000000?logo=anthropic&logoColor=white" alt="Claude Code"/>
  <img src="https://img.shields.io/badge/Cursor-000000?logo=cursor&logoColor=white" alt="Cursor"/>
  <img src="https://img.shields.io/badge/GitHub_Copilot-24292e?logo=github&logoColor=white" alt="GitHub Copilot"/>
  <img src="https://img.shields.io/badge/Codex-412991?logo=openai&logoColor=white" alt="Codex"/>
  <img src="https://img.shields.io/badge/Gemini-4285F4?logo=google&logoColor=white" alt="Gemini"/>
  <img src="https://img.shields.io/badge/Antigravity-111111" alt="Antigravity"/>
  <img src="https://img.shields.io/badge/Pi-7C3AED" alt="Pi"/>
</p>

## Useful commands

| Command | What it does |
|---|---|
| `ssg init` | Install agent adapters and local configuration |
| `ssg setup` | Walk through recommended setup and ruleset selection |
| `ssg serve` | Start the local approval dashboard |
| `ssg eval` | Evaluate a tool call from stdin (JSON) |
| `ssg audit search` | Query local audit history for agents, tools, and actions |
| `ssg rule ...` | List, search, enable, disable, and edit rules |
| `ssg hub ...` | Search, install, update, and audit Hub rulesets |
| `ssg doctor` | Run a health diagnostic for the local installation |
| `ssg mcp-server` | Start the local MCP server for agent integrations |

## Authentication

Local rule evaluation, local dashboard usage, and local audit inspection work **without signing in**. `ssg auth login` unlocks account-backed features: Hub publishing, organization workflows, support, and private ruleset access.

## Community & support

- 💬 **Discord** — [discord.gg/ghWA8Xhs4T](https://discord.gg/ghWA8Xhs4T)
- 🐛 **Report an issue** — [github.com/sigmashakeinc/ssg/issues](https://github.com/sigmashakeinc/ssg/issues)
- 🏢 **Enterprise & support** — [support@sigmashake.com](mailto:support@sigmashake.com)
- 🌐 **Hub** — [hub.sigmashake.com](https://hub.sigmashake.com)
- 🔐 **Accounts** — [accounts.sigmashake.com](https://accounts.sigmashake.com)

## License

Proprietary. The `ssg` binary is free to use for local governance, auditing, and dashboard workflows. **Source code is not distributed** — this repository publishes release artifacts only. See [`LICENSE`](./LICENSE) for the full terms.

<p align="center">
  <sub>© Sigma Shake. All rights reserved. · <a href="https://sigmashake.com">sigmashake.com</a> · <a href="https://docs.sigmashake.com/policies/terms-of-use">Terms</a> · <a href="https://docs.sigmashake.com/policies/privacy-policy">Privacy</a></sub>
</p>
