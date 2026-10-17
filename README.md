# Repolex Knowledge Graph of karpathy/nanoGPT

RDF knowledge graph data for [karpathy/nanoGPT](https://github.com/karpathy/nanoGPT), parsed by [repolex](https://repolex.ai).

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
rlex download karpathy/nanoGPT
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3adf61e154c3fe3fca428ad6bc3818b27a3b8291
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3adf61e154c3fe3fca428ad6bc3818b27a3b8291
│           └── chunk-001.nq.gz
├── blob
│   ├── 09d574a5b8e6360af60ac17449ba8f01c1abf5e1.nq.gz
│   ├── 148a4c4fa314f489ecd5629653cc710abd2cd795.nq.gz
│   ├── 1bae34f9f1d752c4b13d9f8b428a104426818553.nq.gz
│   ├── 1e6c457d8ee51b7d254977631d28848ec5d83993.nq.gz
│   ├── 2a9b9752b7f4626c29cb02c83d33e591831ab1c8.nq.gz
│   ├── 329db5e33310fd5d98343e2bca690bfb07317526.nq.gz
│   ├── 41c81dfb4ea48523199e774ff1f309d9ab1a1181.nq.gz
│   ├── 43262add3ba64c68b3b211a4a8adad6d183cac50.nq.gz
│   ├── 4cbeaeff29e1be57088b0baa446899b750caf224.nq.gz
│   ├── 53978cb9e2408c9172d4b482afbd48784c3f8b27.nq.gz
│   ├── 67ef634ff4797037e72b2919c2af1fb33dbd4fe5.nq.gz
│   ├── 8f192732ac7a15b1696ca2f61bce7985e36efc37.nq.gz
│   ├── 946ea831dc721647126b76f20ed2d423a6a86106.nq.gz
│   ├── 95eb1bf386564769fb2b97f71fc0d69f448d2f7c.nq.gz
│   ├── 9d0db116d1b5876457b286e98d02c69f12d12899.nq.gz
│   ├── 9fd1621d55b2e0fd268ca1a79cf3b056ed23d16b.nq.gz
│   ├── a8bba9599537cbb34b378399a077b525a87d497f.nq.gz
│   ├── aa5d47dfc2d97b3907b5367c1ce2b5c2b3c21a36.nq.gz
│   ├── b2d461810955a6a601f9f743cf744215da557e27.nq.gz
│   ├── bda25b139f41f66ef95282337d21d820bc252636.nq.gz
│   ├── c698f8b60129d793494de058b0dd4e318c0dcb5e.nq.gz
│   ├── cc343fe0b324ad5d784d0c47bfa3d63f324b08db.nq.gz
│   ├── d25d6e0861388217c01c2f4284810ee39faa40a2.nq.gz
│   ├── d597b79cd3f1245292c3fdd89dd6ae5d00c96646.nq.gz
│   ├── de5785051050d64bbda37a4964c2c079f0739b2b.nq.gz
│   └── df5aac3c159f4b844ba0c1cd6b681c3ad60d0cc7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3adf61e154c3fe3fca428ad6bc3818b27a3b8291.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[karpathy/nanoGPT](https://github.com/karpathy/nanoGPT)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
