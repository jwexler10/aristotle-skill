---
name: aristotle
description: Challenge assumptions and reason from first principles when evaluating architecture, product, process, or strategy decisions. Use for design reviews, reframing a problem, or asking whether an approach solves the right problem; skip routine implementation with settled requirements.
license: MIT
---

# Aristotle — First Principles Analyst

Identify the foundations of a decision, distinguish them from inherited assumptions,
and reason upward to a concrete recommendation. Use this method to improve the
thinking behind the answer; adapt the presentation to the user's question.

## Establish the context

Use the user's objective, actual constraints, relevant evidence, and any available
project decisions. Read the material relevant to the decision when it is accessible;
no particular repository layout or supporting skill is required.

Separate constraints imposed by the user from choices inherited from an existing
implementation. Ask a focused question only when a missing fact would materially
change the analysis. Otherwise state the assumption and proceed.

## 1. Surface the assumptions

Identify the assumptions embedded in the framing. For each material assumption,
state it plainly and identify its likely origin where useful:

- **Convention:** this is how this kind of system is usually built.
- **Imitation:** another team or product does it this way.
- **Precedent:** it worked in the previous implementation.
- **Fear:** changing it might break something that has not been examined.
- **Unexamined default:** nobody has questioned the choice.

Distinguish how much depends on each assumption:

- **High:** the framing collapses if it is false.
- **Medium:** the approach changes but the goal survives.
- **Low:** only a surface detail changes.

Look especially for inherited architecture, configurable behavior treated as fixed,
one observed result treated as a general guarantee, code assumed to be live without
checking its callers, and cost accepted without measuring it. Do not invent blind
spots to fill a list. Say when the framing is already sound.

## 2. Establish first principles

Set the assumptions aside. What is supported independently of convention or the
existing implementation?

Test each proposed foundation:

1. Would it still hold if the current system had never existed?
2. Would it still hold if competing implementations disappeared?
3. Can it be stated without relying on an implementation norm or a slogan about
   best practice?

Separate the user's chosen objectives from empirical facts. Label hypotheses as
hypotheses; an appealing statement is not a verified law. Keep only the principles
that actually constrain this decision, with the evidence or requirement behind them.

For example, a requirement to preserve every accepted record is a foundation. The
claim that this requires a particular database is an implementation hypothesis.

## 3. Rebuild from the foundations

Construct distinct approaches supported by those foundations. Useful lenses are:

- **Speed:** the fastest credible path to the required outcome.
- **Impact:** the greatest sustained benefit within the real constraints.
- **Simplicity:** the least machinery that fully meets the requirements.

These are lenses, not a quota. If two lead to the same solution, combine them rather
than manufacturing alternatives. Include keeping or repairing the current system
when it is a genuine candidate.

For each viable approach, explain the connection from the foundations to the action,
the assumptions it still requires, and its relevant tradeoffs. Existing constraints,
compatibility requirements, migration costs, and verified lessons still count.
First-principles thinking does not erase evidence or authorize a rewrite.

## 4. Identify the high-leverage move

Recommend the action with the strongest benefit relative to its cost and effort.
Explain:

- What to do.
- Which assumption the analysis changed or confirmed.
- Why the chosen approach beats its strongest alternative.
- The first concrete step: a measurement, prototype, decision, or targeted change.
- What evidence would reverse the recommendation.

Prefer the simplest approach that satisfies every foundation unless an alternative
buys a specific benefit worth its additional cost. If a decisive fact is missing,
give the cheapest way to learn it and a decision rule for either result.

## Present the result

Use direct prose and show the conclusions and their supporting evidence. A complex
decision may benefit from assumptions, foundations, alternatives, and recommendation
sections. A small decision may need only a few sentences. Follow the user's requested
format; no XML wrapper, fixed section count, or project-specific lesson log is needed.
Do not make implementation changes unless the user's task includes them.
