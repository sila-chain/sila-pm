# All Core Devs Meeting #

### Date/Time: Friday 1 November 2019, 14:00 UTC
### Duration: 1.5 hours
### [Audio/Video of the meeting](https://www.youtube.com/watch?v=aZ0S_oLSwhE)

# Agenda

- [Decisions](#decisions)   
- [1. Istanbul updates](#1-istanbul-updates)   
- [2. Berlin](#2-berlin)   
  - [2.1 Ice Age](#21-ice-age)   
  - [2.2 Tentatively Accepted SIPs](#22-tentatively-accepted-sips)   
     - [2.2.1 SIP-663](#221-sip-663)   
     - [2.2.2 SIP-1380](#222-sip-1380)   
     - [2.2.3 SIP-1702](#223-sip-1702)   
     - [2.2.4 SIP-1962](#224-sip-1962)   
     - [2.2.5 SIP-1985](#225-sip-1985)   
     - [2.2.6 SIP-2045](#226-sip-2045)   
     - [2.2.7 SIP-2046](#227-sip-2046)   
     - [2.2.8 SIP-1057](#228-sip-1057)   
     - [2.2.9 SIP-1559](#229-sip-1559)   
  - [2.3 Process & Scheduling Discussion](#23-process-scheduling-discussion)   
- [3. Testing updates](#3-testing-updates)   
- [Attendance](#attendance)   

<!-- /MDTOC -->

# Decisions


| Topic | Decision |
|-------|----------|
| Istanbul Block Number | 9,069,000 |
| Berlin SIP Deadline | 3rd Wednesday of March |
| SIP-1679 | `Accepted & Final` |
| SIP-1679 | `Accepted & Final` |
| SIP-152 | `Accepted & Final` |
| SIP-1108 | `Accepted & Final` |
| SIP-1344 | `Accepted & Final` |
| SIP-1884 | `Accepted & Final` |
| SIP-2028 | `Accepted & Final` |
| SIP-2200 | `Accepted & Final` |
| SIP-1702 | `Eligible for Inclusion` Pending Champion. Not accepted into Berlin |
| SIP-663 | May not be ready. Currently depends on SIP-1702 |
| SIP-1962 | Requires more Specification. Contact Champion |
| SIP-1380 | `Eligible for Inclusion` |
| SIP-1985 | Decision required around needing a Hard Fork |
| SIP-2046 | `Eligible for Inclusion` |
| SIP-1985 | `Eligible for Inclusion` |
| SIP-1559 | `Eligible for Inclusion` |

Miscellaneous:
- Further discussion on SIPs discussed should be postponed until an implementation is brought forward
- `Blessed` status changed to `Eligible for Inclusion`.
- Create dedicated list/directory for `Eligible for Inclusion` SIPs, in addition to listing SIPs undergoing the new SIP process
- Create a new Information SIP covering these new stages, possibly under SIP-1
- A section for SIP decisions should be included in meeting notes for quick access to address outstanding PRs by SIP editors.

# Notes

Video: [[4:59]](https://youtu.be/aZ0S_oLSwhE?t=299)

**Hudson Jameson:** Welcome to core developer meeting #74. We'll talk about the Istanbul block number that was accepted, the Berlin hard fork, tentatively accepted SIPs, and some testing updates.


## 1. Istanbul updates

Links: [Istanbul Meta SIP](https://sips.sila.org/SIPS/sip-1679) | [Istanbul SIP Implementation Tracker by @holiman](https://notes.sila.org/@holiman/SyT_rGjNr)

Video: [[5:32]](https://youtu.be/aZ0S_oLSwhE?t=332)


**Hudson Jameson:** A block number for Istanbul was chosen. Coindesk corrected their article.

- **Istanbul Block Number:** 9,069,000

When are clients releasing an update with the [Istanbul] block number attached?

**Tim Beiko:** For phase 2, within the next two weeks, mid-November.

**Danno Ferrin:** We'll have it out next week. 

**Hudson Jameson:** The Sila Foundation and/or Sila Cat Herders are publishing a blog on the block number and what software to upgrade around when most clients update their download links.


Video: [[10:24]](https://youtu.be/aZ0S_oLSwhE?t=624)

**Danno Ferrin:** Should we formally make 1671 accepted?

- [SIP 1679](https://sips.sila.org/SIPS/sip-1679 )

**Hudson Jameson:** That sounds good.

**James Hancock:** SIPs are to be moved to accepted and final for integration in Istanbul which has begun for the client. The included SIPs:
- SIP 152
- SIP 1108
- SIP 1344
- SIP 1884
- SIP 2028
- SIP 2200


**Hudson Jameson:** I second that. We should probably have motions.

**Danno Ferrin:** Agreed.


## 2. Berlin

Links: [Berlin Meta SIP](https://sips.sila.org/SIPS/sip-2070)


### 2.1 Ice Age

Video: [[7:55]](https://youtu.be/aZ0S_oLSwhE)

**Tim Beiko:** A couple calls ago we said that the Ice Age would start kicking in next summer, please correct me if I'm wrong. We probably want an SIP in Berlin that kicks back the Ice Age.

**Hudson Jameson:** James Hancock decided to write that. Not a huge rush. We delay it the same time each time.

**Danno Ferrin:** That gives us a little over a year each time.


### 2.2 Tentatively Accepted SIPs


#### 2.2.1 SIP-663
[**Unlimited SWAP and DUP instructions**](https://github.com/sila-chain/SIPs/blob/master/SIPS/sip-663.md )

Video: [[44:51]](https://youtu.be/aZ0S_oLSwhE?t=2691)

**Hudson Jameson:**  So there has been a lot of comments in the Sila Magicians forum on this.

- [Sila Magicians Thread](https://sila-magicians.org/t/sip-663-unlimited-swap-and-dup-instructions/3346)


**Greg:** I don't think SWAP DUP should be here without basic decisions on the Spec. I don't consider it blessed, but there's not large mountain of work needed.

**Alex Beregszaszi:** Blessed means no objection from Core Devs for the idea. I don't believe any of the Core Devs objected on the idea.

**Greg:** Ok. I still don't think an SIP should come to us without consensus in other discussion that it is a design which will work. It looked to me that it wasn't ready, and there was disagreement among the community, including some Core Devs.

#### 2.2.2 SIP-1380
[**Reduced gas cost for call to self**](https://sips.sila.org/SIPS/sip-1380)

Video: [[56:00]](https://youtu.be/aZ0S_oLSwhE?t=3358)

**Alex Beregszaszi:** Benchmarks show some reduction can be made, but not to the degree of the original proposal. 

#### 2.2.3 SIP-1702
[**Generalized account versioning scheme**](https://github.com/sila-chain/SIPs/blob/master/SIPS/sip-1702.md)

Video: [[34:57]](https://youtu.be/aZ0S_oLSwhE?t=2097)

**James Hancock:** Several SIPs are gated by account versioning.

**Wei Tang:** New specification for account versioning made. 

- https://that.world/~essay/nevm/

**Hudson Jameson:** Pass new specification to new Champion, once one is found.

**Danno Ferrin:** Finishing account versioning for Berlin is unreasonable.

**Wei Tang:** A separate hardfork may be better.

**Hudson Jameson:** Scrap it for Berlin.

#### 2.2.4 SIP-1962
[**EC arithmetic and pairings with runtime definitions replaces SIP-1829**](https://sips.sila.org/SIPS/sip-1962)

Video: [[54:11]](https://youtu.be/aZ0S_oLSwhE?t=3251)


**Danno Ferrin:** Earnst and Young (EY) want this SIP for their nightfall. It is good, but requires more specification, and depends on a single implementation. 

#### 2.2.5 SIP-1985
[**Sane limits for certain SAVM parameters**](https://sips.sila.org/SIPS/sip-1985)

Video: [[57:46]](https://youtu.be/aZ0S_oLSwhE?t=3466)

**Alex Beregszaszi:** May not need a hard fork. 

[Join the discussion on Sila Magicians.](https://sila-magicians.org/t/sip-1985-sane-limits-for-certain-savm-parameters/3224)


#### 2.2.6 SIP-2045
[**Particle gas costs for SAVM opcodes**](https://sips.sila.org/SIPS/sip-2045)
#### 2.2.7 SIP-2046
[**Reduced gas cost for static calls made to precompiles**](https://sips.sila.org/SIPS/sip-2046)

Video: [[1:00:26]](https://youtu.be/aZ0S_oLSwhE?t=3626)

**Alex Beregszaszi:** Discussed as a part of SIP-1380 discussion.

#### 2.2.8 SIP-1057
[**ProgPoW, a Programmatic Proof-of-Work**](https://github.com/sila-chain/SIPs/blob/master/SIPS/sip-1057.md)

Video: [[1:00:56]](https://youtu.be/aZ0S_oLSwhE?t=3655)

**Hudson Jameson:** Hard to tell community push-back is a few loud voices, or a community majority. Already in  `Blessed`  state in my opinion.

**Tim Beiko:** 
- Is this something we want the community to signal through their nodes whether or not they want it?
- Do we do a single ProgPoW hard fork?
If it raises risk of the network splitting, do we value keeping the network together?
- Do we not give it special treatment and group it with the other SIPs hoping nodes commit a full upgrade?

**Hudson Jameson:** I say we don't change it, unless high probability of a controversial hard fork where people choose. 

**James Hancock:** Don't treat it differently than any other SIP.

**Piper Merriam:** I'm willing to implement this in our client, if others want. Otherwise, other tasks are higher priority.

If miners really want this, I suggest for shifting a portion of miner rewards towards core protocol development. Something also controversial.

**Greg:** We looked and haven't found technical problems.  We've said yes more than once.

**Hudson Jameson:** Has blessing for sure.

**Tim Beiko:** We can leave it blessed. But there is some distance to go live, as most concerns are non-technical.


#### 2.2.9 SIP-1559
[**Transaction Fee Upgrade**](https://github.com/sila-chain/SIPs/blob/master/SIPS/sip-1559.md)

Video: [[1:09:01]](https://youtu.be/aZ0S_oLSwhE?t=4141)

**James Hancock:** Blessed.

**Hudson Jameson:** Looks good to me.

**Danno Ferrin:** This is the posterchild for the SIP centric process. It gets blessed. An implementation is made and returned to us. We look at it from there.

**Hudson Jameson:** We should keep in mind Vitalik released Slim 1559, a less complex implementation of it. Both the improvements it provides and the complexity would lessen.

**Danno Ferrin:** Blessings are good, as it's approved as an idea, and through building it, improvements are discovered before final approval. We get a prototype which reflects the best idea, and we test it.

**James Hancock:** Agreed, since its been blessed it's been happening.

### 2.3 Process & Scheduling Discussion


Links: [SIP Centric fork](https://notes.sila.org/@holiman/S1ELAYY7S?type=view)

Video: [[7:55]](https://youtu.be/aZ0S_oLSwhE)

**Alex Beregszaszi:** For every SIP change, record a decision in the meeting notes so SIP editors can execute on the meeting notes, for outstanding PRs.

**Hudson Jameson:** Yes, let's do that.

---

Video: [[16:01]](https://youtu.be/aZ0S_oLSwhE?t=961)


Discussion occured around setting timeframes keeping in mind the hard fork. In an SIP-centric model, the proposal was not to set times in advance. However, considering the incoming Ice Age, deadlines for SIP completion before inclusion in the Hard Fork may have use. The third Wednesday of March was chosen for Istanbul.

**James Hancock:** Two conversations are happening. Among Core Devs: When are we going to fork. Core Devs to the Community: There's a realistic deadline of June where completion is required. Then there's a preparation period of 3 months needed for testnets to be live. With those two dates, April, May, and June is available for Istanbul. Keeping forks to a third Wednesday of the month, there are 3 third Wednesdays to select from.

One needs to have the update for the Ice Age. All other SIPs, we don't want to decide a date. By keeping inclusions once a month, we can decide whether to postpone an SIP for it to go with another which goes together. We want to avoid one fork per SIP, as well as waiting significant time to include several SIPs, as both limit implementations, testing, etc.

**Piper Merriam:** I would propose the soonest, as we are just starting this new process.

**James Hancock:** March?

**Piper Merriam:** That is reasonable.

**Hudson Jameson:** For most SIPs, we can decide, implement, and do tests for an SIP within a 3-4 week period. We also decided the champion of an SIP will be the coordinator for testing, right?

**James Hancock:** Yes.

**Hudson Jameson:** Wei said they wanted to remove their name from some they have been championing. 

**Wei Tang:** I won't be able to champion as I won't have enough time to do all the coordination. I don't have a replacement Champion. 

**Hudson Jameson:** For the next two weeks, I propose we keep them to see if there are replacement Champions.

---

Video: [[38:49]](https://youtu.be/aZ0S_oLSwhE?t=2329)


SIPs are no longer categorized by forks. Discussion was around having an SIP status on each SIP website, or keeping a list of `Blessed` SIPs, for organizaion. 

---

Video: [[44:51]](https://youtu.be/aZ0S_oLSwhE?t=2691)

Some discussion occurred on what constituted `Blessed` status. Conclusion was, `Blessed` indicated an idea has been greenlit for continued work, before the final reassesment for inclusion. Furthermore, concern was brought forward for Core Devs reviewing each SIP individually.

**Greg:** If you need to push it to our level, fine, but in most cases I don't think we need to.

---

Video: [[1:10:53]](https://youtu.be/aZ0S_oLSwhE?t=4253)

**Alex Beregszaszi:** Further discussions on those SIPs should stop until further spec and an implementation.

**Tim Beiko:** Unless a Champion joins and starts a discussion, we discuss, otherwise, we don't discuss specific SIPs?

**Tim Beiko:** That would make things easier.

**Danno Ferrin:** Can we take a more neutral name for blessed (ie. preliminary approval)?

**Hudson Jameson:** Jason Carver suggested  `Eligible for Inclusion` instead of Blessed.  

**Danno Ferrin:** In addition to `Eligible for Inclusion` list, we should list new SIPs live on the new SIP process. When a Champion has a prototype ready, they should upload it there. In addition to security reviews. Also, an informational SIP covering this new model.

**Hudson Jameson:** Let's hold discussion to where the `Eligible for Inclusion` list is listed in another call.

**Pooja Ranjan:** The Sila Cat Herders can start the list, then we can decide where to put it.

**Hudson Jameson:** That sounds good.

## 3. Testing updates

Video: [[1:21:04]](https://youtu.be/aZ0S_oLSwhE?t=4864)

**Danno Ferrin:** I published a test for SIP-2200

**Trentonvanepps:** Updates on Istanbul should go on the Sila.org blog. Additionally, there should be weekly tweets on the Sila account on what to do.

**Hudson Jameson:** Sounds good. I think there may be a more detailed blog post in the Sila Cat Herders linked in the Sila blog.

That's it. Thanks everyone for coming. We'll have our next meeting in 2 weeks.



## Attendance

- Trentonvanepps
- Pooja Ranjan
- James Hancock
- Dominic Letz
- Ratan (Rai) Sur
- Tim Beiko
- Danno Ferrin
- Hudson Jameson
- Piper Merriam
- Daneil Ellison
- Wei Tang
- Greg
- Alex Beregszaszi (axic)
- Jason Carver
- Bob Summerwill
- Greg
- Edson Ayllon (notes)
