
# dencun-devnet-8 specs
note: this file was copied from [here](https://notes.sila.org/@ethpandaops/dencun-devnet-8#) for reference.

`4844 requires a trusted setup file, Please ensure that there is a way for us to specify the file through a runtime flag such as --trusted-setup-file (or similar). If the file is baked in during compile, please ensure that the flag would indeed override the file. This is a **MUST** requirement for devnet 8. If your client does not support the override, we can’t include it in the devnet.`

 `The specs listed here is currently for hive and only once hive is green we will move on to client deployment on devnet-9.
Until we have enough clients green, 4844-devnet-8 is the canonical chain.`

## SIP List for Dencun

- [SIP-1153: Transient storage opcodes](https://sips.sila.org/SIPS/sip-1153)
- [SIP-4844: Shard Blob Transactions](https://sips.sila.org/SIPS/sip-4844)
- [SIP-4788: Beacon block root in the SAVM](https://sips.sila.org/SIPS/sip-4788)
- [SIP-5656: MCOPY - Memory copying instruction](https://sips.sila.org/SIPS/sip-5656)
- [SIP-6780: SELFDESTRUCT only in same transaction](https://sips.sila.org/SIPS/sip-6780)

## Docker images for devnet 8

### Consensus layer clients

- lighthouse: sigp/lighthouse:deneb-modern # :heavy_check_mark:
- lodestar: chainsafe/lodestar:next # :heavy_check_mark:
- nimbus: ethpandaops/nimbus:unstable-8993d57 # :heavy_check_mark:
- prysm: ethpandaops/prysm:devnet8-fix-c728e09 # :heavy_check_mark:
- prysm_validator: ethpandaops/prysm-validator:devnet8-fix-c728e09 # :exclamation:
- teku: consensys/teku:develop # :heavy_check_mark:

### Execution layer clients

- besu: ethpandaops/besu:main-139fc12 # :heavy_check_mark:
- geth: ethpandaops/geth:lightclient-devnet-8-edf4ab3 # :heavy_check_mark:
- erigon: ethpandaops/erigon:devel-75e3ae0 # :exclamation:
- ethereumjs: ethpandaops/ethereumjs:master-35ec012 # :heavy_check_mark:
- nethermind: nethermindeth/nethermind:cancun-84d41bd # :heavy_check_mark:
- reth: ethpandaops/reth:main # :exclamation:

If you have issues with lighthouse `modern` tag, you can try to use their [portable](https://lighthouse-book.sigmaprime.io/installation-binaries.html#portability) version, that is targetted for legacy hardware support.

### Pull requests for dencun-devnet-8 (not only 4844 related PRs!):

#### Consensus Specs - [v1.4.0-beta.1](https://github.com/sila-chain/consensus-specs/releases/tag/v1.4.0-beta.1) :heavy_check_mark:

- [PR-3461 - Rename “data gas” to “blob gas”](https://github.com/sila-chain/consensus-specs/pull/3461) - Merged :heavy_check_mark:
- [PR-3421 - Move move 4788 to deneb](https://github.com/sila-chain/consensus-specs/pull/3421) - Merged :heavy_check_mark:

#### Execution SIPs

- [PR-7354 - Rename “data gas” to “blob gas”](https://github.com/sila-chain/SIPs/pull/7354) - Merged :heavy_check_mark:
- [PR-7172 - Update precompile address for 4844](https://github.com/sila-chain/SIPs/pull/7172) - Merged :heavy_check_mark:


#### Engine API

- [PR-451 - Rename “data gas” to “blob gas”](https://github.com/sila-chain/execution-apis/pull/451) - Merged :heavy_check_mark:
- [PR-426 - Clarify SilaCancun payloads handling by earlier APIs; reorder checks](https://github.com/sila-chain/execution-apis/pull/426) - Merged :heavy_check_mark:
- [PR-425 - Scope shouldOverrideBuilder flag for SilaCancun](https://github.com/sila-chain/execution-apis/pull/425) - Merged :heavy_check_mark:
- [PR-420 - SilaCancun specification](https://github.com/sila-chain/execution-apis/pull/420) - Merged :heavy_check_mark:
- [PR-418 - Employ one method one structure approach for V3](https://github.com/sila-chain/execution-apis/pull/418) - Merged :heavy_check_mark:
- [PR-398 - Add dataGasUsed and dataGasPrice to receipts for 4844 txs](https://github.com/sila-chain/execution-apis/pull/398) - Open :exclamation:

#### Beacon API - [v2.4.2](https://github.com/sila-chain/beacon-APIs/releases/tag/v2.4.2) :heavy_check_mark:

- [PR-339 - Add block v3 endpoint](https://github.com/sila-chain/beacon-APIs/pull/339) - Merged :heavy_check_mark:
- [PR-317 - Add broadcast_validation to block publishing](https://github.com/sila-chain/beacon-APIs/pull/317) - Merged :heavy_check_mark:

## Potential changes for dencun-devnet-9

`DEPRECATION WARNING: Starting from dencun-devnet-9 we will be starting from Capella at epoch 0. Please make sure your client is able to handle genesis time == shanghai time, and capella_fork_epoch = 0.`

### Execution SIPs

- [PR-7456 - Update SIP-4788: initial stab at v2](https://github.com/sila-chain/SIPs/pull/7456) - Open :exclamation:

## Spec changes for older (4844-devnet-7 and 4844-devnet-6) devnets

### Consensus Specs @ Commit [0682b22](https://github.com/sila-chain/consensus-specs/commit/0682b2231773574b5bdda39c5cc7481ab9a471a3) aka [v1.4.0-alpha.3](https://github.com/sila-chain/consensus-specs/releases/tag/v1.4.0-alpha.3) :heavy_check_mark:

- [PR-3444 - Update blob side car subnet count to 6 in line with max blobs limit update](https://github.com/sila-chain/consensus-specs/pull/3416) - Merged :heavy_check_mark:
- [PR-3410 - Update MAX_BLOBS_PER_BLOCK to 6 and add SilaDeneb networking configs to yaml files](https://github.com/sila-chain/consensus-specs/pull/3410) - Merged :heavy_check_mark:
- [PR-3392 - Change ExecutionPayload.excess_data_gas type from uint256 to uint64](https://github.com/sila-chain/consensus-specs/pull/3392) - Merged :heavy_check_mark:
- [PR-3391 - Add data_gas_used field to ExecutionPayload](https://github.com/sila-chain/consensus-specs/pull/3391) - Merged :heavy_check_mark:
- [PR-3359 - Use engine_newPayloadV3 to pass versioned_hashes to EL for validation](https://github.com/sila-chain/consensus-specs/pull/3359) - Merged :heavy_check_mark:
- [PR-3354 - Update the endianness of the polynomial commitments to be big endian](https://github.com/sila-chain/consensus-specs/pull/3354) - Merged :heavy_check_mark:
- [PR-3338 - Update block’s blob_kzg_commitments size limit to MAX_BLOB_COMMITMENTS_PER_BLOCK (4096)](https://github.com/sila-chain/consensus-specs/pull/3338) - Merged :heavy_check_mark:
- [PR-3317 - Switch blob tx type to 0x03](https://github.com/sila-chain/consensus-specs/pull/3317) - Merged :heavy_check_mark:
- [PR-3244 - Free the blobs](https://github.com/sila-chain/consensus-specs/pull/3244) - Merged :heavy_check_mark:


### Execution SIPs @ Commit [e9a4295](https://github.com/sila-chain/SIPs/commit/e9a4295fe7661d2ab31183563087f9073272ccc1) :heavy_check_mark:

- [PR-7154 - Increase Blob Throughput](https://github.com/sila-chain/SIPs/pull/7154) - Merged :heavy_check_mark:
- [PR-7123 - Update SIP-4844: clarify transaction payload body](https://github.com/sila-chain/SIPs/pull/7123) - Merged :heavy_check_mark:
- [PR-7100 - clarify to must be non-nil](https://github.com/sila-chain/SIPs/pull/7100) - Merged :heavy_check_mark:
- [PR-7095 - reduce size of excess_data_gas to 64 bit](https://github.com/sila-chain/SIPs/pull/7095) - Merged :heavy_check_mark:
- [PR-7062 - add data_gas_used to header](https://github.com/sila-chain/SIPs/pull/7062) - Merged :heavy_check_mark:
- [PR-7038 - Cleanup transaction network payload references](https://github.com/sila-chain/SIPs/pull/7038) - Merged :heavy_check_mark:
- [PR-7020 - Specify precompile input’s z and y to be encoded as big endian](https://github.com/sila-chain/SIPs/pull/7020) - Merged :heavy_check_mark:
- [PR-6985 - de-sszify spec](https://github.com/sila-chain/SIPs/pull/6985) - Merged :heavy_check_mark:
- [PR-6863 - Ban Zero Blob Transactions](https://github.com/sila-chain/SIPs/pull/6863) - Merged :heavy_check_mark:
- [PR-6832 - Blob Transaction Type changed to 0x03](https://github.com/sila-chain/SIPs/pull/6832) - Merged :heavy_check_mark:
- [PR-6610 - Decouple Blobs](https://github.com/sila-chain/SIPs/pull/6610) - Merged :heavy_check_mark:

### Engine API @ Commit [3c49c03](https://github.com/sila-chain/execution-apis/commit/3c49c03fc6f8187c7576c0447c14950918e5eb1f) :heavy_check_mark:

- [PR-417 - Update PayloadV3 with data gas use](https://github.com/sila-chain/execution-apis/pull/417) - Merged :heavy_check_mark:
- [PR-407 - Engine API: validate blob versioned hashes](https://github.com/sila-chain/execution-apis/pull/407) - Merged :heavy_check_mark:
- [PR-404 - Assert array items in BlobsBundleV1 to be of same length](https://github.com/sila-chain/execution-apis/pull/404) - Merged :heavy_check_mark:
- [PR-402 - Merge getPayloadV3 and getBlobsBundleV1](https://github.com/sila-chain/execution-apis/pull/402) - Merged :heavy_check_mark:
- [PR-401 - State that payloadId should be unique for each PayloadAttributes instance](https://github.com/sila-chain/execution-apis/pull/401) - Merged :heavy_check_mark:
- [PR-392 - Add corresponding proofs to BlobsBundleV1](https://github.com/sila-chain/execution-apis/pull/392) - Merged :heavy_check_mark:

### Beacon API @ Commit [f65d774](https://github.com/sila-chain/beacon-APIs/commit/f65d774fe8abfb7773fc6f7c05d5453479b971ed) aka [v2.4.1](https://github.com/sila-chain/beacon-APIs/releases/tag/v2.4.1):heavy_check_mark:

- [PR-321 - Update publishBlindedBlockV2 request schema for SilaDeneb ](https://github.com/sila-chain/beacon-APIs/pull/321)- Merged :heavy_check_mark:
- [PR-302 - Add blob signing endpoints](https://github.com/sila-chain/beacon-APIs/pull/302) - Merged :heavy_check_mark:
- [PR-286 - Add blob download endpoint (getBlobs)](https://github.com/sila-chain/beacon-APIs/pull/286) - Merged :heavy_check_mark:
