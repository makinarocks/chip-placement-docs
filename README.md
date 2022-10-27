# Chip Placement
---
- This documentation describes the chip placement results for Makinarocks.
- There are three netlists corresponding to difficulty: Easy, Medium and Hard.
    - In general, the number of cells corresponds to difficulty.
    
        ![image](./images/netlist.png)
- The result consists of adjacent matrix, floor planning and Quality of Routing (QoR).
    - [adj_mat]
        - Column sequntially indicates `port`, `macro` and `cluster`.
        - Row is equivalent to Column. 
    - [clustering]
        - For efficiency, it clusters standard cells. According to the number of standard cells, the number of clustering can be adjusted.
    - [QoR]
        - We use [ICC2](https://www.synopsys.com/implementation-and-signoff/physical-implementation/ic-compiler.html) as EDA tool
        - In EDA, it proceeds up to `route_opt`.
---
## Easy Netlist
- placement_map
- QoR: Timing metric and Power -> TNS / WNS / POWER
- port + macro + clustering adj map (excel)
