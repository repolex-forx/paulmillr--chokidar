# Repolex Knowledge Graph of paulmillr/chokidar

RDF knowledge graph data for [paulmillr/chokidar](https://github.com/paulmillr/chokidar), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download paulmillr/chokidar
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c0c8d20e49d337491891078d1081bf91bd178de6
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c0c8d20e49d337491891078d1081bf91bd178de6.nq.gz
│   └── repolex
│       └── c0c8d20e49d337491891078d1081bf91bd178de6
│           └── chunk-001.nq.gz
├── blob
│   ├── 0df29460c195146894e69319dfd45805bf2dc567.nq.gz
│   ├── 43f16abcadecdc863dc0dbd5f6ee9a3711f7ea19.nq.gz
│   ├── 453e1c66949d856e5501b7921663d15cc02a638b.nq.gz
│   ├── 4cd2de1f61deca0b6b8483da01911ba0a3adefc6.nq.gz
│   ├── 532d51d49be7ec66ea9405ad568a173bfac12af4.nq.gz
│   ├── 690ad2a836164cc0a25d78439f90215e914333ff.nq.gz
│   ├── 789ac2e5d9a0c619dd195fe9c50a65b749e22557.nq.gz
│   ├── 8c27184e967ba358f021395738d20dfd8d0eb39e.nq.gz
│   ├── 9d5d65248b73b580873b67b8987b0fa6a6783618.nq.gz
│   ├── afb93b999c3d1289099ba3fb67b1df0f35d8a758.nq.gz
│   ├── d9f629c668cdddd20645bfe886966b6e0c4be6a4.nq.gz
│   ├── e76afe2800f5a959fa400d813cb6d0e915af6cbb.nq.gz
│   ├── e7e0bcbf68e40dc2a41791edc9e344b5af58d327.nq.gz
│   ├── ed3d1a54547e495113af06fe5f77801022975fd9.nq.gz
│   └── fce5ba04531b4f34a723ed7311594e9238b987be.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── c0c8d20e49d337491891078d1081bf91bd178de6.nq.gz
├── filetree
│   └── c0c8d20e49d337491891078d1081bf91bd178de6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 25 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |

## Source repository

[paulmillr/chokidar](https://github.com/paulmillr/chokidar)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
