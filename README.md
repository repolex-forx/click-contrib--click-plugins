# Repolex Knowledge Graph of click-contrib/click-plugins

RDF knowledge graph data for [click-contrib/click-plugins](https://github.com/click-contrib/click-plugins), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download click-contrib/click-plugins
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ab3c1e7f0bd8a5c47ecc7db9ed9cfebe80b22175
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ab3c1e7f0bd8a5c47ecc7db9ed9cfebe80b22175
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d3356c4299c695fa2717036bcb9e7156733e713.nq.gz
│   ├── 78f90b4f33df848ad7e7b97edb5341bf302add8b.nq.gz
│   ├── 90bad5fd3814cf453fa6a5ebd5586acc92a3b363.nq.gz
│   ├── ae906b30e103b76e560c747cc495286ad061ada6.nq.gz
│   ├── d095200e3f7c6a2229f4512562ab2cf2de6f11e8.nq.gz
│   ├── dfc55a32436b05bf95ffdc8369274740238c67bb.nq.gz
│   ├── eae1c9a8b3f465731dacd8634f5f55f288587ee5.nq.gz
│   ├── f2f8dff3da9cc451eafcc1cdb130b0538e97b174.nq.gz
│   └── f88694e17d1fe8cc05b81fc60b95eb3bdfc31a79.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ab3c1e7f0bd8a5c47ecc7db9ed9cfebe80b22175.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[click-contrib/click-plugins](https://github.com/click-contrib/click-plugins)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
