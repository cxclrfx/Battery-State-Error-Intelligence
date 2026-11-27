# External Numerical Validation — PyBaMM DFN

## Results

An external numerical comparison was performed using PyBaMM 26.11 DFN and matched physical inputs and current profiles. The proprietary solver implementation was not used in the external calculation.

| Model | Profiles | Samples | Maximum absolute discrepancy (mV) | RMSE (mV) |
|---|---:|---:|---:|---:|
| Stage 14, 12 modes | 15 | 3000 | 1.480725 | 0.327912 |
| Stage 15, corrected 12 modes | 5 | 1000 | 0.190984 | 0.077574 |
| 384-mode reference | 5 | 1000 | 0.190987 | 0.077575 |

## Corrected 12-mode model by profile

| Profile | Maximum discrepancy (mV) | RMSE (mV) |
|---|---:|---:|
| Constant current | 0.113389 | 0.103493 |
| Fast switching | 0.190984 | 0.106457 |
| Irregular current | 0.166609 | 0.057639 |
| Pulse and relaxation | 0.092826 | 0.034706 |
| Current reversal | 0.173569 | 0.059313 |

All five corrected-model profiles remain below 0.2 mV maximum discrepancy. The corrected compact model and the 384-mode reference exhibit nearly identical agreement with DFN.

## Method and scope

Electrolyte transport and reaction kinetics were aligned with the original model inputs. Saved DFN voltages were interpolated onto the original output times, and absolute discrepancies and RMSE were independently recomputed from the saved voltage records. The sine profile used a coarser DFN mesh due to memory limitations. A full mesh-convergence series has not yet been established.

These are inter-model numerical discrepancies, not physical-cell measurement errors or certified bounds relative to DFN. The source of the remaining discrepancy has not been isolated. Runtime, memory and internal-state comparisons are outside this report.

External platform: [PyBaMM](https://github.com/pybamm-team/PyBaMM).

Proprietary implementation and detailed computational configurations remain protected.
