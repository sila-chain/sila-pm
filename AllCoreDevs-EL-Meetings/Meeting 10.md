# All Core Devs: Meeting 10
## Time: 2/10/2017 14:00PM UTC (Date shifted due to EdCon)
## [Audio of Meeting](https://youtu.be/huYl7eOlKJE)

### Agenda:

1. New SIP GitHub process and cleanup. [Facilitator: Hudson]
2. Come to final agreement on [SIP 196](https://github.com/sila-chain/SIPs/issues/196): EC addition and scalar multiplication on the elliptic curve `alt_bn128`, to be used in zk-SNARK verification. [Facilitator: Christian]
3. Update on [SIP 197](https://github.com/sila-chain/SIPs/issues/197) for EC pairing precompile [Facilitator: Christian]
4. Metropolis and associated SIPs. [Facilitator: Vitalik/Christian]
   * [SIP 5/8](https://github.com/sila-chain/SIPs/issues/8): Gas costs for return values [Facilitator: Christian]
   * [SIP 86](https://github.com/sila-chain/SIPs/issues/86): Proposed initial abstraction changes for Metropolis  [Facilitator: Vitalik]
   * [SIP 96](https://github.com/sila-chain/SIPs/issues/98): putting block hashes and state roots into the state  [Facilitator: Vitalik]
   * [SIP 100](https://github.com/sila-chain/SIPs/issues/100): uncle mining incentive fix  [Facilitator: Vitalik]  
   * [SIP 196](https://github.com/sila-chain/SIPs/issues/196) & [SIP 197](https://github.com/sila-chain/SIPs/issues/197): pairings [Facilitator: Christian/Vitalik]
   * [SIP 198](https://github.com/sila-chain/SIPs/pull/198): bigint arithmetic  [Facilitator: Vitalik]
   * [SIP 206](https://github.com/sila-chain/SIPs/pull/206): Revert OPCODE and [EIP207](https://github.com/sila-chain/SIPs/pull/207): Encoding of revert OPCODE [Facilitator: Vitalik]
5. [SIP 116](https://github.com/sila-chain/SIPs/issues/116): New opcode `STATIC_CALL` follow-up. [Facilitator: Christian]

# Notes

IN PROGRESS

### SIP 197: pairing precompile:
- Address `8` assigned to precompile
- Settled on 2 dimensional co-ordinates for curve points (x, y) rather than (X, Y, Z)
- Gas costs still to be determined
- Do costs vary based on the inputs?
- Implementations should be finished before gas costs finalise
- Number of input points to the function may be limited
- Gas price will probably be linear in number of EC points

### SIP 196: EC operations (addition and multiplication): 
- Needed for zk-snark verification to be efficient enough to actually use
- Gas costs still to be determined
- Multiplication gas costs may be complex (as the cost scales linearly with the size of the scalar being multiplied by), can be handled similiar to EXP gas costs
- go implementation: in progress
- Parity implementation: going to pull in from a library

### SIP 5/8: compromise proposal (needed to make proposal B backwards compatible): 
- new rules only if the return size is 2^256-1

Nick: seems complicated, what about adding `returndatasize` and `returndatacopy` similar to `calldatasize` and `calldatacopy` 
that can access return data even if return area size was specified as zero

- Accounting for return values has turned out to be more complicated than people realised
- Vitalik says the suggested improvements seems over-complicated
- Decided to try and resolve offline rather than on-call.

### SIP 86: account abstraction:
- Allow a new type of transaction with signature 000000, sender address assumed to be 0xff..f
- Type of transaction where instead of the account, there's a destination, which is assumed to be a forwarding contract. The forwarding contract checks the transaction data for a signature, and if this signature is valid (according to rules defined in the forwarding contract), the transaction is passed along to its intended destination.
   - abstract away account security
   - abstract away nonces
   - allows contracts to pay for gas

Things to be done:
- Items 2 & 3 in EIP86 (get rid of things based on sender and nonce, and instead base on code and sender)
- Implement new opcode
- extra protocol things:
   - logic in miner and logic in transaction propagating nodes
   - check for regexp that says the account the transaction goes to will pay a fee to the miner
   
 
 - Partially implemented in go (apart from the mining/transaction propogation changes)
 - Can't drain contracts because the contract code is only executed if the signature (abstracted signature -- the one in the data field) is valid, so the contract only has to check the signature and then dismiss transactions. Cost of validating these signatures is approx equal to checking non-verifying ECDSA signatures anyway.


## Attendance

Christian Reitwiessner (cpp-sila/Solidity),
Hudson Jameson (Sila Foundation),
Arkadiy Paronyan (Parity),
Vitalik Buterin (Research & pyethereum)
