# Repolex Knowledge Graph of scrapinghub/varanus

RDF knowledge graph data for [scrapinghub/varanus](https://github.com/scrapinghub/varanus), parsed by [repolex](https://repolex.ai).

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
rlex download scrapinghub/varanus
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 383ef738515d62dae6aff53c7f3036ac3abde83e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 383ef738515d62dae6aff53c7f3036ac3abde83e
│           └── chunk-001.nq.gz
├── blob
│   ├── 078d071114bf7427efb3cdfb6a21f3346f779cec.nq.gz
│   ├── 0ca88ba237c9f2e9e70ed57bf02fc032645ea667.nq.gz
│   ├── 0d4877e78b3febd6c6b46302e7a99dd82516e94e.nq.gz
│   ├── 14d7ff52f45ab88a5bb326f864c0054fe0bc7394.nq.gz
│   ├── 1520f763778cc76b8e614fc9eb2af7e6f7215c6a.nq.gz
│   ├── 275fbbd40be2045b2672e63445b61362c8592116.nq.gz
│   ├── 484c5172ca86ac2b3fa1f00dbc297b04d46b9099.nq.gz
│   ├── 4f015f1f5e5f4b9e3861456a837e6ab2028b067b.nq.gz
│   ├── 56fcb918919380afcb0064b864342d4103cff2c1.nq.gz
│   ├── 6341fe106dc687e7839771a80a948f7bc41ca5b7.nq.gz
│   ├── 69b2962364091ee058da8e77903638810208b2ed.nq.gz
│   ├── 73be395feb5368cef6d371a1f6cc66f44b17ef7e.nq.gz
│   ├── 778330a450bffdb1f43dad939f7c0e1b4f279565.nq.gz
│   ├── 83df94f11c8b28595604a73fdfe5026e9a8183c0.nq.gz
│   ├── 87d675b583d1a265e2c9057cc13262710b9618cf.nq.gz
│   ├── 8cf15cc23fede3013e245afbb34f9e068d64105f.nq.gz
│   ├── 96b29f24bf0c4203cf7f89c2c5ee49574368f534.nq.gz
│   ├── a65d740390bcdfa493d972a46130295aa28e24b6.nq.gz
│   ├── a6af9e0f49f26e63fe943a9751eb5f014d17d44f.nq.gz
│   ├── aef1c3a23c7383401983904cc1d740012656b99c.nq.gz
│   ├── b802ae5acc59036077d6aaf7036ea933cc0038b9.nq.gz
│   ├── bf55e5df653243ad74a4cea49ecba78db0499eb1.nq.gz
│   ├── c926ee8a2e2d6a686154bfa2e49aea97eed0c51a.nq.gz
│   ├── cb25952684185579f890f1b73e34e171d1e347bd.nq.gz
│   ├── d2ee58b9ff2c03976ef759250bfc9c9908a8dabf.nq.gz
│   ├── d7204ed9a84a3456f912fbe083c1920290d0866e.nq.gz
│   ├── d7512e42dba4b520f13b7a5fd26cc428529a37a5.nq.gz
│   ├── e0261aad03fc444e74954c76d6e80d351418c399.nq.gz
│   ├── e26e8381f9839eb38fb98f532872151f8e7c8eca.nq.gz
│   ├── e38b2e760de8a2145f3bbc7b1507947bf4b0ea9b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e96e1ae2c5bea235e857f44f6b83b717bf815120.nq.gz
│   ├── edff38fcc263cdb228f2045660f36e5e3dae03e2.nq.gz
│   ├── f151c29b27873b5efd94472dbf22bb33eb969ec4.nq.gz
│   ├── f162321a2fb69862429fc56a9dc3280d1b524e57.nq.gz
│   ├── f6f307dca85cc855601ca8a84289c98091a68913.nq.gz
│   ├── fb8c2f170d9ae1ba73b79ddfc1ff62169c6c163a.nq.gz
│   └── fe2268cfabf9ff6e655d40c435090a10f576f650.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 383ef738515d62dae6aff53c7f3036ac3abde83e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[scrapinghub/varanus](https://github.com/scrapinghub/varanus)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
