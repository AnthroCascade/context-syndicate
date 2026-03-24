# Noise Taxonomy

## Domain

Recognising conversation content that has served its purpose and should not carry forward into a fresh context.

## Optimises for

Ruthless exclusion. When uncertain, drop. The clean transcript is a tool, not a record.

## Noise classes

### Corrective sub-threads

A corrective sub-thread starts when the user challenges or corrects output. It includes: the challenge, the model's acknowledgement, the model's explanation or diagnosis of why it failed, the user's response to that diagnosis, and any further exchange before a new output is attempted.

The correction is load-bearing only until it has been applied. Once a revised output exists that addresses the correction, the corrective exchange that preceded it is noise.

Test: Is there a subsequent output in the transcript that addresses this correction? If yes, the entire corrective exchange is noise.

### Diagnostic exchanges

Conversations about why something failed. The model offers an explanation. The user challenges it. The model revises the explanation. Nothing is produced except competing diagnoses.

The diagnosis is not the fix. If a fix exists later in the transcript, the diagnostic conversation is noise. If no fix was ever produced, the whole thread — failure, diagnosis, and all — is noise.

### Apologies and acknowledgements

Model self-flagellation. "You're right, I apologise." "I understand, that was a mistake." "Fair point." These carry no content. Drop all of them.

Exception: an acknowledgement that contains a restatement of direction the user just gave — that restatement may be signal embedded in noise. Extract the direction if necessary; drop the acknowledgement wrapping it.

### Sidebars

Exchanges that don't advance the primary task. An interesting observation, a related question, a digression. If the sidebar did not result in a decision or an output that the main thread depends on, it is noise.

### Abandoned directions

A direction started and then dropped — explicitly ("let's not go there") or implicitly (the conversation continued without using the output). The output, the exchange that produced it, and any evaluation of it: all noise.

Test: Does any subsequent signal message depend on this direction? If not, it is abandoned.

### Meta-process discussion

Conversations about process rather than execution. Discussions about which approach to take, which tool to use, how to scope the task. Once a decision is reached, only the decision matters — not the negotiation that preceded it.

Exception: if the reasoning behind a decision is genuinely load-bearing for downstream signal messages, treat as potential SIGNAL. Apply scepticism.

## Anti-patterns

- Keeping a corrective exchange because the diagnosis was interesting
- Treating the model's self-correction as equivalent to a fresh output
- Preserving apologies as evidence that a problem was acknowledged
- Keeping diagnostic content to "explain" a fix that already speaks for itself
- Treating the first message in a corrective sub-thread as signal because it contains a finding (the finding is noise if the fix already exists)
