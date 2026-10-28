# Repolex Knowledge Graph of mne-tools/mne-incubator

RDF knowledge graph data for [mne-tools/mne-incubator](https://github.com/mne-tools/mne-incubator), parsed by [repolex](https://repolex.ai).

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
rlex download mne-tools/mne-incubator
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 744480276d8639bff3b29e045bf11f105f36c8ad
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 744480276d8639bff3b29e045bf11f105f36c8ad
│           └── chunk-001.nq.gz
├── blob
│   ├── 094b67df437e39a92011997e46f4eab68002cb9d.nq.gz
│   ├── 0f5bc735e77b793e0d30d9ee13e3d4e58c8dd35e.nq.gz
│   ├── 111aaed33607d90404a9f086c5cbb48faab961c5.nq.gz
│   ├── 19494f9263a6cdc16f16f07aa9dcc712d64d0a39.nq.gz
│   ├── 1ff324df83f9363648cfd23217a52f018f3b02f1.nq.gz
│   ├── 2913033cb50329b4c9a3a2e6b4ce80b8e023fd05.nq.gz
│   ├── 2a43082e5a2e39d8fc0d62360ff2c9f9ceb466f8.nq.gz
│   ├── 2c62abc8a5715874abce1dde154cb3daa9b47301.nq.gz
│   ├── 30f59838f37bca04a2d81419d2e22e47121e9f24.nq.gz
│   ├── 3c2c862283d5e3ccb1e4b09d9968da9d4ac0d40c.nq.gz
│   ├── 3ce9cf27ac0e396563b3388a161b3de7d7df10f6.nq.gz
│   ├── 417dc210c5906ee78e3abf41ca3bfd13df9567b6.nq.gz
│   ├── 51213d24ea8c1bb93b7ecc25a86f3b2cfdb84531.nq.gz
│   ├── 5bf13cf8f67c03f51c8c2266ef9e6113c2331473.nq.gz
│   ├── 5e9aadd365d190639399cdc7c9dbadb0618e2079.nq.gz
│   ├── 60bef7b60a3022f00426ca9745edb26ece1a24c2.nq.gz
│   ├── 66c2e337999833e800b2fdeadbd04f7af614d4e2.nq.gz
│   ├── 6b035f5f5610efa2bcc6236c4c4bea98c59814a4.nq.gz
│   ├── 709601962829e044ebd43e5a7403f36c3f780d6b.nq.gz
│   ├── 7aab3c1f2c1b84e3e1926c633da9caf9942469a8.nq.gz
│   ├── 8149e25f000b1b3cf00133d30711f9e3c953bcda.nq.gz
│   ├── 8a318a80895d4e40a7f647997e140b5ce693ec73.nq.gz
│   ├── c1d9216c7402c0cfcbe32cb36fe82458c83e98b3.nq.gz
│   ├── c626916034544ca40209386ea475292de8750150.nq.gz
│   ├── cde531ce2fcdaf59eff8ed2a9800f1521e933de1.nq.gz
│   ├── d71b9e9b6736697d9fc88b94bb85c2dc9ec20681.nq.gz
│   ├── db644da7963a8510b1ee117e33b50a64bd0a36bf.nq.gz
│   ├── ddb1db58a09d2b00868e688b8a895357eb9b3653.nq.gz
│   ├── e171e8a7b2787db9471869b28cee85a7c26542ef.nq.gz
│   ├── e1b23084bfb5a13738a53dc87181ef33524600ef.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7a34ed69e0898af43203bec3cc4471a38914710.nq.gz
│   └── f32220af3b0a100fca6d8fae0bdaf3f6eeb08985.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 744480276d8639bff3b29e045bf11f105f36c8ad.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[mne-tools/mne-incubator](https://github.com/mne-tools/mne-incubator)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
