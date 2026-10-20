# Repolex Knowledge Graph of klen/muffin-prometheus

RDF knowledge graph data for [klen/muffin-prometheus](https://github.com/klen/muffin-prometheus), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-prometheus
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f21e86f944a9e55688b357baec76b77c7ec1a5fe
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f21e86f944a9e55688b357baec76b77c7ec1a5fe
│           └── chunk-001.nq.gz
├── blob
│   ├── 00b6bad5aef8952aeb61c230ca7c9457c18443d8.nq.gz
│   ├── 01916fa1ef38ff5bb56d66f0ee9287f16b47426c.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 2a0f9a13351f2da0843fb8b22b5b0056032e5e44.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 43d683a04e1d0b28840d5d57d3a28e6c12f6bfbf.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 4f245c703669bb9c59a05a1e8d19bf32096a2be9.nq.gz
│   ├── 5ce2ba731e747feeebc07e9804cfbd767665cecb.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 7bc8eb6443a48bf3021fc5379f5df8d869f9f9d5.nq.gz
│   ├── 87c8a02a2eb14be7da90be0b62b8da90d8bd057b.nq.gz
│   ├── a212d85837f56b13dced448d452daca01136abec.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── dc03fb0fe7677f18a9412cb36b5791a0bd8c6661.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f21e86f944a9e55688b357baec76b77c7ec1a5fe.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 28 files
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

[klen/muffin-prometheus](https://github.com/klen/muffin-prometheus)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
