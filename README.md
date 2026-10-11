# Repolex Knowledge Graph of pydantic/speedate

RDF knowledge graph data for [pydantic/speedate](https://github.com/pydantic/speedate), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/speedate
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a68ce8660d0488b82fade9cfc6b9665d0a30cf09
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a68ce8660d0488b82fade9cfc6b9665d0a30cf09
│           └── chunk-001.nq.gz
├── blob
│   ├── 0716871caabdbbb3e77a0371d49936cef1923ea1.nq.gz
│   ├── 0b55289a6236a9547e783664c174cd774d2a4132.nq.gz
│   ├── 0e9ab290e2721d00963d2c7bc2b9221857a91f4d.nq.gz
│   ├── 11d3d2f57b80b4131929d6db69b85f1145df0556.nq.gz
│   ├── 248ffc54d6a969197948dce6cd388711ecfaa4ec.nq.gz
│   ├── 2b7939818c8d7a94353e1b2c88f2bd0de3b9341e.nq.gz
│   ├── 2e384b697a09f03f632bbd72f074ba651717bd23.nq.gz
│   ├── 30dcf5e2bc4af5aba56332b65e824be9883cdf1c.nq.gz
│   ├── 347504ba8671430fe21b2c06a812afad7b77a2ca.nq.gz
│   ├── 360876d30eabb655adbc53af5e78c860297b50ba.nq.gz
│   ├── 39fc9225a2a0ae9e6854e0baffbf5b5b934be1c4.nq.gz
│   ├── 3b8a1accfc32225354489b8fe7c8a9a5e84d20e7.nq.gz
│   ├── 403f31a65d341dc9ff7f5bd74b55300a1b7cbfb7.nq.gz
│   ├── 455963f41782c79a8b56535770d474fc3decb00c.nq.gz
│   ├── 556d2e3d47c4ef25bdcfaffff6e2a884bb80271d.nq.gz
│   ├── 6b489673e17cd9d1e362acc9967e174cd2b71ce0.nq.gz
│   ├── 74edac0ca46d8aef358c8c9e89e0abe651fee2ae.nq.gz
│   ├── 75306517965a54731b94dca8bace640e856af115.nq.gz
│   ├── 873f8d2f0a87e7eef2787908a0e1a5f4ca18ad79.nq.gz
│   ├── 913c076cdf4767443de70b763fab56f19af997e8.nq.gz
│   ├── a0925114d619b8cee7d72961b052ddcc42023a24.nq.gz
│   ├── a23c98b37f61935ddb970103ed2f3557f8417f70.nq.gz
│   ├── b601056072127023904baf64ac909c90a9df5f30.nq.gz
│   ├── b7b5422d03815d74ccfdd28536cdd477de184153.nq.gz
│   ├── bb1abba4977c275e99a1518979ff23dc7f79a4d9.nq.gz
│   ├── c19ab545c1323ff4456b2658e0ad5146fa5c6923.nq.gz
│   ├── e43e7e6f83df4d6450aa8f19ad0833515056a8c7.nq.gz
│   ├── e77b54e3c80d5f1d92074d43bc373673ea94ad9a.nq.gz
│   ├── f44ebc44c48f94603a3372e40fa14e9f2c830f0a.nq.gz
│   ├── f834c215e54f9a07ae87b212ba3e09172d16f990.nq.gz
│   └── ff79299430c7ede5056e6035f5e10563d43d26e1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a68ce8660d0488b82fade9cfc6b9665d0a30cf09.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[pydantic/speedate](https://github.com/pydantic/speedate)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
