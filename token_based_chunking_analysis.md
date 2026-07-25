# Token-Based Chunking Analysis

## Why token-based chunking is better for LLM context windows
Token-based chunking matches how models actually count input. A chunk that is 1,000 characters long can contain very different numbers of tokens depending on word length, punctuation, and formatting, so character limits are only a rough proxy.

## Token-based vs character-based chunking
- Token-based chunks are more consistent for prompt budgeting.
- Character-based chunks are easier to reason about visually, but they do not map cleanly to model limits.
- For the same nominal size, character-based chunks can underfill or overfill the token budget.

## Podcast vs PDF
- The podcast transcript benefits more from token-based chunking because speech transcripts often have uneven sentence lengths and filler text.
- The PDF also benefits, but it already has more structure, so the difference is less noisy than in the transcript.

## Summary
- Use token-based chunking when the target is an LLM context window.
- Keep character-based chunking only when you need a simple text heuristic or a quick visual baseline.
