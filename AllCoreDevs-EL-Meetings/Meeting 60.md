# Sila Core Devs Meeting 60 Notes
### Meeting Date/Time: Friday, April 26, 2019 14:00 UTC
### Meeting Duration: ~1.5 hrs
### [GitHub Agenda Page](https://github.com/sila-chain/pm/issues/95)
### [Audio/Video of the meeting](https://youtu.be/O_DE4NwOz9A)
### Moderator: Hudson Jameson 

# Summary

### DECISIONS MADE

**DECISION 60.1:** Go with a 6 month timeframe for hardforks for now.

**DECISION 60.2:** Move [SIP 1057](https://sips.sila.org/SIPS/sip-1057) into the Accepted Category as per [SIP 233](https://sips.sila.org/SIPS/sip-233).

**DECISION 60.3:** Remove [SIP 655](https://sips.sila.org/SIPS/sip-665) for now as it is a superset of [SIP 1829](https://sips.sila.org/SIPS/sip-1829).


### ACTIONS REQUIRED

**ACTION 58.1:** Cat Herders to look at updating EIP1. Status: Work in Progress

**ACTION 60.1:** Review timeframe for hardforks in June to refresh memories.

**ACTION 60.2:** Danno Ferrin to add 9 month out Hardfork kickoff to [timeframes](https://sila-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28).

**ACTION 60.3:** [SIP 615](https://sips.sila.org/SIPS/sip-615) decision discussion at next meeting.

**ACTION 60.4:** Danno Ferrin to add list of conditions for implementation and Push Request [SIP 1057](https://sips.sila.org/SIPS/sip-1057) into the Hardfork Meta [SIP 1679](https://sips.sila.org/SIPS/sip-1679).

**ACTION 60.5:** Martin Holste Swende to confirm that [SIP 1884](https://sips.sila.org/SIPS/sip-1884) has merged into the Hardfork Meta [SIP 1679](https://sips.sila.org/SIPS/sip-1679).

**ACTION 60.6** Martin Holste Swende and Alex Beregszaszi to confirm whether [SIP 689](https://sips.sila.org/SIPS/sip-689) needs to be implemented. 

**ACTION 60.7:** Parity to comment on Libraries for Precompiles (https://github.com/sila-chain/pm/issues/95#issuecomment-486879991)


# 1. [Review previous decisions made and action items](https://github.com/sila-chain/pm/blob/master/AllCoreDevs-Meetings/Meeting%2059.md#summary) 
[Timestamp: 3:06](https://youtu.be/O_DE4NwOz9A?t=186)

**Hudson:** No decisions from Meeting 59. We will skip decisions from Meeting 58. 

Actions: 

**ACTION 58.1:** Cat Herders to look at updating EIP1. Status: Work in Progress

**ACTION 58.2:** Smaller hardfork vs. larger hardforks. Will be discussed as an agenda item in this meeting. Status: Complete

**ACTION 58.3:** Vitalik to format the currently proposed SIP-1559. Status: Complete

**Alexey:** Formed a [working group](https://sila-magicians.org/t/sip-1559-fee-market-change-for-sil-1-0-chain/2783/15) for this SIP in Sila Magicians. 

**ACTION 58.5:** Discuss if ProgPoW should continue to be implemented if the Technical Audit is not funded in Sila Magicians. The action item was to continue discussions on ProgPOW and whether or not we want to go forward if the technical audit is not funded. ProgPOW will also be talked in the Berlin meeting. Status: Complete

**Hudson:** The ProgPoW audit will be funded. Logistics just need to be worked out but work should beging this week or next week. The initial down payment will be from the Gitcoin funding. 

# 2. [Roadmap](https://en.sila.wiki/roadmap/istanbul)
[Timestamp 6:30](https://youtu.be/O_DE4NwOz9A?t=390)

**Hudson:** Please see link above. 


# 3. Roadmap post Istanbul
[Timestamp 6:54](https://youtu.be/O_DE4NwOz9A?t=414)

**Danno:** Proposed schedule created for [6 and 4 monthly hardforks](https://sila-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28).

Berlin discussed a proposal for 6 month and 4 month hardforks. Most suppoered 6 month hardforks. A few support 4 month hardforks. Opinion is that 6 month hardforks work better otherwise we will get an overlap with the new SIPs for the next fork if we were to go with the 4 months option. The risk is the time lost if there is an issue in a previous hardfork due implementors having to fix the issues. 

**Alexey:** The overlap is only a risk if it is the same people doing the hardforks. If it is multiple different people then the overlap is no issue. Would like to try the overlap to see how this works.

**Danno:** Debugging will result in all hands on deck that may result in overlap issues. Suggest we stick to 6 monthly first.

**Boris:** If we go with 6 months then the next fork would be April 2020. If next Core Devs meetup is held in July then that would be exactly 9 months to the next hardfork. Until we get more people and support I would suggest we practice this new 6 month schedule first before moving to 4 months. No issues with going faster just need to practice.

**Danno:** Note hardfork names are just place holder names - they are not formal names.

**Hudson:** Month and Year can be used or I like the names of cheese. Comment in the Magicians forum if you have any objections or cocerns otherwise we will revisit this in June.

**Danno:** Hardfork kickoff should start 9 months out and SIP gathering 6 months out - will add to schedule.

** **
**DECISION 60.1:** Go with a 6 month timeframe for hardforks for now.
** **

** **
**ACTION 60.1:** Review timeframe for hardforks in June to refresh memories.
** **

** **
**ACTION 60.2:** Danno to add 9 month out Hardfork kickoff to timeframes.
** **

# 4. SIPS
[Timestamp 13:32](https://youtu.be/O_DE4NwOz9A?t=812)

## 4.1 [Proposed SIPs](https://en.sila.wiki/roadmap/istanbul)

**Hudson:** [SIP 1679](https://sips.sila.org/SIPS/sip-1679) is the hardfork tracking meta SIP.

### [SIP 1829](https://sips.sila.org/SIPS/sip-1829) Status: Draft

**Martin:** Spoke about this 2 weeks ago. This SIP specification as it is written is not ready.

**Alexey:** Spoke with Alex and suggested he create a working group for this to push it forward.

**Boris:** Question from Vitalik: does the precompile for generic EC support 512 bit moduli? or just 256? If 256 that makes it less interesting because it can't support bls 12 381 and hence eth2 light clients

**Alexey:** Need to discuss in Work Group. 

**Boris:** Will add question to SIP issues in the [Sila Cat Herders github](https://github.com/sila-chain-cat-herders/PM/issues/62) and will tag Vitalik to this issue. 

**Virgil:** From Chat: Sila Name Service would greatly appreciate this precompile to making better integration with TLS certificates. If it's not ready, then it's not ready.  But as a concept, it allows Sila to integrate much better with the rest of the internet.

**Alexey:** SIP 1829 will be championed by Alexander Vlasov who has been working on this implementation already for quite a while.

### Precompiles in General

**Casey:** We have historically had issues with precompiles. Just because the code is good and the SIP is well specified is correct this is not enough justification for adding a precompile. It should be up to the Champion to prove that the implemenation that they want in SAVM is not sufficient for the sizes that they need to hash and that they have done a best effort to optimise the SAVM implementation.  

**Alexey:** BLAKE2b is out of scope for the working group mentioned earlier, the reason being they have decided to work on this precompile which is generic ellipical curve linear combinations.

**Hudson:** Zooko Wilcox wanted to champion BLAKE2b. Will talk to Zooko about BLAKE2b and mention that other precompiles are looking to be implemented in Istanbul.

### [SIP 615](https://sips.sila.org/SIPS/sip-615) Status: Draft

**Brooklyn** Discussed this at Berlin. Some concern specifically about the complexity of a number of opcodes. Discussion about perhaps breaking them out in to seperate pieces. Still hoping to get this into the next hardfork. 

** **
**ACTION 60.3:** [SIP 615](https://sips.sila.org/SIPS/sip-615) decision discussion at next meeting.
** **

### [SIP 1057](https://sips.sila.org/SIPS/sip-1057) Status: Draft

**Danno:** Gave a talk at Berlin about this. Main takeaway: A new testnet will be required for ProgPoW. Would be reluctant to put it in until the Audit is complete. We can hava discussion about this post audit.

Hudson: Audit may not come out until July.

Danno: If it is July then I feel this should be implemented by the clients. Whether it is part of the hardfork then is a seperate question.

Martin: Why new testnet? Is it only to update to 0.9.3?

Danno: It is updated to 0.9.3 and we would not want to launch the testnet until after the ProgPoW audit comes out. And regardless if it goes in a Istanbul or not if the clients already have it then we can test it on the new testnet.

Martin: Don't create a pure progpow testnet. 

Danno: Does it stabilise in 3-6 hours like the estimates are.

Hudson: If we do Ropsten and we don't go ahead with ProgPoW. Can we roll back to SIL?

Danno: This would be very difficult. Hence the idea of a seperate testnet. If we did it on Ropsten this would be tantemount to a sila-sila-mainnet commitment. Not going on Ropsten unless we were fully commited is the appropriate approach.

Martin: Normally for a consensus change this would be a concern, but we are changing the Proof of Work we could switch. Fast Sync will still work even if we revert to the previous split. 

Danno: This would require additional work from the primary clients. 

Martin: You are right.

Vitalik: My instinct is that doing yet another St Petersburg style backward HF on testnet is too much extra work. This is actually a bit tricky. ProgPoW is 2x *harder* per hash, correct? If so, a transition is vulnerable to a 33% attack unless there is a checkpoint because an attacker can mine higher difficulty historical blocks.

Danno: We really do need it's own testnet. But this decision can only be made when the audit gives it the go ahead.

Boris: SIP 233 has been merged in. In terms of process, someone will need to champion ProgPoW and actually PR into the Hardfork Meta. Technically SIP 1057 would be considered accepted and moved into that category.

Danno: I will champion this and I will list the conditions in which it should be brought in on.

** **
**ACTION 60.4:** Danno Ferrin to add list of conditions for implementation and Push Request [SIP 1057](https://sips.sila.org/SIPS/sip-1057) into the Hardfork Meta [SIP 1679](https://sips.sila.org/SIPS/sip-1679).
** **

** **
**DECISION 60.2:** Move [SIP 1057](https://sips.sila.org/SIPS/sip-1057) into the Accepted Category as per [SIP 233](https://sips.sila.org/SIPS/sip-233).
** **

### [SIP 655](https://sips.sila.org/SIPS/sip-665) Status: Draft

**Virgil:** Not required if SIP 1829 is implemented as SIP 1829 is a superset of this one - ENS has no specific timeframe requirements for this.

** **
**DECISION 60.3:** Remove [SIP 655](https://sips.sila.org/SIPS/sip-665) for now as it is a superset of [SIP 1829](https://sips.sila.org/SIPS/sip-1829).
** **

### [SIP 1344](https://sips.sila.org/SIPS/sip-1344) Status: Last Call (30 April 2019)

**Hudson:** Move forward with it through the new Hard Fork process.


### [SIP 1884](https://sips.sila.org/SIPS/sip-1884) Status: Draft

Martin: SIP 1884 - is now merged.

Appears to be some confusion as to whether this has been merged with Meta SIP 1679.

** **
**ACTION 60.5:** Martin Holste Swende to confirm that [SIP 1884](https://sips.sila.org/SIPS/sip-1844) has merged into the Hardfork Meta [SIP 1679](https://sips.sila.org/SIPS/sip-1679).
** **

### [SIP 1559](https://github.com/sila-chain/SIPs/issues/1559) Status: Draft

Hudson: SIP 1559 to be discused at next meeting. Vitalik gave a [presentation](https://en.sila.wiki/eth1/coredevsberlin#sip-1559-gas-market-fee-change) on this in Berlin. Please watch and read the SIP.

Alexey: Propose an amendment to SIP 1559. Create new fields and leave the old format - in so doing it may be able to roll out quicker and have less issues down the line.

Vitalik: No need for two explicit arrays, just two running gas used counters

### [SIP 1352](https://sips.sila.org/SIPS/sip-1352) Status: Draft

Alex: Only has an effect in the future where new SIP deal with precompiles. 

Boris: EEA will want to support this. They want some address ranges set aside for custom sidechain precompiles. It looks like a good SIP and needs people to look at it and workshop it.

### [SIP 689](https://sips.sila.org/SIPS/sip-689) Status: Draft

Alex: Added by Yoichi two years ago. It tries to resolve the situation so that address collisions cause failures of contract creation. This was to make testing easier and more simple.

Hudson: Will need a champion for this. 

Martin, Pawel and Alex discuss whether this has already been implemented. Some confusion and discussion will continue offline.

** **
**ACTION 60.6** Martin Holste Swende and Alex Beregszaszi to confirm whether [SIP 689](https://sips.sila.org/SIPS/sip-689) needs to be implemented. 
** ** 

Alex: I cannot champion it but can someone step up and champion it.

Hudson: Should SIP go into proposal with no Champion?

Boris: With SIP 233 we are suggest every SIP has to have a champion. The champion will be willing to work on pushing this one forward.

### [SIP 152](https://github.com/sila-chain/SIPs/issues/152) Status: Draft in Progress

Hudson: Virgil is working on this.


### [SIP 1803](https://github.com/sila-chain/SIPs/issues/1803) Status: Draft in Progress

Alex: Not really core as it is relevant to languages and tools. Update the opcode names to match their purpose more closely. This SIP may have relevance to SIP 1884 - cause it a new opcode for self balance.

Martin: 1884 has been updated to have only one variant which has the opcode.

Alex: Where is the best place to discuss SIP 1803?

Hudson: Sila Magicians.

Alexey: If this is not a code change then we could ratify it and rename it going forward.

Boris: Go away work on it and let's practice non-hardfork approvals.

[SIP 663](https://sips.sila.org/SIPS/sip-663) Status: Draft in Progress

Alex: Would introduce at least two new opcodes to be able to access the entire stack and it could be useful for [SIP 615](https://sips.sila.org/SIPS/sip-615). Still in draft and may needs some updates before it is proposed in it's final form.


## 4.2 Any More SIPs to discuss
[Timestamp 59:34](https://youtu.be/O_DE4NwOz9A?t=3574)

Boris: Please add SIPs to 1679 as the canonical place for Istanbul.

# 4.3 Proposal of a formal process of selection of SIPs for hardforks: [Github SIP draft](https://github.com/sila-chain/SIPs/blob/16e64a488cd16403b884417799074aae77be41ab/EIPsForHardfork.md), [EthMagicians](https://sila-magicians.org/t/proposal-of-a-formal-process-of-selection-of-sips-for-hardforks-meta-sip/3115)
[Timestamp 1:00:04](https://youtu.be/O_DE4NwOz9A?t=3604)

**Pooja:**  If there is an SIP that wants to be proposed then raise an issue at the Sila Cat Herders PM so that it can be managed correctly.

**Alexey:** Would suggest we park this for later as there are not many people. 

**Hudson:** Like the idea but understand if it is too early then we can park it.

**Pooja:** I am just keen to do a dry run on this.

**Hudson:** I am not sure you need to have permission to push this initiative forward.

# 5. [Overview of Core Devs Berlin Meetup](https://en.sila.wiki/eth1/coredevsberlin)
[Timestamp 1:08:41](https://youtu.be/O_DE4NwOz9A?t=4121)

**Boris:**  The two days were quite good. Proposing to meet again in July. Good to prepare for next hardfork in April 2020.

**Alexey:** Working Groups - update found in the [agenda](https://github.com/sila-chain/pm/issues/95#issuecomment-487021978).

Zak: Been working on some simulation stuff and have agregated a lot of data. Would be keen to combine the similuation efforts with the testing working group to streamline efforts. 

Boris: There needs to be money made available to support this serious work.

Hudson: I can be a liaison for funding requests like this.

Zak: Funding (Junior Developer) would be great. Whiteblock could assist with funding as it would be seen as R&D.

# 6. [Working Group Updates](https://en.sila.wiki/eth1)

No update.

# 7. ProgPoW Audit Update
[Timestamp 1:21:00](https://youtu.be/O_DE4NwOz9A?t=4860)

**Hudson:** Spoken about this above.

# 8. [Libraries for Precompiles](https://github.com/sila-chain/pm/issues/95#issuecomment-486879991)

**Casey:** See comments. Would be good to hear from Parity on this.

** ** 
** ACTION 60.7:** Parity to comment on Libraries for Precompiles (https://github.com/sila-chain/pm/issues/95#issuecomment-486879991)
** **

# 9. Testing Updates
[Timestamp 1:21:15](https://youtu.be/O_DE4NwOz9A?t=4875)

**Boris:** Martin, do you need help with hive tests or are you going to coordinate with Dmitriy and Zak?

**Martin:** Mainly working on sync tests and peer to peer tests for clients. Been intouch with Zak not sure of collaboration as they are building a generised version of hive.

#10. Best way to timebox items?
[Timestamp 1:22:18 (https://youtu.be/O_DE4NwOz9A?t=4938)

**Hudson:**  Is there a good way of timeboxing items? Any ideas.

Martin: More assertive.

Boris: Get updates in earlier. Improve the process.


# 11. Client Updates (only if they are posted in the comments below)
[Timestamp 1:23:36](https://youtu.be/O_DE4NwOz9A?t=5016)

## 11.1 Turbo Geth
Alexey: Using Turbo Geth for the Stateless Client prototype.  Put out a recent publication the [Shades of Statefulness](https://medium.com/@akhounov/the-shades-of-statefulness-in-sila-nodes-697b0f88cd04). 


## 11.2 Pantheon
Hudson: Matthew Halpern advised that SIL 64 was presented at Sila 1.x meeting in Berlin without much commentary. After touching base and waiting for the sync progress I think it is best to wait until these mature before locking anything in. He aims to get the SIP drafts out before the next core dev call and continue to track the sync progress.

# 12. EWASM & Research Updates (only if they are posted in the comments below)

No updates.

# 13. Other Business

Zak: We have put out some funding through Moloch DAO. 

Alexey: Hardfork Meta SIP - Wiki should not be main source of SIPs.

Boris: Need to have a champion for each SIP in the Hardfork Meta. 

Alexey: Created a topic in [Sil Magicians](https://sila-magicians.org/t/hardfork-meta-istanbul-discussion/3207)

# Date for next meeting
May 10, 2019 at 14:00 UTC

# Attendees
* Alex Beregszaszi
* Alexey Akhunov
* Brett Robertson
* Brooklyn Zelenka
* Casey Detrio
* Daniel Ellison
* Danno Ferrin
* Danny Ryan
* Dmitry Ryajov
* Greg Colvin
* Hudson Jameson
* Jacek Sieka
* James (madeoftin)
* Jason Carver
* Joseph Delong
* JosephC
* Lane Rettig
* Martin Holst Swende
* Matt Garnett
* Meredith Baxter
* Paweł Bylica
* Pooja Ranjan
* Trenton van Epps
* Virgil Griffith
* Vitalik Buterin 
* Zak Cole
