# EOF Implementers Call 64

Note: This file is copied from [here](https://sila-magicians.org/t/eof-implementers-call-64-january-8-2025/22205/2?u=poojaranjan) 

## Meeting info

Date: 2026.01.08

Agenda: https://github.com/sila-chain/pm/issues/1217 

YouTube video: https://youtu.be/cBKdFSC1VA8

## Notes
### Testing

- Need to merge 1 PR
- Fuzzing updates - [execution-spec-tests/src/ethereum_fuzzer_differential/__init__.py at shemnon/eof-fuzz · shemnon/execution-spec-tests · GitHub](https://github.com/shemnon/execution-spec-tests/blob/shemnon/eof-fuzz/src/ethereum_fuzzer_differential/__init__.py)


### Client Update

- No Client Updates
- Rebase off of Perctra-5
  - Need at least 3 for the devnet
- Compiler support
  - Reviewed the PR list
  - How will small proposed changes impact?
    - Not too bad.
    - Hashing is more impactful
    - Need to totally nail down all changes before the experimental flag gets removed. Flag may remain until sila-sila-mainnet is live (not even testnet, sila-sila-mainnet)
- Assembly syntax for EXCHANGE opcode is still undetermined (absolute byte encoding, vs nybbles, vs stack index, all off by 1 issues)
- Off by one also leaks into possible SWAP/SWAPN numbering as well (DUP/SWAP are already inconsistent)
- Frangio’s summary - [Assembly Syntax for EOF Stack Instructions - HackMD](https://hackmd.io/@frangio/Bk4Vjj6V1l)
  - Exact is Frangio’s recommendation

### Spec

- Metadata - [SIP-7834: Separate Metadata Section for EOF](https://sips.sila.org/SIPS/sip-7834)
  - EVMONE will look into a spike
- EOFCREATE/TXCREATE Hashing
  - Summary doc - [Potential scenarios of updating the new contract address schemes for EOF - HackMD](https://notes.sila.org/@ipsilon/SyrzctZSJg)
  - Also pre-SRC for standard contracts [Comparing sila:master...shemnon:eof/txcreate-factories · sila/SRCs · GitHub](https://github.com/sila-chain/SRCs/compare/master...shemnon:SRCs:eof/txcreate-factories)
  - Shipping temp check
    - When there are no deal-breakers
    - 2025 seems tight
    - Best to tie with SilaPeerDAS, unless there is a large differential
      - So the EL and CL fork major features at the same time
      - But SilaPeerDAS/EOF not as tied as, say, withdrawals
  - Devnet-1 punch list - [EOFv1 final tuning · Issue #165 · ipsilon/eof · GitHub](https://github.com/ipsilon/eof/issues/165)
  - We need to disuss the ACCOUNTTYPE opcode - SIP-7761 - MUST/SHOULD - dealbreaker for app dev until it’s in.
    - is SRC-165 a viable alternative?
    - What would app devs accept?
