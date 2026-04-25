# cleanse

Cleans a conversation transcript by extracting the positive forward thread and stripping corrective noise. Fires thread-extractor to classify every message as signal, bridge, or noise, then compiles the signal messages into a clean transcript. Use this when the current session's context has been poisoned by accumulated correction history and a fresh starting point is needed.

## Fortes

| Step | Forte | Mode | Receives additionally |
|---|---|---|---|
| 1 | thread-extractor | classify + compile | Full source transcript, noise-taxonomy talent, thread-signal talent |

## Coordination pattern

Single-agent. The thread-extractor receives the full transcript and all its talents, classifies every message, and returns the classified list and compiled clean transcript.

## Context requirements

Before thread-extractor fires:

- `syndicate.md` — context syndicate definition
- `fortes/thread-extractor.md` — forte spec
- `talents/noise-taxonomy.md` — noise class definitions
- `talents/thread-signal.md` — signal class definitions
- The source transcript in full

## Procedure

1. **Determine source.** If a file path argument is provided, use it. If not, look for the most recent file in the current caper's `artefacts/transcripts/` directory. If neither exists, stop and report — no source found.

2. **Read the source transcript** in full before proceeding.

3. **Fire thread-extractor.** Pass inline: the forte spec, both talent files, and the full source transcript. The forte establishes the spine, walks every message classifying it as SIGNAL (keep verbatim), BRIDGE (one-sentence annotation), or NOISE (drop), checks coherence of the result, and compiles the clean transcript.

4. **Write output.** Write the clean transcript to `{source-filename}-clean.md` in the same directory as the source file. The clean transcript is a real transcript — original messages in reading order — not a summary or digest.

5. **Report.** Present: source file path, output file path, and message counts — total, signal (kept verbatim), bridge (kept as annotation), noise (dropped).

## Output

- `{source-filename}-clean.md` in the same directory as the source

## Settlement condition

Clean transcript written to file. Message counts reported.

## Boundary

Classifies and compiles. Does not summarise, interpret, or add content. The output is verbatim signal messages in original order with minimal bridge annotations where coherence requires them. Noise messages are absent, not redacted.
