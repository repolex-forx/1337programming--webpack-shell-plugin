# Repolex Knowledge Graph of 1337programming/webpack-shell-plugin

RDF knowledge graph data for [1337programming/webpack-shell-plugin](https://github.com/1337programming/webpack-shell-plugin), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download 1337programming/webpack-shell-plugin
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 99d0902cf30828110b1161ba15b2304bfecaa2d4
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 99d0902cf30828110b1161ba15b2304bfecaa2d4.nq.gz
│   └── repolex
│       └── 99d0902cf30828110b1161ba15b2304bfecaa2d4
│           └── chunk-001.nq.gz
├── blob
│   ├── 2e94e1a030d819857b1bfb10611a3f721cc953a8.nq.gz
│   ├── 4b66f4ca63d6634e1c3a0530cc618771373c1e6c.nq.gz
│   ├── 4db0c2c86ba5a74e5b84156fca9af91ea5caba61.nq.gz
│   ├── 7c787c613e95097084abf68182301d68277b62d3.nq.gz
│   └── 813fbdeaa200067f4b703c432c5e85bc11ca3e73.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 99d0902cf30828110b1161ba15b2304bfecaa2d4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 14 files
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

## Source repository

[1337programming/webpack-shell-plugin](https://github.com/1337programming/webpack-shell-plugin)

---
*Parsed on 2026-04-19 by [repolex](https://repolex.ai)*
