# JARVIS: privacy-conscious assistant research

**Status: research and integration planning; operational deployment not verified.**

The existing JARVIS project is maintained separately and privately. This public overview summarizes general engineering directions without copying private notes, personal data, credentials, or infrastructure details.

## Research areas
- Korean-language retrieval-augmented generation and source-grounded answers.
- Memory correction, deletion, provenance, and temporal validity.
- Tool contracts, idempotency, retries, and recovery from ambiguous external effects.
- Speech recognition, wake-word detection, text-to-speech, and playback verification.
- Model and hardware evaluation using measured capacity, latency, and end-to-end task completion.

## Proposed verification order
1. Inventory existing components and establish recovery points without modifying live state.
2. Build a small, permission-cleared evaluation dataset.
3. Evaluate retrieval and memory correctness, including correction and deletion cases.
4. Test tool execution with mocks, explicit authorization, and idempotency keys.
5. Test interruption and recovery; only then evaluate voice and serving performance.

## Boundaries
The presence of a design note does not prove a model, memory database, voice service, or external connector is installed or functional. Do not publish private conversation histories, profiles, tokens, configuration, or raw research archives.
