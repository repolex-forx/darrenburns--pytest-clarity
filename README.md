# Repolex Knowledge Graph of darrenburns/pytest-clarity

RDF knowledge graph data for [darrenburns/pytest-clarity](https://github.com/darrenburns/pytest-clarity), parsed by [repolex](https://repolex.ai).

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
rlex download darrenburns/pytest-clarity
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 533056491c6b4e18cce54286cdb3a692a0392780
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 533056491c6b4e18cce54286cdb3a692a0392780
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ab1cf12b345eb44e4c79bdb87075982c28ddec4.nq.gz
│   ├── 1ada606d9a0bed7cac56679b88708b516f8419a5.nq.gz
│   ├── 27ab4d45fb42ac18296fcaac11a3132d402cf71d.nq.gz
│   ├── 3800dd21a337b7430df7f5341ecff4ff5ce7cfad.nq.gz
│   ├── 4bb234219a6eb21bb07c1c2d9b7a4287ea5be3fd.nq.gz
│   ├── 67075d70a5271af629302bc2a5c16ed966cc2af0.nq.gz
│   ├── 6a743225262ab78b634e5b92b7997cd1b53b9505.nq.gz
│   ├── aabb4cbd10bf93ec6674ffe9de028ddd78b4dcc1.nq.gz
│   ├── ba6dacef60876b0a0e0b523ae7f6ad69866c421c.nq.gz
│   ├── bcfe01895d6b9b44b6854d08ac2a092eaaef1905.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── eb322f20fcfd6ef5d6622f70baa181711d0e28a8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 533056491c6b4e18cce54286cdb3a692a0392780.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[darrenburns/pytest-clarity](https://github.com/darrenburns/pytest-clarity)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
