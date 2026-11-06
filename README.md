# Repolex Knowledge Graph of sphinx-contrib/prettyspecialmethods

RDF knowledge graph data for [sphinx-contrib/prettyspecialmethods](https://github.com/sphinx-contrib/prettyspecialmethods), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/prettyspecialmethods
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 38fb1b784aa4a636d670f098dc5a6abf2de18c94
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 38fb1b784aa4a636d670f098dc5a6abf2de18c94
│           └── chunk-001.nq.gz
├── blob
│   ├── 10cb2108220c11458c6d873d3d5e2aa936f07661.nq.gz
│   ├── 2c8ae27b9b7e98ec930fc265fb365e2fb2306d01.nq.gz
│   ├── 3c7125a1c5cbc27a5dffc84104936030a92cf3d7.nq.gz
│   ├── 507e13dac54a3d645c1903655a2107e396b02691.nq.gz
│   ├── 533c570cd48599fc3edba5128a747c766367ca2c.nq.gz
│   ├── 55273db100e239fdc03ca2aef48f20a5101f576e.nq.gz
│   ├── 60358fe4beaeb96ff0b74c4f48555b59f184a205.nq.gz
│   ├── 692262e3cc4e4c8d821845e2c2c4698ca6002ee5.nq.gz
│   ├── 75cd7447e07608dc9fa376f8dc9095d58d896da2.nq.gz
│   ├── 874eb4eee9e6b9ade16e207bba49416fbda8a1e8.nq.gz
│   ├── bc6df17a0d95ea0153cc71c79e7c3209faa3509e.nq.gz
│   ├── c70671dc1e019d5f14e8d362ec0f91f609ba57dc.nq.gz
│   ├── ca2158b94435124c732893ee6b3cfc6937f6f541.nq.gz
│   ├── cb55fcae56401fd71805d0c067879e9532fd5824.nq.gz
│   └── cc5874e8883d802787e7ed8bcaeff0d2805bceb8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 38fb1b784aa4a636d670f098dc5a6abf2de18c94.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[sphinx-contrib/prettyspecialmethods](https://github.com/sphinx-contrib/prettyspecialmethods)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
