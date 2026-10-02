# Repolex Knowledge Graph of NousResearch/hermes-plugin-blender

RDF knowledge graph data for [NousResearch/hermes-plugin-blender](https://github.com/NousResearch/hermes-plugin-blender), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-blender
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 8aab816ce6577eb792a256b51777cbb4cd6523f0
│   │   │   └── chunk-001.nq.gz
│   │   └── d1929b593bddd2241a8939fb355e0a69b8e077af
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   ├── 8aab816ce6577eb792a256b51777cbb4cd6523f0.nq.gz
│   │   └── d1929b593bddd2241a8939fb355e0a69b8e077af.nq.gz
│   └── repolex
│       ├── 8aab816ce6577eb792a256b51777cbb4cd6523f0
│       │   └── chunk-001.nq.gz
│       └── d1929b593bddd2241a8939fb355e0a69b8e077af
│           └── chunk-001.nq.gz
├── blob
│   ├── 08e0503273275173a787ef59306b872e55c35ac9.nq.gz
│   ├── 18ce4607b39114a0dda6ff93afa4ecdf38d1f1a1.nq.gz
│   ├── 1e42db3501d405ff4a3d6a698b54d07f9e2c14b6.nq.gz
│   ├── 2cd2f3857455522eb996b444136d220d4cd04e3d.nq.gz
│   ├── 456a8d3fa36a7f1c54a38a97f0703f37d3358f00.nq.gz
│   ├── 6e48260e4540f7fb4eb06b6c2834d0def2814f1e.nq.gz
│   ├── a680a585dee8a7beec62ee4eac7bac55759a0f3e.nq.gz
│   ├── b7a380d2c4089ca99ab4c7eafaee97ea52b27435.nq.gz
│   ├── e4be8fb1fd0262b555f7319c6b9c374262997cda.nq.gz
│   ├── ede8dfd3cba95b1141fb4ffc948bd61855d5322f.nq.gz
│   └── f1c72edb680143064fc2446ad985ab612e8eb7bb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   ├── 8aab816ce6577eb792a256b51777cbb4cd6523f0.nq.gz
│   └── d1929b593bddd2241a8939fb355e0a69b8e077af.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[NousResearch/hermes-plugin-blender](https://github.com/NousResearch/hermes-plugin-blender)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
