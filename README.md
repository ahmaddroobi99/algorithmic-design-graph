# algorithmic-design-graph

Synthesized knowledge graph for Ahmad Droobi's algorithm practice.

**A node is not a keyword.**  
A node is one complete algorithmic-design problem: symbol, I/O contract, reconstructed narrative, extracted knowledge, step-by-step design, artifact, provenance.

**An edge is not a weight.**  
An edge is a typed design pathway (`reduces-to`, `generalizes-to`, `same-invariant`, `reuses-operator`, `alternative-design`). `confidence` is optional metadata.

Later the same node type can wrap a GitHub repository. Today the artifact is a file in the archived 2021 dump or a 2023 LeetCode discuss post.

Open [index.html](index.html) to walk the seed graph.

This is the synthesis layer. The account map lives in [portfolio-knowledge-graph](https://github.com/ahmaddroobi99/portfolio-knowledge-graph). The raw practice dump stays archived at [ProblemSolving](https://github.com/ahmaddroobi99/ProblemSolving). Catalogs are maps. This repo is not a second dump.

## Seed (11 design nodes)

| id | family | authorship |
|---|---|---|
| [42 Trapping Rain Water](data/nodes/lc-0042-trapping-rain-water.json) | bounded volume from extrema | original |
| [84 Largest Rectangle in Histogram](data/nodes/lc-0084-largest-rectangle-in-histogram.json) | nearest smaller element | original |
| [85 Maximal Rectangle](data/nodes/lc-0085-maximal-rectangle.json) | nearest smaller element | unknown (empty stub) |
| [76 Minimum Window Substring](data/nodes/lc-0076-minimum-window-substring.json) | minimum cover window | mixed |
| [743 Network Delay Time](data/nodes/lc-0743-network-delay-time.json) | Dijkstra | mixed |
| [1584 Min Cost to Connect All Points](data/nodes/lc-1584-min-cost-connect-points.json) | Prim MST | mixed |
| [847 Shortest Path Visiting All Nodes](data/nodes/lc-0847-shortest-path-visiting-all-nodes.json) | bitmask BFS | original |
| [1192 Critical Connections](data/nodes/lc-1192-critical-connections.json) | Tarjan bridges | original |
| [2360 Longest Cycle in a Graph](data/nodes/lc-2360-longest-cycle-in-a-graph.json) | functional graph | original (2023 post) |
| [312 Burst Balloons](data/nodes/lc-0312-burst-balloons.json) | interval DP last-action | mixed |
| [315 Count of Smaller After Self](data/nodes/lc-0315-count-of-smaller-numbers-after-self.json) | merge-sort census | unknown |

Copied / tutorial-shaped files stay in the graph. They are flagged. The useful object is the reconstructed design, not a claim that every line was invented in 2021.

## Layout

```
schema/node.schema.json      # what a node is allowed to be
schema/edge.schema.json      # typed pathways, not weights
data/nodes/*.json            # one design problem each
data/edges.jsonl             # design relations
data/categories.json         # labels only — categories are not nodes
datasets/nodes.jsonl         # HuggingFace-shaped export
docs/VISION.md               # node ontology and honesty rules
index.html                   # local graph walker
```

## Pipeline

1. Inventory an artifact (dump file or discuss post). Record authorship.
2. Reconstruct I/O + invariant + design from the artifact. Do not paste platform statements.
3. Write one JSON node. Point `artifact.path` back at the source file.
4. Add typed edges only when a real design move is shared.
5. Emit `datasets/nodes.jsonl`.
6. When a node is stable, promote it to its own repo and set `node_type` to `github_repo`.

## Honest limits

- Eleven nodes, not 1,845 ACs and not 191 Hards.
- ProblemSolving is archived. This repo does not rewrite it.
- No LeetCode editorial text.
- No trained embeddings. No neural weights.
- Empty or unread files are `unknown`, not silently treated as original.

## License

MIT.
