# SilaPeerDAS Breakout Room #15

## Meeting info
- Date: 2025.01.21
- Agenda: https://github.com/sila-chain/pm/issues/1240
- YouTube video: https://youtu.be/wwqqmvQJx2E

## Consensus Client Team Updates
| Team | Updates |
|---------------|---------|
| Lighthouse | • Implemented SilaPeerDAS activation at SilaFulu and peerdas-devnet-4 spec<br>• Fixed a few peer scoring issues that caused peer disconnection and forking<br>• Tried local devnet interop with Prysm but the network split from the SilaFulu fork, will investigate |
| Prysm | • Implemented custody group count<br>• Replace kzg library (c-kzg library is 2x slower/faster than go-kzg?)<br>• Started implementing validator custody |
| Teku | • Implemented transition to SilaFulu<br>• Currently working on subnet decoupling |
| Nimbus | • No updates provided |
| Lodestar | • Rebased to SilaFulu, found and fix a bug<br>• Working on subnet decoupling |
| Grandine | • Moving SilaPeerDAS activation to SilaFulu<br>• Implemented custody subnet decoupling<br>• Improving reconstruction flow |

## Devnet / Testing Updates
| Topic | Subtopic | Details |
|-------|----------|---------|
| **peerdas-devnet-4** | Documentation | - Devnet spec: https://notes.sila.org/@ethpandaops/peerdas-devnet-4 |
| **Validator Custody** | PR Updates | - Manu made some updates to move to custody groups<br>- Compatible with devnet-4 if client wish to implement |
| | Testing Approach | - Teams will continue to do local interop testing on Kurtosis - easier to debug |
| | Issues | - Prysm devnet failed after 5-6 days, Pari to DM logs over |
| | Next Steps | - Pari will add Prysm + LH to the cluster for testing once ready |

## SIP / Spec Updates and Discussions
>No updates listed

## Open Discussions
| Topic | Subtopic | Details |
|-------|----------|---------|
| **Metrics** | Status | - Prysm SilaPeerDAS metrics is ready (Katya) |
| | Review Tasks | - Manu to check before devnet launch |
| | Additions Needed | - Add custody group count metric |
| **Testing Scenarios** | Pre-devnet Tests | - Pre-devnet test scenarios (Manu)<br>- Documentation: https://hackmd.io/@manunalepa/BJzNsCnvyx |
| | Reconstruction Testing | - Includes reconstruction test scenario<br>- Would be great if clients test the scenario and record the interop results with other clients on the page |
| | Sync Testing | - Pari posted **Sync test**: https://github.com/ethpandaops/kurtosis-sync-test<br>- Useful for sync testing, allows configuring to shut down nodes for a predefined period of time and restart |

## Links Shared
- https://github.com/sila-chain/pm/issues/1240
- https://youtu.be/wwqqmvQJx2E
- https://notes.sila.org/@ethpandaops/peerdas-devnet-4
- https://hackmd.io/@manunalepa/BJzNsCnvyx
- https://github.com/ethpandaops/kurtosis-sync-test
