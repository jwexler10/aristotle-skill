# Aristotle

**Challenge assumptions. Reason from first principles. Choose a concrete next step.**

An agent skill for architecture, product, process, and strategy decisions where inherited assumptions may be choosing the solution for you.

## What it does

- Surfaces material assumptions and distinguishes them from real constraints.
- Establishes the requirements and evidence that survive without the current implementation.
- Compares credible approaches through speed, impact, and simplicity.
- Recommends a high-leverage action and names what evidence would change it.

Best for unsettled decisions. A diagnosed bug or routine task with locked requirements usually needs direct implementation instead.

## Install

This repository contains a portable, instruction-only agent skill. No API key,
MCP server, executable script, or companion skill is required. Tools are useful
when your task needs current information or inspection of an existing project.

1. Download this repository with **Code → Download ZIP**, or clone it:

   ```bash
   git clone https://github.com/jwexler10/aristotle-skill.git
   ```

2. For a Codex project, copy the entire `skills/aristotle` folder into the target
   project's `.agents/skills/` directory. The result should be:

   ```text
   your-project/
     .agents/
       skills/
         aristotle/
           SKILL.md
   ```

   Keep any supporting files inside that folder when copying. For user-wide local
   Codex discovery, use `~/.agents/skills/aristotle/` instead. Choose one scope to avoid
   installing duplicate copies.

3. In Codex, invoke the skill with `$aristotle` followed by your task, or let the
   agent select it when your task matches the description. If it does not appear,
   restart Codex. See the [official skills guide](https://learn.chatgpt.com/docs/build-skills).

For another agent that supports `SKILL.md`, use that agent's documented skills
directory. You can also explicitly ask an agent to read and apply
[`skills/aristotle/SKILL.md`](skills/aristotle/SKILL.md). Discovery and invocation syntax
depend on the host.

## Try it

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

- [`skills/aristotle/SKILL.md`](skills/aristotle/SKILL.md): the complete skill.
- [`LICENSE`](LICENSE): MIT license for these instructions and documentation.

Copyright © 2026 Jason Wexler.
