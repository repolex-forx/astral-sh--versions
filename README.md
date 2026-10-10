# Repolex Knowledge Graph of astral-sh/versions

RDF knowledge graph data for [astral-sh/versions](https://github.com/astral-sh/versions), parsed by [repolex](https://repolex.ai).

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
rlex download astral-sh/versions
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f3d2855b41fb545a4263b67e450c0c20dba734af
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f3d2855b41fb545a4263b67e450c0c20dba734af
│           └── chunk-001.nq.gz
├── blob
│   ├── 023f34a186d76a7b822c092ae669565210bb3ba9.nq.gz
│   ├── 21a2a5c34ab1d25ff16615b25a2e4aa81f129078.nq.gz
│   ├── 3571788df76c0ea95181fb4dd2ab416e58dbbf01.nq.gz
│   ├── 457dc9a324d9fe3817f04ce0a3ad16e1dfe8cc97.nq.gz
│   ├── 8f7b6a337b96108561717de3682194352dcbaf2c.nq.gz
│   ├── 92218615d13717978e843968a246b8a64266b53b.nq.gz
│   ├── 9a5fd105685d6b7c9391b41194e653f4b1ee6f55.nq.gz
│   ├── b2e5fc58e164a357489cd8b3d72c43b2bd7ad139.nq.gz
│   ├── ba22cf8a11d7cb3651574cad7d63555f0187008b.nq.gz
│   ├── bce21cf25ef37fbf307c2fb3a88c9e985b9817ae.nq.gz
│   ├── bd4294892066be59a1dd038d1b9ac9a517cc312c.nq.gz
│   ├── d11a9516310ac816d59b7a26fcfd641a4ead4be3.nq.gz
│   └── ffcf690d6e562c123eb90db2ea1f4956aa6f02fa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f3d2855b41fb545a4263b67e450c0c20dba734af.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[astral-sh/versions](https://github.com/astral-sh/versions)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
