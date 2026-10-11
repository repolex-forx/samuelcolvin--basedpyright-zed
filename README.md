# Repolex Knowledge Graph of samuelcolvin/basedpyright-zed

RDF knowledge graph data for [samuelcolvin/basedpyright-zed](https://github.com/samuelcolvin/basedpyright-zed), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/basedpyright-zed
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a6012ade8a2440434c10924ecfc33fda012f9f55
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a6012ade8a2440434c10924ecfc33fda012f9f55
│           └── chunk-001.nq.gz
├── blob
│   ├── 4f6ca588e01bec367a3f292201610b9b2801ace0.nq.gz
│   ├── 5ae7563067065192d9c6b13d34bdd3d664a36639.nq.gz
│   ├── 6adda1691a4b3c143003353ba26104e17a47cc2e.nq.gz
│   ├── 7cf523123628bc85afd66acf0996381c1aca432f.nq.gz
│   └── c145771a67bffb71732b2a1cf03f29013a77243c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a6012ade8a2440434c10924ecfc33fda012f9f55.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
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

[samuelcolvin/basedpyright-zed](https://github.com/samuelcolvin/basedpyright-zed)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
