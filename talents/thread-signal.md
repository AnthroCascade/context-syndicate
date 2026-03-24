# Thread Signal

## Domain

Recognising conversation content that constitutes positive forward progress — the thread worth carrying into a fresh context.

## Optimises for

The minimum set of messages that makes the clean transcript coherent and purposeful. Less is more. If the subsequent conversation doesn't depend on it, it doesn't need to be there.

## Signal classes

### Forward instructions

Any message where the user gives new direction, makes a request, or establishes a constraint. Always signal.

Exception: instructions immediately superseded ("actually, do X instead of Y") — the superseded instruction is noise; the superseding instruction is signal.

### Accepted outputs

Any output the user accepted, built on, or used as the basis for the next step. Acceptance may be explicit ("good, now...") or implicit (the next instruction assumes the output without challenging it).

Keep the output verbatim. Keep any acceptance message that contains new direction. Drop pure acknowledgements ("great", "ok", "yes") that carry no further instruction.

### Established decisions

Moments where the user made a clear choice that shaped subsequent work. The decision is signal. The deliberation that preceded it may be noise — see meta-process discussion in noise-taxonomy.

Test: If this decision were absent from the clean transcript, would a reader misunderstand why subsequent work took the shape it did? If yes, it is signal.

### Final accepted outputs

The last accepted version of any piece of work — draft, plan, specification, analysis. Always signal, regardless of what preceded it.

When multiple versions exist and only the last was accepted, earlier versions are noise unless they contain material the final version deliberately excludes and which the subsequent thread depends on.

## Signal tests

For each message, apply in order:

1. **Does it advance the primary task?** A step forward, not a repair of a backward step.
2. **Does the subsequent conversation depend on it?** Remove it and check whether the next signal message still makes sense without it.
3. **Does it establish something durable?** A decision, an output, a direction that persists into subsequent exchanges.

Pass any one test: likely signal. Fail all three: likely noise. When uncertain, drop.

## Anti-patterns

- Treating the user's challenge that opens a corrective sub-thread as signal (it is the entry point to noise)
- Keeping partial outputs superseded by complete ones
- Preserving "that's wrong" messages when the correction is already in the transcript
- Including transitional messages ("let's try a different approach") when the approach itself is already captured in what follows
