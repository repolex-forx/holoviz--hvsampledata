# Repolex Knowledge Graph of holoviz/hvsampledata

RDF knowledge graph data for [holoviz/hvsampledata](https://github.com/holoviz/hvsampledata), parsed by [repolex](https://repolex.ai).

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
rlex download holoviz/hvsampledata
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4119603311b5ed158020aa345fa7363876282e42
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4119603311b5ed158020aa345fa7363876282e42
│           └── chunk-001.nq.gz
├── blob
│   ├── 01a97f69567df7a6a680c5aa0fb12b7d454fd195.nq.gz
│   ├── 04c5ea483e9501b8699d065aa303499b1cf472d6.nq.gz
│   ├── 062b785d0008879ec5c4eb0eed57e37d51a20516.nq.gz
│   ├── 07fb6d33786c0865e70d20fe58276ef0bfe22dfa.nq.gz
│   ├── 0c949e4abd2148d88274f74e0a3a6ea04bf97f16.nq.gz
│   ├── 175926c974813ad58147f11d1470019f59f26270.nq.gz
│   ├── 21dd9cd4e11aa0fadb4c8493f89ed7f6629d3d76.nq.gz
│   ├── 27140f82348a6ddee8874138c8b60d4330b98e80.nq.gz
│   ├── 373c49e487c8daaceef7aaf09f92cc411cdd5872.nq.gz
│   ├── 4b11fd71ebf82ba56e79c8f36f5cc11191c048cc.nq.gz
│   ├── 6b88f2353fba85b17150762a576eb87b148ec76f.nq.gz
│   ├── 7006f53221ae41103ff2b9622085c20c443627d5.nq.gz
│   ├── 78eed9eab771e03afc2931be86e30221a5e3ca4f.nq.gz
│   ├── 7deb8ab218129502f74cba47aa9e01d88333f58a.nq.gz
│   ├── 83ba05c89bfe33a88f3132d47439a3e76215e50c.nq.gz
│   ├── 969ce2a2e888f6811c0e2c2c7e745f1bf5307d5d.nq.gz
│   ├── a2d0d43343a5ef8d6a3a8a94b2bea69eb051c065.nq.gz
│   ├── bcfc3f7b0276f3e755527e08f3ffe0e44d0bd96d.nq.gz
│   ├── c029de3c0b7ea95fce92d955609395778459344f.nq.gz
│   ├── c2283c6beaaf01b50f4d699b303a30f1eb5968b6.nq.gz
│   ├── d7f6c548e773f71340c7912028465b432fa10c29.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e7292aa59219491d218d22b739699bf7b1adbe6d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4119603311b5ed158020aa345fa7363876282e42.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[holoviz/hvsampledata](https://github.com/holoviz/hvsampledata)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
