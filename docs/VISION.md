# What a node is

A keyword knowledge graph stores `cat --near--> garden`.
The connection is a thin label. In a neural net the analogue is a weight.

This repository does not do that.

A node here is one complete algorithmic-design problem:

1. a symbol (today a LeetCode id; later a GitHub repo name)
2. an I/O contract
3. a reconstructed narrative (our words, not a scraped statement)
4. the knowledge you have to extract before you can design
5. the design steps, in order, with dependencies
6. the artifact that exists today (a file path) and the artifact that can exist later (a repo)
7. provenance: original / copied / mixed / unknown

The edge is a typed design pathway: `reduces-to`, `generalizes-to`, `same-invariant`, `reuses-operator`, `alternative-design`.
A number may hang on the edge as `confidence`. That number is metadata. It is not the meaning of the edge.

# Why this is not portfolio-knowledge-graph

`portfolio-knowledge-graph` already maps public original repos.
Its own README says catalogs are maps, not implementations.

This repo is the synthesis layer under that map.
Stage 1 (now): node = one design problem, artifact = a file in the 2021 dump or a 2023 discuss post.
Stage 2: one stable node gets its own GitHub repository. `node_type` flips to `github_repo`. The id does not change.
Stage 3: those repos become first-class nodes inside `portfolio-knowledge-graph`.

# Honesty

- The 2021 dump mixes original writes and copied tutorials. Copied files stay in the graph with `authorship=copied` or `mixed`. The useful object is still the design.
- LeetCode statements are not copied here. Reconstruction is from I/O shape, invariants, and the artifact we actually read.
- ProblemSolving is archived. Nothing in this repo writes into that archive.
- Eleven seed nodes is a slice, not the 1,845 AC list.

# HuggingFace-shaped export

`datasets/nodes.jsonl` is one node per line.
That is the synthesized dataset form: loadable, diffable, extendable.
It is not a trained model and it is not a weight matrix.
