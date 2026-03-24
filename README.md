# Context Syndicate

This is a context management system. It coordinates an AI collaborator with a specific job: take a poisoned conversation transcript and produce a clean one.

## How it works

A conversation accumulates. Corrections, apologies, diagnostic exchanges, sidebars, abandoned directions — they all land in the transcript alongside the actual work. The positive thread is buried under the record of everything that went wrong on the way to it. When that history contaminates the working context, subsequent outputs degrade.

The context syndicate treats accumulation as a failure mode. It classifies every message as signal, noise, or bridge — then compiles the signal messages into a clean transcript suitable for use as fresh context in a subsequent session.

The output is a real transcript, not a summary. What gets cut is gone. What stays is verbatim.

## Fortes

Each forte has its own spec in [`fortes/`](fortes/):

| Forte | Job |
|-------|-----|
| [thread-extractor](fortes/thread-extractor.md) | Classifies every message as signal, noise, or bridge; compiles the signal messages into a clean transcript |

## Talents

Shared skill domains in [`talents/`](talents/):

| Talent | Domain |
|--------|--------|
| [noise-taxonomy](talents/noise-taxonomy.md) | Recognising content that has served its purpose and should not carry forward |
| [thread-signal](talents/thread-signal.md) | Recognising content that constitutes positive forward progress |

## The governing principle

The forte suppresses AI's default: treat all context as equally load-bearing. A transcript is not a log. It is an artefact. The thread-extractor edits it with the same ruthlessness an author applies to a draft — cutting everything that was necessary to get here but not necessary to go forward.

## Full specification

The complete syndicate spec — command, coordination, resonance — is in [syndicate.md](syndicate.md).
