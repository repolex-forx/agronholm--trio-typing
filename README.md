# Repolex Knowledge Graph of agronholm/trio-typing

RDF knowledge graph data for [agronholm/trio-typing](https://github.com/agronholm/trio-typing), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/trio-typing
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2b182b7d7820104763657211840bac06506c9564
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2b182b7d7820104763657211840bac06506c9564
│           └── chunk-001.nq.gz
├── blob
│   ├── 104c402ebf17ef55f9cdca2114f0a4449f6dd039.nq.gz
│   ├── 173c048032c80b8fdbd5e79532b28ede661aaaa2.nq.gz
│   ├── 179b8738051ef973889c0f6bc3843b387116bdca.nq.gz
│   ├── 18e13053ffaa425ad53a1f477b0d04eccf96df0c.nq.gz
│   ├── 1a7a2c0d69568d37f80a2afd2f3887c7422a43b5.nq.gz
│   ├── 2173795f56ededd08284c207515b510feee94997.nq.gz
│   ├── 393deb4e98f84814c557f1190fdef5aa0bce356c.nq.gz
│   ├── 51f3442917839f8e0f0cccb52b3c10968ad0779e.nq.gz
│   ├── 54049ef94abf207ac32fce7d743061317862df3b.nq.gz
│   ├── 555e03c6e87b38372bf775c631daea83ab8beb1f.nq.gz
│   ├── 5841d55ca4653485068291fefcdd28a0ae15ad54.nq.gz
│   ├── 5d98063257ed0757771c39a4c7c68b17dab1aa03.nq.gz
│   ├── 5f4fdcdc949bb73a6b7e36f5138c3324ae64f3b7.nq.gz
│   ├── 60febc40bdd6561d1a6bfb22c8c5ac80434ab770.nq.gz
│   ├── 7bf9b761f7debc2e7d476750b80d29fe4f5dde52.nq.gz
│   ├── 7d710a41f46ef50fabea3e14c47800b42857a2ea.nq.gz
│   ├── 80ed00e67216adca089a7a4466116944d59b920f.nq.gz
│   ├── 8bc335e01944f920aef91696deab3a4e64b92987.nq.gz
│   ├── 9a9e002b037993f63cd8a34f6d89fb111e07fd2c.nq.gz
│   ├── a149830562ce59e831505595debab54fc66885e2.nq.gz
│   ├── ae1086409cbfaf96503e42bf50fdef82938e4608.nq.gz
│   ├── b6225824b589cf0ebbe7b4e83a730f7c4283f02b.nq.gz
│   ├── b73f39c1741ddc3c8f177b4325e3037494e2b2c1.nq.gz
│   ├── b7f2434b084b520967d03c0d0f89f7980f362f9b.nq.gz
│   ├── b8bb97185926d7daed314609753173945ed4ff1a.nq.gz
│   ├── bebfb75fbef38be9588871522322d601bcde631a.nq.gz
│   ├── c7046c5e45dc150d6c3fab087ef4744b7fdf73aa.nq.gz
│   ├── d08a2532fdb9fd1323d9f88d48733029bc173921.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d84dda8209f17155c12f156f457b6add16d50836.nq.gz
│   ├── ddba9056a8ffd6183294ed1dfa2619b0046e75ee.nq.gz
│   ├── e45f52e14ca122d36e485d846aa399244e5b64f4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb193545173ca7889b606f9fb94e4966899f0d81.nq.gz
│   ├── f38c5167733eb2fd1cb677450f876788a4aa603e.nq.gz
│   └── ff0fb6b94e9972a18564f36df546cb5ec1b8830f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2b182b7d7820104763657211840bac06506c9564.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 42 files
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

[agronholm/trio-typing](https://github.com/agronholm/trio-typing)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
