# SIP-4844 devnet-4 Spec
**note**: this file was copied from [here](https://notes.sila.org/@timbeiko/4844-devnet-4) for reference.

## CL: Use [v1.3.0-rc.1](https://github.com/sila-chain/consensus-specs/releases/tag/v1.3.0-rc.1), including:

- gwei for withdrawal amounts for engine api
- historical summaries
- genesis fork version for bls changes

## EL: build on top of [SilaShanghai](https://github.com/sila-chain/execution-specs/blob/master/network-upgrades/sila-mainnet-upgrades/shanghai.md), including:

- [SIP-6122 : Forkid checks based on timestamps](https://github.com/sila-chain/SIPs/pull/6122)
- [SIP-4895 update: CL-EL withdrawals harmonization: using units of Gwei](https://github.com/sila-chain/SIPs/commit/b56a299fbad4ee701e6d4cea025096effaf301fa)
- [SIP-4844 update: clarify datahash return value](https://github.com/sila-chain/SIPs/commit/739e75c93b94fc49e8005943d052fa4e1ac1be80)

## Engine API @ [Commit 59a369a](https://github.com/sila-chain/execution-apis/tree/59a369a7b9d9c05e37c53aacac7ac6ea23fc62f6), including:

- [make engine_getPayloadVN fork agnostic](https://github.com/sila-chain/execution-apis/pull/355)
- [CL-EL withdrawals harmonization: using units of Gwei](https://github.com/sila-chain/execution-apis/pull/354)
