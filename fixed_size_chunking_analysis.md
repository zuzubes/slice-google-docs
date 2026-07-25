# Fixed-Size Chunking Analysis

## Does fixed-size chunking break sentences in the middle?
Yes. `CharacterTextSplitter` cuts by character count, so sentences can be split anywhere a chunk boundary lands. This is easiest to see at `500` characters with `0` overlap, where chunk edges are most abrupt.

## How does it handle paragraph boundaries?
It does not preserve them reliably. Paragraphs are only kept intact if they happen to fit inside a chunk window. Otherwise, paragraph breaks are ignored or split across chunks.

## Which content type handles fixed-size chunking better?
The PDF generally handles fixed-size chunking better than the podcast transcript. The PDF text is usually more structured and paragraph-based, while the transcript is conversational and more likely to produce awkward mid-sentence splits.

## Summary
- Smaller chunks produce more boundary breaks.
- Larger overlaps reduce information loss, but they also create more repeated text.
- The PDF is the cleaner candidate for fixed-size chunking, but both sources are better served by a structure-aware splitter when exact boundaries matter.
