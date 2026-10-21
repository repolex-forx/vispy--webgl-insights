# Repolex Knowledge Graph of vispy/webgl-insights

RDF knowledge graph data for [vispy/webgl-insights](https://github.com/vispy/webgl-insights), parsed by [repolex](https://repolex.ai).

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
rlex download vispy/webgl-insights
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 80fbc1c5585d1fdedc58195b702a558e6c3965ed
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 80fbc1c5585d1fdedc58195b702a558e6c3965ed
│           └── chunk-001.nq.gz
├── blob
│   ├── 028e14d46d0580c3731b93e0f40338b3a0140421.nq.gz
│   ├── 03ed27ac0bad7cec89e682b9e909c51584782718.nq.gz
│   ├── 517488a2911ccf4cf043379cdd178c5b764c6b84.nq.gz
│   ├── 61cd85a3880d3c571e9e64930e063c6b8ce77221.nq.gz
│   ├── 8bc8c84a2e7d96942c01bbcdabd2a57f8be7be33.nq.gz
│   ├── 8d599243aa9366265f7df68b3b29e7d20497a8ee.nq.gz
│   ├── 8f37f46f68b824fd64fa493a712bd27fef322868.nq.gz
│   ├── b19b7180f3f2415bfa81b43bdad33c9e4d733100.nq.gz
│   ├── db92a80654cab5d489b40c402249b8fb50adaa12.nq.gz
│   └── f09f8ce9605564c866673e8afcea25592e2be434.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 80fbc1c5585d1fdedc58195b702a558e6c3965ed.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[vispy/webgl-insights](https://github.com/vispy/webgl-insights)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
