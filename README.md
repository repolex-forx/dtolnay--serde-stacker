# Repolex Knowledge Graph of dtolnay/serde-stacker

RDF knowledge graph data for [dtolnay/serde-stacker](https://github.com/dtolnay/serde-stacker), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/serde-stacker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 77f36700ac40b18a9341d8e5d2a1dc5d5e793a8b
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 77f36700ac40b18a9341d8e5d2a1dc5d5e793a8b.nq.gz
│   └── repolex
│       └── 77f36700ac40b18a9341d8e5d2a1dc5d5e793a8b
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 33c947ae0fa9247500b0a7669e3258b86349324c.nq.gz
│   ├── 43fce39f56ac3b0462105f76aadc1cfbb53267e3.nq.gz
│   ├── 5ad4a8b924c861ad6a6c5635eec4dde1019e7bcf.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 779df500e29623a18d5d7ffa595c37be4307a4dd.nq.gz
│   ├── 77b809c03008aa0cface457b4d15afeb4331bda6.nq.gz
│   ├── ae1ee44a309fbf17b03f86ef9f26b1ad364cbb84.nq.gz
│   ├── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
│   ├── ec2159355c970f06e155cce3f5b2ee7b0d3399a0.nq.gz
│   └── f7d41a654a2b16c708f78627e5c6b1e945d1b609.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 77f36700ac40b18a9341d8e5d2a1dc5d5e793a8b.nq.gz
├── filetree
│   └── 77f36700ac40b18a9341d8e5d2a1dc5d5e793a8b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[dtolnay/serde-stacker](https://github.com/dtolnay/serde-stacker)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
