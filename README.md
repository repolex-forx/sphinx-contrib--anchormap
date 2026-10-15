# Repolex Knowledge Graph of sphinx-contrib/anchormap

RDF knowledge graph data for [sphinx-contrib/anchormap](https://github.com/sphinx-contrib/anchormap), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/anchormap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d73763e0694cd417babbe11cb4c177b7f6886183
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d73763e0694cd417babbe11cb4c177b7f6886183
│           └── chunk-001.nq.gz
├── blob
│   ├── 3ed9a8afaa81d5a6bbc637df593df9de2d38ff66.nq.gz
│   ├── 5d24ff14b48ce89c8b9e3865f120c8ea685630ea.nq.gz
│   ├── 67d36375e6cbceca160cca91e9472f1fbe8ef64c.nq.gz
│   ├── 8620b2da5741421f1b2ef98850b47631c3e53c0c.nq.gz
│   ├── 8963fec3df7402376105304eecb4657618c1bd85.nq.gz
│   ├── 913a9ad6906c7500f6fb8eba135da9302dbc028b.nq.gz
│   ├── a0f6f8c6f410d595ad00276d3f6d928bc26a4e24.nq.gz
│   ├── c0460fa6d51c4e9e89a0e99927fc540fea4e7236.nq.gz
│   ├── d7de51dd622b7f9f59bee4d47503ee27d58714f0.nq.gz
│   ├── de7df723507ee62c74274f23434b911bc764f489.nq.gz
│   ├── ea3dd6b1e5cdea001e5299eeef0eca662b3c5d1c.nq.gz
│   └── f50f6492e34038ecd972dc9d33108ee4aec9f30c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d73763e0694cd417babbe11cb4c177b7f6886183.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 19 files
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

[sphinx-contrib/anchormap](https://github.com/sphinx-contrib/anchormap)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
