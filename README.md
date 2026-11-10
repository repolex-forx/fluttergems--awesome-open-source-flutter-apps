# Repolex Knowledge Graph of fluttergems/awesome-open-source-flutter-apps

RDF knowledge graph data for [fluttergems/awesome-open-source-flutter-apps](https://github.com/fluttergems/awesome-open-source-flutter-apps), parsed by [repolex](https://repolex.ai).

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
rlex download fluttergems/awesome-open-source-flutter-apps
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1e7e724e21cce83b04327cb6c927b027ed5deee0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1e7e724e21cce83b04327cb6c927b027ed5deee0
│           └── chunk-001.nq.gz
├── blob
│   ├── 2dbecd63295bb36fe8d7956ea877ea609771d112.nq.gz
│   ├── 65b5f3e40f000fc15d7f3f57bd7f96c48aef06d0.nq.gz
│   ├── 6ee1443cf1d64eef20cf54fad2306ea3da21ecb1.nq.gz
│   ├── 7b0713b73c07e0b7cfa1652edea2fb18818a8ae3.nq.gz
│   ├── 8912e30d518bcba50315a2af91da7853ae0f6e1e.nq.gz
│   └── f9b01a21daf4030495a6752f29746d085f73ae68.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1e7e724e21cce83b04327cb6c927b027ed5deee0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 14 files
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

[fluttergems/awesome-open-source-flutter-apps](https://github.com/fluttergems/awesome-open-source-flutter-apps)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
