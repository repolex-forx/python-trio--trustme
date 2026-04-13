# Repolex Knowledge Graph of python-trio/trustme

RDF knowledge graph data for [python-trio/trustme](https://github.com/python-trio/trustme), parsed by [repolex](https://repolex.ai).

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
lexq download python-trio/trustme
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6d39f51de72ce21bbb1d3842f8ed795b39e4cc9b
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 6d39f51de72ce21bbb1d3842f8ed795b39e4cc9b.nq.gz
│   └── repolex
│       └── 6d39f51de72ce21bbb1d3842f8ed795b39e4cc9b
│           └── chunk-001.nq.gz
├── blob
│   ├── 08f7ff742b09032f22f593f4b399fcfeac285773.nq.gz
│   ├── 0a153f128e63737bb5a8a0d1350fcec2c9e5bf75.nq.gz
│   ├── 0be2520b0e591cc9191c8cffc3a73b00b0bb2207.nq.gz
│   ├── 1040892281e96e9ea9f64ce6a72640053adfab3d.nq.gz
│   ├── 16216c85b08f3c97947619497ccd3578607102e3.nq.gz
│   ├── 3568b2c0a6a3f23607cd0aac6ac50e69194fbc03.nq.gz
│   ├── 437ac203f409fa3854a8df245e621c0fe43ba574.nq.gz
│   ├── 458a850458796f94fcf37b54e67f25fd372c36c4.nq.gz
│   ├── 47b3d219d0ce95766d6523c88af1fa2ec0c830e8.nq.gz
│   ├── 4ebe6b5377d7f6bb4b11c6063f31d2e5d190d7ec.nq.gz
│   ├── 5555fa4d898458dd2370a5358abcd620ded676ec.nq.gz
│   ├── 5fa2f81c34e093b7b461f6c88dc3ec49dcdd3970.nq.gz
│   ├── 68c806afcb607c5f7157de7b9af0f48da576d4ce.nq.gz
│   ├── 6ad0230287e202f0b3ca8371c9da193e8d08096b.nq.gz
│   ├── 714673b76282b26f96280c2f2b33e60cd5a0ed2f.nq.gz
│   ├── 78760e5bed2661b6d0fa621c760c60884ceaeed9.nq.gz
│   ├── 7a2aed25dabac193fb464801434e3756becb9a0a.nq.gz
│   ├── 81a7c3fd8e4e5242f98b0071134895ae22621def.nq.gz
│   ├── 84a45d40a953ae08d44cf84d7a27df3a894a6519.nq.gz
│   ├── 93275bc10410a64bd78211290a471f048553626e.nq.gz
│   ├── 97eaaa22b74c0c1eefcafbb49081bd640ed6c349.nq.gz
│   ├── 9b81d1de5ca8084af4d219bc8e4c6d7775d7c8e4.nq.gz
│   ├── 9c579d6be15ef724911e6a7c589a9b118bc83553.nq.gz
│   ├── a4ebcf75b56d51ed2aad57cd5977dcebabf682f8.nq.gz
│   ├── a71b7d942449a4e66a8d763ab3abc81ff245ee50.nq.gz
│   ├── a955fdae12bdf32b79296a3a6dd424aac3843677.nq.gz
│   ├── ab0bc4a7444a59b2e2ffe1b5fc018271d5d9a26b.nq.gz
│   ├── b38f1a56edac686f29b4e1c99c1fa8fe0f488f04.nq.gz
│   ├── b8bb97185926d7daed314609753173945ed4ff1a.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d66ee3dd13156f2807cc8e0222e23084a0010ecc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f0b73f8f18672260659f5556e0aa5f00a1905c4a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 6d39f51de72ce21bbb1d3842f8ed795b39e4cc9b.nq.gz
├── filetree
│   └── 6d39f51de72ce21bbb1d3842f8ed795b39e4cc9b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 43 files
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

[python-trio/trustme](https://github.com/python-trio/trustme)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
