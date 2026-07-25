# Chunking Strategies Lab

This project compares different text chunking strategies for two source types:

- a podcast transcript generated from `data/CVX_manufacturing_podcast.mp3`
- a PDF document loaded from `data/The AI Ladder.pdf`

The goal is to compare chunking methods, inspect boundary quality, and document which strategy works best for each content type.

## Project Files

- `chunking_strategies.ipynb` - main notebook with Steps 1 to 8
- `chunking_recommendations.md` - final recommendation summary
- `fixed_size_chunking_analysis.md` - notes for fixed-size chunking
- `recursive_character_chunking_analysis.md` - notes for recursive chunking
- `token_based_chunking_analysis.md` - notes for token-based chunking
- `lab_proof.md` - place for proof or evidence from the lab
- `data/` - source podcast and PDF files

## What The Notebook Covers

1. Setup and data loading
2. Fixed-size chunking
3. Recursive character chunking
4. Token-based chunking
5. Visual comparison of chunk statistics
6. Chunk quality analysis using boundary checks
7. Recommendations by content type

## Requirements

The notebook installs the needed packages in Step 1, but the main dependencies are:

- `openai`
- `python-dotenv`
- `langchain-text-splitters`
- `pypdf`
- `tiktoken`
- `matplotlib`

## Setup

1. Open the notebook `chunking_strategies.ipynb`.
2. Make sure a valid `OPENAI_API_KEY` is available in the local `.env` file.
3. Run the notebook from top to bottom.

## Expected Outputs

- The podcast transcript is saved locally as `data/CVX_manufacturing_podcast_transcript.txt`
- Chunk statistics are printed for fixed-size, recursive, and token-based strategies
- Boundary quality is measured by checking whether chunk endings look sentence-complete
- Comparison plots are generated with `matplotlib`
- Final recommendations are written to `chunking_recommendations.md`

## Recommendation Summary

- Use `Recursive-1000` for most PDF and transcript work when preserving structure matters.
- Use `Token-500` when prompt-budget accuracy matters most.
- Use `Fixed-500` only as a simple baseline.

## Notes

- The notebook is designed to be inspectable: each step prints or saves intermediate results.
- The comparison focuses on the behavior of chunk boundaries, not only on chunk counts.
- If you rerun Step 1, the transcript file will be overwritten with a fresh transcription.

