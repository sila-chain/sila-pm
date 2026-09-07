# FOCIL session - Devcon SEA L1 R&D Workshop

## Summary

The goals of this session are twofold:

1. Increase the understanding of the **Fo**rk-**C**hoice enforced **I**nclusion **L**ists ([FOCIL](https://ethresear.ch/t/fork-choice-enforced-inclusion-lists-focil-a-simple-committee-based-inclusion-list-proposal/19870)) design, especially given the new [SIP-7805](https://x.com/soispoke/status/1853420123563970810?s=61).
2. Surface initial thoughts from developers regarding the implementation of FOCIL in clients.

**Facilitators:** Julian Ma, Terence Tsao, and Barnabé Monnot. **Note taker:** Barnabé Monnot.

## Agenda

- **State of FOCIL (Julian; 30 minutes; [slides](https://docs.google.com/presentation/d/1x-Blq5wqU_JaSmBkeEUz0PdY_cLyE0JPmi-CAChXqbU/edit?usp=sharing))**
    - What are FOCIL's design goals, and how does the mechanism work? How do the mechanism’s design parameters contribute to the design goals? These questions will be answered during the first presentation, where we will introduce FOCIL and explain what it does (and does not do).
- **Development of FOCIL (Terence; 15 minutes; [slides](https://docs.google.com/presentation/d/1sy42uuWUzyXXx_XUZDnFKIQ-ffgAmANdkJB44GHmaVo/edit?usp=sharing))**
    - This presentation explores the implementation space of FOCIL. What changes need to be made to support FOCIL?
- **Open Discussion (30 minutes)**
    - Time is allocated to discuss the parts of FOCIL that the audience is most interested in. These subjects could include but are not limited to, deep-diving specific FOCIL design considerations, better understanding how FOCIL may be implemented, and exploring the design space of extensions that FOCIL unlocks.
- **Closing Out (15 minutes)**
    - We will summarize the session and aim to agree on the most important topics to focus on.

## Session notes

### [Part 1: Julian presentation](https://docs.google.com/presentation/d/1x-Blq5wqU_JaSmBkeEUz0PdY_cLyE0JPmi-CAChXqbU/edit)

- Potuz question on fork choice
    - Something missing from SIP (ask Fradamt)
- Does FOCIL enforce ordering?
    - No, if it enforces some ordering, then IL committee members have sway over ordering, and they get sophisticated, which we don’t want
- Interaction of equivocation and free DA
    - Attack: send IL to everyone, send another one to the block builder, so the builder ignores the IL and gets screwed
    - Defense: there is some time for the builder to distribute equivocating ILs
- What if you craft a transaction which invalidates another transaction?
    - Such a tx would have to come from the same account, and if there are reverts, it’s fine, it’s invalid transactions we care about
    - See also tx stuffing attack defenses.
    - In MEV-Boost context, builder knows they are the winning builder at the end of the slot, may need to prepare the attack much earlier than this…
- If there are only 16 proposers, couldn’t a large staking pool capture all 16 slots?
    - Probabilistically unlikely, but if it happens, you have some sort of power but can’t do much with it (see also [tweet](https://x.com/barnabemonnot/status/1806814612509049275))
- Are ILs unattributable? Do we know who put what in which ILs?
    - There are other designs that have such properties, see [anon-ILs](https://ethresear.ch/t/anonymous-inclusion-lists-anon-ils/19627).
- Are there incentives for the 16 IL proposers, to not miss their IL?
    - No penalties if you miss your slot.
- Should IL committee members be incentivised to include things in their ILs?
    - There is ongoing work on fee markets for FOCIL, [it’s a pretty hard question to get right](https://ethresear.ch/t/fork-choice-enforced-inclusion-lists-focil-a-simple-committee-based-inclusion-list-proposal/19870).
- Should there be a rule for building the ILs? e.g., clients follow a randomised inclusion rule to prevent as much as possible overlaps between ILs
    - The SIP is somewhat generic.

### [Part 2: Terence presentation](https://docs.google.com/presentation/d/1sy42uuWUzyXXx_XUZDnFKIQ-ffgAmANdkJB44GHmaVo/edit)

- Should we include the validator index? If we want to do anonymised ILs?
    - Open question but there could be other designs
    - But you need to verify the signature so how do you do that?
- Fradamt: would be nice to do the sampling the same way we do it for aggregators.
    - sighs of relief in the room
- Why “up to 2 ILs per sender” are gossipped?
    - We gossip 2 if there is equivocation, so we keep propagating evidence of the equivocation, so people can ignore the list and de-score
- Should we slash for equivocation?
    - No need, too much work tbh 🙂(side rant, slashing for source/target is of a very different nature to slashing for block/head equivocation, and proposing two ILs is more of the second nature)
- Do you sell full txs on the gossip or hashes?
    - Full ones, but the EL knows the transactions already, so we could gossip just the hashes.
    - But this is a design decision that we are considering. If you do it by hash, then you can have very large transactions in there, e.g., stark proofs, but it’s more involved.
- Engine API changes, in ePBS would you need the second endpoint? “Enable the proposer to update its block with a list of IL txs with sufficient time”
    - Seems not
- In theory, can piggyback IL on the new payload response
- Is a block that doesn’t satisfy the IL “invalid”?
    - Not really, it’s more like invalid in the sense of the honest reorg.
    - Need sth like get_attester_head thing in the specs.
- Interaction with syncing
    - You don’t care about it unless it’s the current slot, only matters if you’re moving the head.

### Part 3: Jacob about the [SIP](https://sips.sila.org/sips/sip-7805)

Discussion about the specifications.

- Do we care about the gas target or the limit for conditional inclusion?
    - The limit, if you run out of gas in the block.

### Part 4: Q&A

- Interaction with SIP-1559 priority fee?
    - Not really, it’s maybe included through FOCIL, but then you have the usual flow.
- Can block stuffing happen?
    - Should be fine, there is economic cost.
    - Protocol can’t decide what’s “best” for the block if someone is willing to pay for trash getting in the block.
    - See [also](https://ethresear.ch/t/fun-and-games-with-inclusion-lists/16557#block-stuffing-in-forward-ils-2).
- Does it affect the target gas?
    - No, because inclusion happens via FOCIL maybe but then this is piped into the usual SIP-1559 flow.
- Should the builder API change?
    - Not really.
- Do we expect non-solo stakers to not make good ILs?
    - No, but they are more of an upper bound of quality.
- Should it be a default option in the clients?
    - Yes, makes sense.
    - There could be different rules, the clients are agents of the validators, who choose which rule to turn on for instance (with a default on thing).
- Should we integrate some rule with the MEV circuit breaker?
    - Could use that signal to do something, e.g., some IL building rule.
- Do extortion attacks work? e.g., putting malicious transactions in the ILs?
    - You can still do that, but there is no way to economically benefit from it, because there are 15 other IL proposers that could ignore the extortion.
    - And if this is attacks against bad censoring builders then it’s whatevs.

## Pre-Reads

Participants familiar with the following posts will be able to better participate in the workshop.

**If you have little time, please read at least the following:**

- [**Fork-Choice enforced Inclusion Lists (FOCIL)**](https://ethresear.ch/t/fork-choice-enforced-inclusion-lists-focil-a-simple-committee-based-inclusion-list-proposal/19870): A simple committee-based inclusion list proposal: The initial proposal of FOCIL.
- [**FOCIL CL and EL Workflow**](https://ethresear.ch/t/focil-cl-el-workflow/20526): Outline of the latest FOCIL implementation, defines the roles and duties of IL committee members, nodes, proposers, and attesters. We also address potential edge cases (e.g., equivocation, invalidation) and how to mitigate them.

**To be well-prepared, please read these as well:**

- [**FOCIL Resource Design Considerations**](https://hackmd.io/@ttsao/focil-resource-considerations#Proposer-Edge-Case): The resources FOCIL demands throughout an Sila slot.
- [**Uncrowdability of FOCIL**](https://mirror.xyz/julianma.sil/Gnd8N1IsoHuGHRisp6nCldlt72ZacoXUA-O76qQN3mc): This note discusses whether FOCIL participants (IL committee members) will outsource their IL construction to a centralized set of entities.

**These notes relate FOCIL to other block construction-related mechanisms:**

- [**Block construction session**](https://www.notion.so/Block-construction-session-bd611621250f45948eff05fcf6a34067?pvs=21): This note places FOCIL in the context of various block construction mechanisms such as ePBS and APS.
- [**On Multi-proposer Gadgets and Protocols**](https://hackmd.io/xz1UyksETR-pCsazePMAjw): This note compares FOCIL and BRAID, a multiple concurrent proposer design, on their properties and stages of research and development.

## Schematic Overview of FOCIL

![FOCIL.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/b6f02e04-07e9-46dc-b1e0-099d23103588/f16021c5-230f-405f-87ce-8ba89cc4581d/FOCIL.png)

## Current FOCIL Design Parameters

The following design parameters may inform the discussion during the workshop. Design parameters may be subject to change as FOCIL develops.

- **Commitee-based** (vs single-proposer)**:** 16 committee members create local inclusion lists, which are aggregated into one inclusion list.
- **Size:** Each local inclusion list is at most 8 kilobytes. There could be around 20 average-sized transactions in each local inclusion list, so there are around 320 average-sized transactions in all local inclusion lists. A block contains around 100-200 transactions.
- **Conditional** (vs [unconditional](https://ethresear.ch/t/unconditional-inclusion-lists/18500))**:** The aggregate inclusion list does not constrain the beacon block if the execution payload is full.
- **Spot** (vs [forward](https://notes.sila.org/@fradamt/forward-inclusion-lists))**:** The aggregate inclusion list created in slot $n$ constrains the beacon block in slot $n$.
- **Unordered** (vs ordered)**:** The inclusion list does not impose ordering constraints on the execution payload.
- **Anywhere-in-block** (vs top-of-block or bottom-of-block)**:** Transactions from the inclusion list could be included anywhere in the execution payload.
- **Expiring** (vs [cumulative](https://ethresear.ch/t/cumulative-non-expiring-inclusion-lists/16520))**:** The aggregate inclusion list created in slot $n$ only constrains the beacon block in slot $n$ and does not constrain later beacon blocks.