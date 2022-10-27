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
### A. `adj_mat.csv`
* Each column indicates `port`, `macros` and `standard cell clusters`.
* Row is equivalent to column.
### B. `{idx}_placement.png`
* Visualize floorplan result
### C. `{idx}_macro_placement.png`
* The coordinates(bottom_left) of all macros are described.
* Each line has the below format.
```bash
{macro index} {macro_width} {macro_height} {x_bottom_left} {y_bottom_left} {orientation}
```
### D. `{idx}_qor.png` & `{idx}_power.png`
* Timing report and the power report which are provided from commercial EDA Tool([ICC2]((https://www.synopsys.com/implementation-and-signoff/physical-implementation/ic-compiler.html)) by Synopsys).
* We employ the worst `Reg2Reg` negative slack to compare each placement quailty.
* We employ `Summary` value in the power report as the comparison factor.

## Contributions
### [공개 데이터 1] 소자 간 연결 데이터 (Description의 A에 해당)
* Macro및 Standard cell 간 연결 여부를 binary 데이터로 제공 (Excel 형태로 제공)
* Netlist를 그래프로 표현하는 방안으로, Neural network에 input 정보로 활용 가능
* 실험 위한 강화학습 환경 구성 시, Netlist를 그래프로 표현하는 시간을 단축하여 실험 환경 구성에 소요되는 시간 단축을 지원함
### [공개 데이터 2] Chip placement에 따른 PPA 결과 데이터 Set (Description의 B, C, D에 해당)
* 최적 배치 탐색 시간 절약 (다양한 분포의 배치), 후발 연구자(기관)의 신속한 실험 지원
* 다양한 배치를 사전에 확인할 수 있어 성능이 담보되는 배치에 대한 기준과 조건 수립을 지원 (초기 실험 단계의 시행착오 최소화 가능)
* 특히 초기 실험 단계에서 배치에 따른 PPA 결과를 확인할 수 있어, EDA Tool 기동 시간을 줄여줄 수 있으며
* 배치 결과 이미지를 통해 PPA 성과 관점의 좋은 배치의 패턴을 시각적으로 파악하는데 활용 가능
