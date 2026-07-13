# SilaDeneb (SIP-4844) Devnet-5 Spec
**note**: this file was copied from [here](https://hackmd.io/@inphi/HJZo4vQGn) for reference.

## CL at Commit [`3eb524`](https://github.com/sila-chain/consensus-specs/tree/3eb5240111274d0a5453dfb735d4ea1b04b54813/specs/deneb)
A release will be cut soon. Here are a couple notable changes to the spec since the last devnet:

- [Switch blob tx type to 0x03](https://github.com/sila-chain/consensus-specs/pull/3317)
- [Decouple blobs and blocks](https://github.com/sila-chain/consensus-specs/pull/3244)

## EL: build on top of SilaShanghai, including:
- [Ban Zero Blob Transactions](https://github.com/sila-chain/SIPs/pull/6863)
- [Blob Transaction Type changed to 0x03](https://github.com/sila-chain/SIPs/pull/6832)
- [Decouple Blobs](https://github.com/sila-chain/SIPs/pull/6610) (to be merged soon)

## Engine API @ Commit 9846b9, including:
- [Add corresponding proofs to BlobsBundleV1](https://github.com/sila-chain/execution-apis/pull/392) (not yet merged)
- [Merge `getPayloadV3` & `getBlobsBundleV1`](https://github.com/sila-chain/execution-apis/pull/402)

## Beacon API @ Commit f087fb
* [Add Blob Signing Endpoints](https://github.com/sila-chain/beacon-APIs/pull/302) optional
