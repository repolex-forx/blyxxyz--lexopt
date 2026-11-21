# Repolex Knowledge Graph of blyxxyz/lexopt

RDF knowledge graph data for [blyxxyz/lexopt](https://github.com/blyxxyz/lexopt), parsed by [repolex](https://repolex.ai).

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
rlex download blyxxyz/lexopt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f52c6a620b59dcadb01701c039cd4b270e2d5966
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f52c6a620b59dcadb01701c039cd4b270e2d5966.nq.gz
│   └── repolex
│       └── f52c6a620b59dcadb01701c039cd4b270e2d5966
│           └── chunk-001.nq.gz
├── blob
│   ├── 16eed15aeb9e98ab173ef5ca4455af23b6cda9a3.nq.gz
│   ├── 1be03a16fab03f6f0e0d20e9e1f5b833a1bbd754.nq.gz
│   ├── 2bfe5b2c900e234d7425db253beb859380d70b46.nq.gz
│   ├── 340ac0336244d43b32a5524d6e2bf3f9f40d4e1d.nq.gz
│   ├── 3d30690f120489337cb61685b2f0f0d45af983c1.nq.gz
│   ├── 3f0b1eb4fa5bc51bc3755b693a36f601f774f740.nq.gz
│   ├── 4c88279d327851dbb5d134224df8b8b1cca0bf45.nq.gz
│   ├── 572e03bdf321b6cc3a99488183436905cefd086d.nq.gz
│   ├── 5b81db6ccf097e65829e55fd69f0519146f46ec1.nq.gz
│   ├── 70fbaa9605ca64643a98864ae11ec2fc847bd45a.nq.gz
│   ├── 90ca1c081712a53ea553a5b8202f68aed9ab42d4.nq.gz
│   ├── 97b0f128d6712f327f312350a337a0339e80c490.nq.gz
│   ├── a901acf87da47ef2a267a05135fb7e9b09affe69.nq.gz
│   ├── aa294790b57f467514c4cb92ec126b69402dfa1c.nq.gz
│   ├── b398f55af3b5b47ecb79f121b6063e9686d90097.nq.gz
│   ├── b53eda13d7bc0dd11e91019b9824304c4b4ed60b.nq.gz
│   ├── c640ca5379ab68c6904db791c07e8d0c75f4e406.nq.gz
│   └── e1dd0c0439d30de9c2df332a4b2d9ac78d9e2c2d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f52c6a620b59dcadb01701c039cd4b270e2d5966.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 27 files
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

[blyxxyz/lexopt](https://github.com/blyxxyz/lexopt)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
