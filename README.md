# WingIndex Next

**A source-grounded aviation document assistant.**

WingIndex Next is a private, locally running pilot-document application. It helps authorized users search their own manual libraries, ask questions, and open the exact source pages behind an answer.

**Source-grounded by design:** the answer generator is instructed to use only retrieved pages from the user's authorized library. Each factual paragraph, list item, or table row needs its own page citation. The validation path rejects missing or invalid citations and can limit or withhold answers when source coverage is incomplete. Citations make claims traceable; they do not guarantee that every generated interpretation is correct.

## The answer flow

![WingIndex Next source-grounded answer flow](assets/wingindex-next-workflow.png)

The engineering work focuses on:

- Checking a user's library access before search, answer generation, or source viewing.
- Building a RAG pipeline that retrieves relevant document pages and gives the answer generator bounded source context. Retrieval can use lexical search and compatible vector embeddings.
- Splitting supported text-layer PDF pages into overlapping chunks, preparing embeddings, and validating the index against the original source. The initial manual pack reused existing validated vectors rather than embedding those PDFs again.
- Binding citations to a document revision and original PDF page.
- Letting readers open the cited page as a preview instead of downloading an entire manual.
- Preparing supported text-layer PDFs with resumable uploads and processing checkpoints.
- Using an evaluation harness with frozen question sets, replayable retrieval context, and source checks to study answer quality and regressions. These evaluations are separate from the application's normal answer path.

**Selected stack:** Node.js, SQLite, a responsive web client, and PDF page previews.

**Current status:** A local pilot application. Independent HTTPS hosting and on-device offline answering are not complete. It is a reference aid, not a substitute for approved manuals or aircraft-specific checks.

## Development activity

WingIndex and WingIndex Next are separate private repositories in the same project family. Their GitHub histories show **30 pull requests in total, 28 merged**:

| Repository | Development history | Pull requests | Merged | Commits on main |
| --- | --- | ---: | ---: | ---: |
| WingIndex | August–September 2026 (~1 month) | 27 | 25 | 65 |
| WingIndex Next | September 2026 (under 1 month) | 3 | 3 | 80 |

*Figures are repository-specific snapshots as of September 24, 2026. The public repository contains an overview and diagram; source code and manual content remain private.*
