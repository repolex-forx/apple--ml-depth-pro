# Repolex Knowledge Graph of apple/ml-depth-pro

RDF knowledge graph data for [apple/ml-depth-pro](https://github.com/apple/ml-depth-pro), parsed by [repolex](https://repolex.ai).

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
rlex download apple/ml-depth-pro
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9e65e4dbe9568d23c546fcec53302b10445e109e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9e65e4dbe9568d23c546fcec53302b10445e109e
│           └── chunk-001.nq.gz
├── blob
│   ├── 02fa0ad0740b5b47ab66682d0ae2efdf734f7221.nq.gz
│   ├── 0a401def2e1d6a2dd96b204e962569e9da5e0ef1.nq.gz
│   ├── 2b5d926d385a3791efecce5b80d9485f5691ed4c.nq.gz
│   ├── 2cd899f650978043c2c83348670beaf597e9ca30.nq.gz
│   ├── 3545a99993810b7d602f63c057640645b215f2b2.nq.gz
│   ├── 412be5b252712455c2ffbff0c8dc339b1112541f.nq.gz
│   ├── 51cb67aaa3cd74d0ba992d7859208527cdf8eb86.nq.gz
│   ├── 52080b686a64851c4bb62003884fbdeb55dced9a.nq.gz
│   ├── 54ac5722c5db5e9a6846f12fea9efc00f3e385e5.nq.gz
│   ├── 5900286509ca9535d4d29679b88055b5b6aed938.nq.gz
│   ├── 74882c0eacac7e9bde0e13008fab31037eae671d.nq.gz
│   ├── 770665fcd3e47948388d5da43487d9e75dc0f3fc.nq.gz
│   ├── 81da1dcdb786da7bbec861604f50d4f039f695ef.nq.gz
│   ├── 9ab354ba70bc1e32735aff3deecb4c78c1ab9eec.nq.gz
│   ├── a3a3da17d47bf91662463520afaf413f08676c3b.nq.gz
│   ├── c6c3768a1dcedccd99a58f9507f4edac3cde9da0.nq.gz
│   ├── d7650dbb60b990ed66b4444a1bbb7f7eaaed1390.nq.gz
│   ├── f1c85264843ec3be141d14ba6207b838c04cf895.nq.gz
│   ├── f31b4e16178c5e29a3ffcd1a2366fe585bc9c370.nq.gz
│   └── f6b5591157d2ce118d409d1888e0fc451ca0f24c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9e65e4dbe9568d23c546fcec53302b10445e109e.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 26 files
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

[apple/ml-depth-pro](https://github.com/apple/ml-depth-pro)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
