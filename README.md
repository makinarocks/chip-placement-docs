# Chip Placement
## Summary
- This documentation describes the chip placement results for Makinarocks.
- There are three netlists corresponding to difficulty: Easy, Medium and Hard.
    - In general, the number of cells corresponds to difficulty.

<center>

| Netlist | # of macros | # of std cells | # of nets |
|:---|---:|---:|---:|
|**Easy**|18|120k+|120k+|
|**Medium**|104|630k+|630k+|
|**Hard**|118|140k+|130k+|

</center>

- To reduce the calculation complexity, we clustersed standards cells to hundreds of clusters.
    
## Description
We provide the below data.
### `adj_mat.csv`
* Each column indicates `port`, `macros` and `standard cell clusters`.
* Row is equivalent to column.
### `{idx}_placement.png`
* Visualize floorplan result
### `{idx}_macro_placement.png`
* The coordinates(bottom_left) of all macros are described.
* Each line has the below format.
```bash
{macro index} {macro_width} {macro_height} {x_bottom_left} {y_bottom_left} {orientation}
```
### `{idx}_qor.png` & `{idx}_power.png`
* Timing report and the power report which are provided from commercial EDA Tool([ICC2]((https://www.synopsys.com/implementation-and-signoff/physical-implementation/ic-compiler.html)) by Synopsys).
* We employ the worst `Reg2Reg` negative slack to compare each placement quailty.
* We employ `Summary` value in the power report as the comparison factor.
