<p align="center">
  <img src="https://raw.githubusercontent.com/CHSZLab/.github/main/logo/chszlab-banner.png" alt="CHSZLab" width="900"/>
</p>

We develop high-performance algorithms and open-source software for combinatorial optimization problems on graphs and hypergraphs at the [Algorithm Engineering Group, Heidelberg University](https://ae.ifi.uni-heidelberg.de/). Combinatorial optimization on (hyper)graphs addresses the challenge of finding the best solution among a vast, discrete set of possibilities defined by the structure of a network. These problems arise throughout science and engineering, from distributing workloads across processors and detecting communities in social networks to designing circuits and solving large sparse linear systems.

### Problems We Cover

**(Hyper)Graph Partitioning.**
Dividing a graph into k roughly equal-sized blocks while minimizing the edges between them. Our solvers range from multi-level methods with strong balance guarantees to streaming algorithms that partition graphs too large to fit in memory. We also cover node separators, nested dissection orderings, and process mapping (assigning communication tasks to hierarchical processor topologies).

**Graph Clustering.**
Detecting communities and dense substructures without a prescribed number of clusters. This includes modularity-maximizing evolutionary methods, correlation clustering on signed graphs, local triangle-motif-based clustering, and streaming approaches that cluster graphs in a single pass.

**Minimum & Maximum Cuts.**
Computing minimum cuts (both exact and heuristic) on graphs and hypergraphs, including parallel cactus-based algorithms that enumerate all minimum cuts. On the maximization side, FPT kernelization combined with heuristic and exact solvers for the NP-hard maximum cut problem.

**Independent Sets, Matching & Packing.**
Finding maximum (weight) independent sets on graphs and hypergraphs using reduction-based branch-and-bound, evolutionary algorithms, concurrent local search, and GNN-guided kernelization. We also cover hypergraph b-matching (offline and streaming) and maximum 2-packing sets.

**Edge Orientation.**
Orienting the edges of an undirected graph to minimize the maximum out-degree. Our algorithms include greedy 2-approximations, DFS-based local search, and eager path search methods.

**Dynamic Graph Algorithms.**
Maintaining solutions under incremental edge insertions and deletions. We provide fully dynamic algorithms for edge orientation, approximate edge orientation, maximum matching, and weighted maximum independent set, all designed for low amortized update cost.

## CHSZLabLib

**[CHSZLabLib](https://github.com/CHSZLab/CHSZLabLib)** wraps our state-of-the-art C++ solvers into a single, easy-to-use Python package.

```bash
python -m venv .venv && source .venv/bin/activate
pip install chszlablib
```

```python
from chszlablib import Graph, Decomposition

g = Graph.from_metis("network.graph")
result = Decomposition.partition(g, num_parts=8, mode="strong")
print(f"Edge cut: {result.edgecut}")
```

Covers graph partitioning, minimum/maximum cuts, community detection, independent sets, edge orientation, streaming algorithms, hypergraph problems, and fully dynamic graph algorithms.

### Integrated Libraries

| Domain | Libraries |
|:-------|:----------|
| Partitioning & Cuts | [KaHIP](https://github.com/KaHIP/KaHIP), [HeiStream](https://github.com/KaHIP/HeiStream), [VieCut](https://github.com/KaHIP/VieCut), [fpt-max-cut](https://github.com/KaHIP/fpt-max-cut) |
| Clustering | [VieClus](https://github.com/KaHIP/VieClus), [SCC](https://github.com/KaHIP/ScalableCorrelationClustering), [CluStRE](https://github.com/KaHIP/CluStRE), [HeidelbergMotifClustering](https://github.com/KaHIP/HeidelbergMotifClustering) |
| Hypergraphs | [FREIGHT](https://github.com/KaHIP/FREIGHT), [HeiCut](https://github.com/HeiCut/HeiCut), [HyperMIS](https://github.com/KarlsruheMIS/HyperMIS), [HeiHGM](https://github.com/HeiHGM/Bmatching), [HeiHGM-Streaming](https://github.com/HeiHGM/Streaming) |
| Independent Sets | [KaMIS](https://github.com/KarlsruheMIS/KaMIS), [CHILS](https://github.com/KarlsruheMIS/CHILS), [LearnAndReduce](https://github.com/KarlsruheMIS/LearnAndReduce), [red2pack](https://github.com/KarlsruheMIS/red2pack) |
| Process Mapping | [SharedMap](https://github.com/KaHIP/SharedMap) |
| Edge Orientation | [HeiOrient](https://github.com/HeiOrient/HeiOrient) |
| Dynamic Algorithms | [DynDeltaOrientation](https://github.com/DynGraphLab/DynDeltaOrientation), [DynDeltaApprox](https://github.com/DynGraphLab/DynDeltaApprox), [DynMatch](https://github.com/DynGraphLab/DynMatch), [DynWMIS](https://github.com/DynGraphLab/DynWMIS) |

For full algorithmic control and peak performance, use the original C++ repositories directly.

## Agentic Algorithm Engineering

**[AgenticAlgorithmEngineering](https://github.com/CHSZLab/AgenticAlgorithmEngineering)** defines a methodology for autonomous performance tuning via the Algorithm Engineering cycle. An AI agent iteratively designs, analyzes, implements, and experimentally evaluates code changes, driven by falsifiable hypotheses. Contributions welcome!
