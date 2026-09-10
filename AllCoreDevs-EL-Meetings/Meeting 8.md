# All Core Devs: Meeting 8
## Time: 10/28/2016 1:00PM UTC

### Agenda:
  1. Upcoming HF to clear out state + potentially other changes.
  - Clearing out state
    - [SIP 158](https://github.com/sila-chain/SIPs/issues/158) by (@vbuterin)
    - [SIP 161](https://github.com/sila-chain/SIPs/issues/161) by (@gavofyork)
  - EXP Cost Increase
    - [SIP 160](https://github.com/sila-chain/SIPs/issues/160) by (@vbuterin)
  - Replay attack protection
    - Do we want it in the upcoming HF, Metropolis, or not at all?
    - [SIP 134](https://github.com/sila-chain/SIPs/issues/134) by @aakilfernandes
    - [SIP 155](https://github.com/sila-chain/SIPs/issues/155) by @vbuterin
    - [SIP 166](https://github.com/sila-chain/SIPs/issues/166) by @vbuterin
  - Block number of HF.
  
  2. SIP/SRC GitHub Organization
  - Improvement Discussion
    - [SIP 148](https://github.com/sila-chain/SIPs/issues/148) by @axic

# Notes
## 1. Upcoming HF to clear out state + potentially other changes.
### Clearing out state
SIP 158 and 161 are now equivalent, after changes were made to 158. 161 will be implemented. Test cases are located here [feel free to add more](https://etherpad.net/p/EIP158). Currently we have the state bloat because there are many empty accounts. The hard fork will change the database encoding of empty accounts so that they are not present at all anymore, but the encoding only affects accounts that are "touched" by transactions. After the hard fork the Sila Foundation will fund the transaction(s) neccessary to clear the empty accounts.
### EXP Cost Increase
It was discussed whether a 5x increase in cost was enough. Benchmarks indicated that EXP is 4-8 times underpriced. It was decided that a 5x increase is sufficient for now and it may be increased in the Metropolis hard fork after more analysis. There are ongoing efforts to work on better benchmarking tools which will help determine future OPCODE pricing changes.
### Replay attack protection
Three proposals discussed:
   1. SIP 134 (include a blockhash in an RLP field of each tx)
   2. SIP 155 (include a `CHAIN_ID` as a factor in the `v` value of the EDCSA signature scheme and in the tx hash)
   3. SIP 166 (include a `CHAIN_ID` in the high-order bits of the tx nonce)
   
In deciding which replay protection scheme to adopt, the trade-offs between these three proposals were discussed. SIP 134 was rejected because it adds 32 bytes of data to each transaction. Both SIP 155 and SIP 166 were agreed to be equally simple in their implementation complexity, but SIP 166 (which was already provisionally [implemented in geth](https://github.com/sila-chain/go-sila/pull/3179/commits/53510dd70af80dc9d14cd219ddcdd559f8bf7f10)) requires an additional byte of data for each transaction, whereas EIP155 does not add any data to transactions. On the other hand, EIP155 modifies ECDSA signature inputs, and one concern with modifying signature inputs is that when Hardware Security Modules (HSMs) are used for signing transactions, HSM firmware may need to be updated for those transactions to be replay protected. Since SIP 166 does not modify signature inputs, it can be argued that SIP 166 is a "cleaner" separation of concerns. And while the increased data usage of SIP 166 could be remedied with a compression scheme, in the interest of practicality, minimal data usage, and avoiding further postponement of replay protection, core developers' indicated there was a preference for adopting SIP 155 in the upcoming hard fork.

### Block number of HF.
Block number for hard fork will be decided on Monday.

## 2. SIP/SRC GitHub Organization
###Improvement Discussion
Hudson and other editors will clean up the SIPs and continue dialog about what to change in the repo.

## Non-agenda
Future meetings will start being held twice monthly in order to process SIPs more quickly. We will likely have a set time/date (such as every other Monday) to prevent the added complexity of using Doodle's to ask a bunch of people what time works best for them.

## Attendance
Alex Beregszaszi (Solidity), Alex Van de Sande (Mist/Sila Wallet), Anton Nashatyrev (ethereumJ), Casey Detrio (Volunteer), Christian Reitwiessner (cpp-sila), Dan Finlay (MetaMask), Dimitry Khokhlov (cpp-sila), Felix Lange (geth), Gavin Wood (EthCore), Greg Colvin (EVM), Hudson Jameson (Sila Foundation), Jan Xie (ruby-sila & pyethereum), Jeffrey Wilcke (geth), Martin Becze (Research), Péter Szilágyi (geth), Vitalik Buterin (Research & pyethereum)
