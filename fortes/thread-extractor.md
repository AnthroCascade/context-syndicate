# Thread Extractor

## Game aim

One clean transcript. The forward-moving work, stripped of its history.

## Suppresses

- Preserving corrections once they have been applied
- Including apologies, self-diagnosis, or failure explanation in the output
- Carrying forward abandoned directions
- Treating all messages as equally load-bearing
- Producing a summary or digest instead of a real transcript

## Competence

Classification, not summarisation. The output is a real transcript — original messages in original order — not a compressed abstract. What gets cut is gone. What stays is verbatim.

## Draws on

- noise-taxonomy
- thread-signal

## Protocol

### 1. Establish the spine

Before classifying individual messages, read the full transcript and identify:

- What was the primary task or goal?
- What outputs were produced and accepted by the user?
- What decisions were made that shaped subsequent work?

This is the spine. Every message in the transcript is either spine, path to the spine, or noise.

### 2. Walk every message

Classify each message. No skipping.

Apply the signal tests from `thread-signal.md`. If the message passes, classify as SIGNAL. If not, apply the noise tests from `noise-taxonomy.md` and classify accordingly.

Three classes only:

- **SIGNAL** — keep verbatim
- **NOISE** — drop entirely
- **BRIDGE** — keep as a one-sentence `[context: ...]` annotation

Use BRIDGE only where dropping a message would make the next signal message incoherent to a reader who hadn't seen the original. Minimise bridges. When in doubt, drop.

### 3. Check coherence

Walk the classified messages in order. Does the transcript read as a coherent, self-contained document? Would a reader with no prior knowledge of the session understand the thread?

If not, promote specific NOISE messages to BRIDGE — one sentence only, clearly marked — or add minimal `[context: ...]` annotations between messages.

### 4. Compile

Write the clean transcript to `{source-filename}-clean.md` in the same directory as the source file.

Format:

```
**Human:** [message text]

**Assistant:** [message text]
```

Signal messages: verbatim.
Bridge annotations: `[context: one sentence]` inserted between messages, not attributed to Human or Assistant.
Noise messages: absent.

## Output format

File: `{source-filename}-clean.md`

One message block per exchange. No preamble. No summary. No explanation of what was removed. The clean transcript stands alone.
