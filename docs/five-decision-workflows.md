# Five reusable workflows for better product and engineering decisions

By Jason Wexler

A useful recommendation identifies the objective, constraints, evidence,
alternatives, and the fact that would change the answer. Those questions repeat
across architecture reviews, product design, provider choices, and planning.

These five open-source skills give an agent a reusable procedure for one part of
that work. Each lives in its own repository, includes installation instructions,
and works independently. They are instruction-only Markdown packages under the
MIT license. No additional API key or MCP server is required by the skills.

## Choose the question before choosing the skill

| Your question | Skill | What the workflow asks for |
|---|---|---|
| Are we solving the right problem? | [Aristotle](https://github.com/jwexler10/aristotle-skill) | Assumptions, supported foundations, credible approaches, and a concrete next step. |
| What should this experience let a user accomplish? | [Apple](https://github.com/jwexler10/apple-skill) | The value moment, the interaction flow, deliberate omissions, and failure recovery. |
| How can this be immediately useful and still reward exploration? | [Bushnell](https://github.com/jwexler10/bushnell-skill) | First-encounter value, repeated-use depth, and a discovery path that preserves context. |
| Which approach should we actually choose? | [Syndesy](https://github.com/jwexler10/syndesy-skill) | Shared criteria, causal evidence, one target, the strongest alternative, and reversal conditions. |
| Is this worth the cost and scarce resources? | [Evgenii](https://github.com/jwexler10/evgenii-skill) | The relevant economic unit, total and marginal costs, incentives, and break-even thresholds. |

Start with the skill that matches the question. You do not need to install or run
all five for every task.

## Try a decision with Syndesy

Install it from the directory where you want to use it:

```bash
npx skills add jwexler10/syndesy-skill
```

The installer lets you choose Claude Code, Cursor, Codex, and other supported
agents. It requires Node.js 22.20 or later. For graphical installation through
Claude's plugin interface, use the repository's marketplace instructions.

Give the agent a decision with enough evidence to compare alternatives. For
example, in Codex:

```text
$syndesy We need to choose a logging system.

Our only engineer maintaining the self-hosted stack leaves next month.
A managed provider handled our saved queries in a trial, except one dashboard
that would take a day to rebuild. Retention and alerting meet our requirements.
Monthly cost is approximately the same. We have no requirement for two systems.

Should we keep the stack, move, or keep both permanently?
Choose a target and explain the strongest reason against it.
```

In Claude Code, use `/syndesy` for a direct skill install, or
`/syndesy:syndesy` for the marketplace plugin. In Cursor, ask the agent to use
Syndesy and provide the same facts.

For this fictional scenario, a defensible recommendation is to move to the
managed service, subject to verifying the trial covers operational requirements.
A permanent second stack retains the maintenance problem. A temporary migration
period needs an explicit end condition. A new compliance requirement, an unmet
recovery objective, or a material gap in the trial could change the choice.

That is an illustration of the intended reasoning, not a recorded model response
or a claim that a skill guarantees the recommendation. Check whether the actual
agent response uses the supplied evidence and names what would reverse its answer.

## Ask a different question with the same project

**Aristotle:** before deciding that growth requires microservices, separate
capacity, ownership, and deployment constraints from the proposed architecture.
An observed bottleneck is evidence; a familiar architecture is a candidate.

**Apple:** before adding a new dashboard, define what the user should accomplish,
the shortest route to it, and how partial results and failures should behave.
The workflow evaluates the experience beyond the success screenshot.

**Bushnell:** for that dashboard, write two different rewards: what a newcomer
understands immediately and what a returning user can investigate later. Then
design how each deeper question opens without losing the parent context.

**Evgenii:** for a provider decision, compare the outcome you need rather than
only the advertised unit price. Include migration, operations, failure costs,
and engineering attention. Identify the uncertain input that can change the
ranking, then calculate a break-even point or measure that input.

## How the packages are built

Each repository keeps one source of skill instructions at
`skills/<name>/SKILL.md`. A Claude plugin manifest and a single-plugin marketplace
catalog wrap that same source. The skills CLI discovers the skill folder directly.
Supporting material stays beside its skill; there are no mandatory dependencies
between these five repositories.

The public versions replace project-specific paths, examples, and required internal
documents with the user's actual context. They preserve the underlying method
without requiring the original project or its tooling.

## What has been checked

All five packages passed frontmatter validation and strict validation of the
Claude plugin and marketplace manifests. Installation from GitHub was exercised
in isolated projects through the skills CLI for Claude Code, Cursor, and Codex,
and through Claude Code's marketplace installer. Installed skill files were
compared with their source, including supporting files where present.

Those checks establish package loading and installation. They are not a behavioral
benchmark, a security certification, or evidence of improved outcomes across models.
The README comparisons are explicitly illustrative. Try a task whose evidence you
can inspect, and report a prompt and failure example if the method falls short.

## Install the one you need

```bash
npx skills add jwexler10/aristotle-skill
npx skills add jwexler10/apple-skill
npx skills add jwexler10/bushnell-skill
npx skills add jwexler10/syndesy-skill
npx skills add jwexler10/evgenii-skill
```

Run only the commands for the skills you want. Follow each repository's README for
host-specific invocation, graphical installation, and user-wide installation.
Each skill and its documentation may be adapted and redistributed under its MIT
license.

Contributions are most useful when they include the decision, supplied evidence,
actual response, and the specific step where the method failed. Open an issue in
the relevant skill repository with that example.
