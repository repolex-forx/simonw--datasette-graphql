# Repolex Knowledge Graph of simonw/datasette-graphql

RDF knowledge graph data for [simonw/datasette-graphql](https://github.com/simonw/datasette-graphql), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-graphql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 587ebdd6a0c5998f61993ca01a130f54d229c05f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 587ebdd6a0c5998f61993ca01a130f54d229c05f
│           └── chunk-001.nq.gz
├── blob
│   ├── 05101a37427db4f255ff99921bbe0109684fadc6.nq.gz
│   ├── 065d576ff1b402fffbc6ff1a81c90bb0bbd2b0d0.nq.gz
│   ├── 08e3c29e6ba1081d83431a604a0ac3676e26abb2.nq.gz
│   ├── 0a50cf52b39a8a5d6320219d56344407276fbe3d.nq.gz
│   ├── 0fd1c23d3e806dba471999ea81298a646f1166a2.nq.gz
│   ├── 117d99ad9335561c6f6dd12a25d2a6a5acff82e3.nq.gz
│   ├── 1cb6f5b1b45e81c6b7d8c163c11d5026faea7dde.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 26b1e57f44fb97f37e3b29860d335b83d2d07c45.nq.gz
│   ├── 338b0e2e6607bfc66b41c3cc5c08d7529974c43c.nq.gz
│   ├── 39c90280c84ba9f3f8158240b7fe901661c1d718.nq.gz
│   ├── 3d006520b68baae13079655c016408c198567751.nq.gz
│   ├── 419c38048a74196b73e87537c59969eff5fb0414.nq.gz
│   ├── 4d0f767bc7bbc07d716eb41a36c06fcaf2d86a55.nq.gz
│   ├── 4d981c709dee1471ec9f333add0ee0fbb0e2c523.nq.gz
│   ├── 4eefb8138f3198107dbd230c6e0f2e3e612e870a.nq.gz
│   ├── 4efb1762b3723d263b08001b48567640ff9a76bf.nq.gz
│   ├── 501408391bb4dea32ea547449009509dc35641b6.nq.gz
│   ├── 5445ff5f27eeb50b8b291742166b91ccbed5d22f.nq.gz
│   ├── 641c4b55d03cd3ba3f2184b0a448b173766dcd7e.nq.gz
│   ├── 86c15605de2812638d0b01c278d7f0702dafd5ac.nq.gz
│   ├── 8e5c151c001efca5dd0f64aa3ed060b8e4c79c35.nq.gz
│   ├── 917f6daeb925c60a1320d9176eeaaa040ebf4367.nq.gz
│   ├── 91d72429150dd7a09531741409736ac7f5102f72.nq.gz
│   ├── a1e50534cf363bacab36ccae61327438a8272835.nq.gz
│   ├── b4c8638721d4069ec19debc154cca8b3682cdb0e.nq.gz
│   ├── c0b5043acb678d9c38f0cc64548056c752587e52.nq.gz
│   ├── c8c423c47f7701a58b8cf76c0a10de6cc4943976.nq.gz
│   ├── d3f49028c79fe673f6829438cc5e0d2a32ddbff7.nq.gz
│   ├── e26fc46c58bf1ee8ae8fbcd631747b58107f530e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f17c1fc40922627b520bddafeea4751c6bb561bf.nq.gz
│   ├── f3e7bee62b10679d42e98388445ee886fbbbd790.nq.gz
│   ├── f6f8489ee2f30229743f8eb03a0a146ca61e3b0a.nq.gz
│   ├── f7eabf358dbb093ad7a5502d2a273780c86b1c96.nq.gz
│   ├── f850477ebded57c33f766f5d0e2f8beecde0eb95.nq.gz
│   ├── fe5bfd9a61157fe6d0cca0d15f6070d3b5e321fb.nq.gz
│   └── fe6ed477ff00470436728a686364ea75bb12c6f1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 587ebdd6a0c5998f61993ca01a130f54d229c05f.nq.gz
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

[simonw/datasette-graphql](https://github.com/simonw/datasette-graphql)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
