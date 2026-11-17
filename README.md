# Aristotle

**Challenge assumptions. Reason from first principles. Choose a concrete next step.**

An agent skill for architecture, product, process, and strategy decisions where inherited assumptions may be choosing the solution for you.

## Install in one command

```bash
npx skills add jwexler10/aristotle-skill
```

Choose Claude Code, Cursor, Codex, or another supported agent in the installer.
Requires [Node.js](https://nodejs.org/) 22.20 or later. Installs to the current project
by default; add `--global` for a user-wide installation. See the
[skills CLI](https://github.com/vercel-labs/skills) for supported agents and options.

For a noninteractive installation to Claude Code, Cursor, and Codex together:

```bash
npx skills add jwexler10/aristotle-skill --skill aristotle --agent claude-code cursor codex --yes
```

Prefer a graphical install? Use the Claude marketplace option below.

## What it does

- Surfaces material assumptions and distinguishes them from real constraints.
- Establishes the requirements and evidence that survive without the current implementation.
- Compares credible approaches through speed, impact, and simplicity.
- Recommends a high-leverage action and names what evidence would change it.

Best for unsettled decisions. A diagnosed bug or routine task with locked requirements usually needs direct implementation instead.

## Before vs. after

**Example request:** “Our application is growing. Should we split it into microservices?”

| Aspect | Without the skill: illustrative pitfall | With Aristotle: intended behavior |
|---|---|---|
| Framing | Assumes growth means a distributed architecture. | Separates growth, deployment, ownership, and capacity requirements from the microservices proposal. |
| Comparison | Lists generic benefits of microservices. | Compares a targeted repair, modular monolith, and service split against the same actual constraints. |
| Next step | Recommends a migration before measuring the bottleneck. | Identifies the decisive unknown and recommends the smallest measurement or change that resolves it. |

These are illustrative comparisons, not recorded model outputs or benchmark results.
Actual results depend on the model, the prompt, and the evidence you provide.

## Install as a Claude plugin

This repository is both a standalone skill and a single-plugin marketplace. The
plugin and the skills CLI install the same `SKILL.md`; choose one route per host
to avoid duplicate installations.

### Claude and Cowork: no terminal

1. Open **Plugins** (or **Customize → Plugins**, depending on your version).
2. Choose **Add → Add marketplace → Add from a repository**.
3. Enter `jwexler10/aristotle-skill` or `https://github.com/jwexler10/aristotle-skill`.
4. Select **Aristotle** and add the plugin. Find its skill through `/` or the
   skill picker; when namespaced commands are shown, use `/aristotle:aristotle`.

Availability and organization controls depend on your Claude plan and account.
See [Anthropic's plugin installation guide](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

### Claude Code: marketplace commands

Run these inside Claude Code:

```text
/plugin marketplace add jwexler10/aristotle-skill
/plugin install aristotle@jwexler10-aristotle
```

Then invoke `/aristotle:aristotle` followed by your task. The marketplace is defined in
[`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json), and the plugin
in [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json).

### Manual installation

Download the repository using **Code → Download ZIP**, or clone it:

```bash
git clone https://github.com/jwexler10/aristotle-skill.git
```

Copy the entire `skills/aristotle` folder, including any supporting files, into the
appropriate directory in your target project:

| Agent | Project skill directory | Invocation |
|---|---|---|
| Claude Code, direct skill | `.claude/skills/aristotle/` | `/aristotle` |
| Codex | `.agents/skills/aristotle/` | `$aristotle` |
| Cursor | `.cursor/skills/aristotle/` | Ask the agent to use Aristotle. |

Each destination must contain `SKILL.md` directly. Other hosts may use different
discovery or invocation rules; follow their documentation. See the
[Codex skills guide](https://learn.chatgpt.com/docs/build-skills).

This is an instruction-only skill: no API key, MCP server, companion skill, or
executable script is required. Tools are useful when your actual task needs live
information or inspection of an existing project.

## Try it

The prompts below use Codex's `$aristotle` syntax. In Claude Code, use `/aristotle` for a
direct skills installation or `/aristotle:aristotle` for a marketplace plugin. In Cursor,
ask the agent to use Aristotle and give it the same task.


```text
$aristotle We think our growing application needs microservices. Challenge that assumption before we split the codebase.
```

```text
$aristotle Should this reporting feature compute results on demand or maintain a precomputed table? Separate actual constraints from inherited choices.
```

```text
$aristotle Review our plan to require account creation before trying the product. What foundations support that decision?
```

Expect an assumption check, supported foundations, distinct alternatives, and a concrete recommendation. The response format scales to your request.

## Adapt it

Supply your actual objective, constraints, evidence, and priorities. Edit the skill
to fit your workflow. It assumes no particular product, repository structure,
technology stack, or internal decision log. Applying a thinking skill does not
itself authorize changes, purchases, deployments, or other external actions.

## Repository contents

- [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json): Claude plugin metadata.
- [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json): installable marketplace catalog.
- [`skills/aristotle/SKILL.md`](skills/aristotle/SKILL.md): the complete skill.
- [`LICENSE`](LICENSE): MIT license for these instructions and documentation.

Copyright © 2026 Jason Wexler.
