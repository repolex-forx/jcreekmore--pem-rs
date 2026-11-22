# Repolex Knowledge Graph of jcreekmore/pem-rs

RDF knowledge graph data for [jcreekmore/pem-rs](https://github.com/jcreekmore/pem-rs), parsed by [repolex](https://repolex.ai).

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
rlex download jcreekmore/pem-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7d6157704805dcedf703229926938a71b1ddd0b1
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7d6157704805dcedf703229926938a71b1ddd0b1.nq.gz
│   └── repolex
│       └── 7d6157704805dcedf703229926938a71b1ddd0b1
│           └── chunk-001.nq.gz
├── blob
│   ├── 139c48656ea3145c9d8b3f97dda172d3e92997be.nq.gz
│   ├── 1571a5ee037996d1f9da93c0ce1e42f85651c903.nq.gz
│   ├── 2372ee1cf5958254e1799d6a40139dba45d74463.nq.gz
│   ├── 53134fde26b8edc00a0b9a23f7a89aa9474dbb5a.nq.gz
│   ├── 78a5709a5fe107fe17b392b7f707f52c3589c572.nq.gz
│   ├── 7e16e1d7f8cd8161e9d33e3b923919f7d5cb5c7c.nq.gz
│   ├── 80039326e64ed6a2c31a9dcb136a3ed7a8f251ca.nq.gz
│   ├── 8d7f438312d7a663a2142c5be8442b8428814582.nq.gz
│   ├── ca6bd9c9f0f003894f35f45c3e4116daebd92273.nq.gz
│   └── f62760291a6b716a7a48444e75758dfe313f507d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7d6157704805dcedf703229926938a71b1ddd0b1.nq.gz
├── filetree
│   └── 7d6157704805dcedf703229926938a71b1ddd0b1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

[jcreekmore/pem-rs](https://github.com/jcreekmore/pem-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
