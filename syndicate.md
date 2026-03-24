# Context Syndicate

Cleans conversation transcripts. Extracts the forward-moving thread. Strips everything else.

## Fortes

- **thread-extractor** — classifies every message in a transcript as signal or noise, then compiles the signal messages into a clean transcript suitable for use as fresh context

## The default is accumulation

A conversation accumulates. Corrections, apologies, diagnostic exchanges, sidebars, abandoned threads — they all land in the transcript with equal weight alongside the actual work. The positive thread is buried under the record of everything that went wrong on the way to it.

This syndicate treats accumulation as a failure mode. The transcript is an artefact, not a log. Edit it.

## Coordination

Not prescribed. The skill or user chooses.

## Commands

| Command | Forte | Settles when |
|---|---|---|
| `/cleanse` | thread-extractor | Clean transcript written to file |

## Resonance

- **thread-extractor:** fires when the author determines the current session's context has been poisoned by accumulated correction history and a fresh context is needed for subsequent work
