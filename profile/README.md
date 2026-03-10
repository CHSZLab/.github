<p align="center">
  <img src="https://raw.githubusercontent.com/CHSZLab/.github/main/logo/chszlab-banner.png" alt="CHSZLab" width="900"/>
</p>

We develop high-performance algorithms for combinatorial optimization problems on graphs at the [Algorithm Engineering Group, Heidelberg University](https://ae.ifi.uni-heidelberg.de/).

## CHSZLabLib

**[CHSZLabLib](https://github.com/CHSZLab/CHSZLabLib)** wraps our state-of-the-art C++ solvers into a single, easy-to-use Python package.

```bash
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
| Hypergraphs | [FREIGHT](https://github.com/KaHIP/FREIGHT), [HeiCut](https://github.com/HeiCut/HeiCut), [HyperMIS](https://github.com/KarlsruheMIS/HyperMIS), [HeiHGM](https://github.com/HeiHGM/Bmatching) |
| Independent Sets | [KaMIS](https://github.com/KarlsruheMIS/KaMIS), [CHILS](https://github.com/KarlsruheMIS/CHILS) |
| Process Mapping | [SharedMap](https://github.com/KaHIP/SharedMap) |
| Edge Orientation | [HeiOrient](https://github.com/HeiOrient/HeiOrient) |
| Dynamic Algorithms | [DynDeltaOrientation](https://github.com/DynGraphLab/DynDeltaOrientation), [DynMatch](https://github.com/DynGraphLab/DynMatch), [DynWMIS](https://github.com/DynGraphLab/DynWMIS) |

For full algorithmic control and peak performance, use the original C++ repositories directly.
