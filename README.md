# Repolex Knowledge Graph of Textualize/pytest-textual-snapshot

RDF knowledge graph data for [Textualize/pytest-textual-snapshot](https://github.com/Textualize/pytest-textual-snapshot), parsed by [repolex](https://repolex.ai).

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
rlex download Textualize/pytest-textual-snapshot
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 893f812d44bbe37ddd4fc356d0d9dbb5725301b2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 893f812d44bbe37ddd4fc356d0d9dbb5725301b2
│           └── chunk-001.nq.gz
├── blob
│   ├── 003901d70317d763bc74290cd049d2bdd6c31078.nq.gz
│   ├── 44c5fd4cd6acf9018d7778edcbf41bd015666d63.nq.gz
│   ├── 5ac5d0ab2baf36c24223b4e6cd1fc668d2954c12.nq.gz
│   ├── 62ce991983e028c17228890a82447dcc151b31b7.nq.gz
│   ├── 66157b2e204155ae043dc8294568d233d7305713.nq.gz
│   ├── 75073b163019f057857d34b96b1688cc634ca329.nq.gz
│   └── a36204b95364a9322a9e2cbbc0f226cc20876a5a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 893f812d44bbe37ddd4fc356d0d9dbb5725301b2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[Textualize/pytest-textual-snapshot](https://github.com/Textualize/pytest-textual-snapshot)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
