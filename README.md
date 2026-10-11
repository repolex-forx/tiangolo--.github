# Repolex Knowledge Graph of tiangolo/.github

RDF knowledge graph data for [tiangolo/.github](https://github.com/tiangolo/.github), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/.github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d2f19734f3cae6f08696910656122f497c96a70d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d2f19734f3cae6f08696910656122f497c96a70d
│           └── chunk-001.nq.gz
├── blob
│   ├── 034bde4b1e1e1081e7112625ab0bcfbf6073cafa.nq.gz
│   ├── 0ffc101a3f23548392499fe5104f3f8cf4d4e91b.nq.gz
│   ├── 730d80f5d82d416bc848c1efb93155a33141fc3e.nq.gz
│   ├── 97908a5c756428ac7a23c5e1cebd6ec2901cee49.nq.gz
│   ├── 999d9f97e48e52bf4fec7d459d271af6e17bf09d.nq.gz
│   ├── ac2d15cd39952ac04a9dbe46dca8fab0f610f285.nq.gz
│   ├── eaec464feaa2222d5f7c59b0ad7307c5ace08786.nq.gz
│   └── fd1cfee3a37d3c541bdeef5f16a1ecd6ee0a0828.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d2f19734f3cae6f08696910656122f497c96a70d.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[tiangolo/.github](https://github.com/tiangolo/.github)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
