# Recursive Character Chunking Analysis

## Does recursive chunking preserve sentence boundaries better?
Yes, usually better than fixed-size chunking. `RecursiveCharacterTextSplitter` tries larger separators first, so it is less likely to cut through a sentence or paragraph unless it has to fall back to smaller separators.

## How does it handle the podcast's conversational structure?
It handles the transcript better than fixed-size chunking because it tends to keep conversational turns and pauses together when the separator priority starts with paragraph breaks or line breaks. It still cannot fully understand speaker intent, so short back-and-forth exchanges may still be split if they are long enough.

## Does it respect PDF section headers?
More often, yes. When the separator priority favors paragraph boundaries first, recursive chunking is more likely to keep section headers attached to the paragraphs they introduce. It is still a text-based heuristic, so headers are preserved only when the extracted PDF text contains clear line or paragraph breaks.

## Summary
- Recursive chunking is a better fit than fixed-size chunking when boundary preservation matters.
- It is strongest on the PDF because the document has more explicit structure.
- For the podcast transcript, it is better than fixed-size chunking, but still limited by transcript formatting quality.
