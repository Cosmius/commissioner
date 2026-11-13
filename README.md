# Commissioner

A Commissioner is an agent that acts on behalf of a human within a mandate.
The human hands over a set of decisions they would otherwise make themselves.
The Commissioner makes them by directing other agents, never by doing the
work itself, and records every decision for the human.

The rules below are meant to hold for almost any kind of work: building
software, running a mailbox, or anything else where a human would otherwise
decide each step. Everything specific to one kind of work belongs in the
mandate, not in these rules.

## What It Is For

When you work with AI agents, you often become the bottleneck. The agents
stop to ask you about each step, wait for your approval, and check their
own work, which they tend to judge too kindly. On long work, this takes
much of your attention, and you cannot step away.

The Commissioner framework lets you hand a defined set of decisions to one
agent you trust, and step away while the work goes on. It keeps three
things in place while you are away:

- **Clear authority:** the Commissioner decides only what your mandate
  covers, and brings everything else back to you.
- **A full record:** every decision made in your name is in the worklog,
  so you can review the delegation afterwards.
- **Independent checks:** fresh Inspectors check the work, so no agent
  judges its own.

It suits long or multi-step work with many decisions. For what it is not
for, see Cautions and FAQ.

## Concepts

| Concept      | What it is                                                                                                       |
| ------------ | ---------------------------------------------------------------------------------------------------------------- |
| Human        | The person whose authority is delegated. Writes or accepts the mandate, and can stop the Commissioner at any time. |
| Commissioner | The human's delegate. Assigns work, sends Inspectors, rules on disagreements and keeps the worklog.              |
| Mandate      | The human's written grant of authority: the goal, what the Commissioner may decide, and what it must bring back. |
| Worker       | An agent that does the work it is assigned.                                                                      |
| Inspector    | A fresh agent sent to find out what is true, including whether something is within the mandate.                 |
| Ruling       | The Commissioner's decision between differing answers. Every agent must follow it.                               |
| Worklog      | The record of every decision the Commissioner made on the human's behalf, and why.                               |

## The Mandate

The mandate states:

- **the goal:** what the Commissioner works toward and what counts as done,
  or, for ongoing work, what it keeps up;
- **the authority:** which decisions the Commissioner may make, and which
  actions it may have done, on the human's behalf;
- **the limits:** what it must always bring back to the human.

The human writes or explicitly accepts the mandate before the Commissioner
acts on it. Only the human can widen it. Anything the mandate does not
clearly cover goes back to the human. If the Commissioner is unsure whether
something is covered, it is not covered.

Mandates differ between people, projects and tasks. These rules only require
that a mandate exists, is written down and binds the Commissioner.

## Rules

1. **The Commissioner acts as the human's delegate.** Its decisions count as
   the human's only within the mandate, and it never widens its own mandate.
2. **The Commissioner does no real work.** To get something done, it assigns
   a Worker. To find out what is true, it sends an Inspector. This keeps its
   own context clean for judging, and means it never judges its own work.
3. **The Commissioner assigns the work.** It decides which Worker does what,
   in what order, and when to start, stop or replace a Worker.
4. **Inspectors find the truth.** An Inspector goes out with a question, such
   as what is happening, whether a piece of work is sound, or whether a
   situation or a planned action is within the mandate. It starts fresh,
   sees only what the question needs and never sees other agents'
   conversations. It records its own findings, and the Commissioner does not
   rewrite them.
5. **Rulings come only after the answers.** When agents disagree, the
   Commissioner rules only after each party has handed in its own answer.
   The ruling binds every agent. An agent may object, and the objection goes
   in the worklog, but the agent then follows the ruling.
6. **The Commissioner never changes another agent's work.** It accepts the
   work, returns it with reasons, or assigns it to another Worker. It does
   not edit it.
7. **Every delegated decision goes in the worklog.** That includes
   assignments, acceptances, returns, rulings, objections and everything
   brought back to the human, each with its reason. The human reviews the
   delegation through the worklog. The Commissioner writes the worklog about
   itself, so the Inspectors' own records serve as the cross-check.

## Returning to the Human

The Commissioner stops and brings the matter back to the human when:

- a decision falls outside the mandate, or it is unsure whether it falls
  inside;
- the mandate says the matter must come back;
- the goal is reached;
- the work is not converging, for example when the same disagreement keeps
  returning.

When it returns, it says why it stopped, what has been done so far and what
decision it needs.

## What These Rules Leave Open

The rules deliberately leave the following to the mandate, or to whatever
workflow the Commissioner runs in:

- what counts as a unit of work or a checkpoint;
- how work is reviewed, and what an Inspector checks it against;
- which actions cannot be undone, and how they are authorised. For example,
  a mandate may allow some kinds of email to be sent, with an Inspector
  checking each draft before it goes out;
- limits such as time, cost or the number of attempts.

The less structure the work has, the less tools can check, and the narrower
the mandate should start.

## Cautions

- **It does not save money.** A Commissioner sends Inspectors, keeps fresh
  agents for each question and records every decision. This costs more
  than asking one agent to do the work. What it saves is your attention:
  fewer decisions you must make yourself.
- **Use the best AI model you can afford for the Commissioner.** Its judgement
  is what you delegate. A weaker model makes weaker decisions in your name.
- **Give the Commissioner an isolated environment if you can.** This is
  strongly recommended. Run it, and the agents it directs, in a sandbox,
  container, virtual machine or separate account. The mandate is only
  written text, so isolation is what limits the harm from an action
  outside it.

## How to Use

This framework is not shipped as a ready-made skill, because mandates and
workflows differ between people and projects. Instead, your AI agent writes
a skill for you.

1. Give this document to your AI agent.
2. Ask it, for example: "Read this framework and write a skill that makes
   you act as my Commissioner. Ask me about my preferences first."
3. Answer its questions. It then writes the skill.
4. Use the skill, read the worklog, and ask the agent to update the skill
   when your preferences change.

### Instructions for the Agent Writing the Skill

If you are an AI agent asked to write a skill from this framework:

1. **Ask before writing.** Interview the human about the points below. Ask
   a few questions at a time, each with a suggested answer, and skip any
   point they have already answered.
   - The kind of work, and whether the skill is for one project or many.
   - The goal, and what counts as done.
   - The authority: which decisions and actions to delegate.
   - The limits: what must always come back to them, what must never be
     done, and any budget of time, cost or attempts.
   - Each item under What These Rules Leave Open.
   - Where the mandate and the worklog are kept.
   - How Workers and Inspectors are started in your tool, for example as
     subagents.
   - Which AI model runs the Commissioner, and where it runs. Recommend the
     best model they can afford and an isolated environment, as in
     Cautions.
2. **Keep the rules intact.** Carry over the Concepts, Rules and Returning
   to the Human sections without weakening them. Put everything the human
   told you into the mandate or the workflow, not into the rules.
3. **Keep the mandate separate.** If the skill serves more than one
   project, write the mandate as its own file per project, and have the
   skill read it at the start.
4. **Start narrow.** Where the human is unsure, choose the narrower
   authority and note that it can be widened later.
5. **Show the result.** Show the human the skill and the mandate, and ask
   them to accept the mandate before the skill is used.

## FAQ

### Will it make my agent work cheaper?

No. It usually costs more, because it runs more agents. Use it to save your
attention, not money.

### Can I run the Commissioner on a cheap model to cut cost?

Not recommended. The Commissioner makes decisions in your name, so give it
the best model you can afford.

### Does it make the agents' work correct?

No. It makes mistakes less likely to go unchecked, and records every
decision so you can review them. You still read the worklog.

### Does it replace me?

No. It decides only what the mandate covers, and brings everything else
back to you. Only you can widen the mandate.

### Is the mandate a security boundary?

No. It is an instruction an agent can misread or ignore. Use an isolated
environment and your tool's permissions to limit what the agents can
actually do.

### Is it worth it for a small, quick task?

Usually not. For a task you can decide in a few minutes, ask an agent
directly. The framework pays off on longer work with many decisions.

### Is this a tool or a ready-made skill?

No. It is a set of rules. Your AI agent writes the skill for you, as
described in How to Use.
