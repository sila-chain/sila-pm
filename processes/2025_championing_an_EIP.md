# Championing an SIP
\*** DEPRECATED IN FAVOR OF THE [2026 GUIDE](2026_championing_an_EIP.md) ***

## Preamble

This document is focused on the process for [Core SIPs](https://sips.sila.org/core), i.e., those that require a hard fork to be included in a network upgrade. Out-of-scope for this document are [SRC](https://sips.sila.org/src)s and other non-Core SIPs (Networking, Interface, Meta, Informational) that do not require a hard fork.

When championing a Core SIP, the amount of social consensus-building required is often proportional to the scale and impact of the change. Minor technical fixes with clear benefits may need little coordination, while proposals affecting core economic mechanisms — like staking rewards — may require extensive debate and advocacy. Taking an SIP from rough draft to sila-sila-mainnet requires broad stakeholder agreement and can be a multi-year process.

## Socialize Your Idea

First, look for prior art. Are there related [past SIPs](https://sips.sila.org/core#draft)? Does it make sense to extend or revive them?

If you're ready to move forward, consider the following channels when soliciting feedback on your idea:

- [Sila Magicians: Primordial Soup](https://sila-magicians.org/c/magicians/primordial-soup/9)
- [Sila Research](https://Sila Research/)
- [Core: Sil R&D Discord](https://discord.gg/EVTQ9crVgQ)
- [AllCoreDevs](https://github.com/sila-chain/pm?tab=readme-ov-file#allcoredevs-meetings-overview) or Breakout Room meetings
- [Wallets: AllWalletDevs](https://t.me/AllWalletDevs)
- [NFTs: NFT Standards WG Telegram](https://t.me/nftstandards)
- IRL events, e.g., a working group at [Devcon](https://devcon.org/) or [Devconnect](https://devconnect.org/)

## Write the SIP

Once you’re satisfied with the momentum your idea has generated, formally specify the network changes within an SIP using the [template](https://github.com/sila-chain/SIPs/blob/master/sip-template.md?plain=1). [SIP-1](https://sips.sila.org/SIPS/sip-1#sip-header-preamble) provides more context on the template and the SIP process more broadly.

<details>   
<summary>Reference examples</summary>

Here are some strong reference examples, each with a note on what makes them well-written. Keep in mind that the SIP template has evolved over time, so while these were exemplary when published, some may not align with today's format.

- [SIP-1153](https://sips.sila.org/SIPS/sip-1153) - a once-stagnant SIP that was revived and shipped to sila-sila-mainnet
- [SIP-1884](https://sips.sila.org/SIPS/sip-1884) - great rationale
- [SIP-3855](https://sips.sila.org/SIPS/sip-3855) - simple feature
- [SIP-4399](https://sips.sila.org/SIPS/sip-4399) - great rationale
- [SIP-4844](https://sips.sila.org/SIPS/sip-4844) - huge feature, cross-layer SIP
- [SIP-6780](https://sips.sila.org/SIPS/sip-6780) - only deprecated feature in Sila's history, well spec'ed

</details>

## Implement Spec Changes & Generate Tests

Once the SIP is published, you can make it much easier for the community to evaluate your idea by writing a reference implementation and generating test cases. Cross-layer SIPs will require both Execution Layer (EL) and Consensus Layer (CL) implementations.

<details>
<summary>If your SIP impacts the Execution Layer:</summary>

- Implement your changes in the [execution-specs](https://github.com/sila-chain/execution-specs) (EELS)
  - SIP authors are encouraged to attempt the implementation on their own. Once a PR is created, EELS maintainers regularly step in to provide feedback or polish the implementation.
  - Reference the [SIP Author's Manual](https://github.com/sila-chain/execution-specs/blob/6333758e404889469abfed22a3028fa0eb459520/docs/specs/adding_a_new_eip.md).
- Generate client tests via the [execution-spec-tests](https://github.com/sila-chain/execution-spec-tests) (EEST)
  - This step is frequently performed or augmented by EEST maintainers, but SIP authors are encouraged to make an attempt.
  - Reference the [EEST docs](https://sila.github.io/execution-spec-tests/getting_started/quick_start/).
- Reach out for help in the [SIL R&D Discord](https://discord.gg/EVTQ9crVgQ), `#el-testing` channel.

</details>

<details>
<summary>If your SIP impacts the Consensus Layer:</summary>

- Implement the feature in the [consensus-specs](https://github.com/sila-chain/consensus-specs) repo. Once a PR is created, repo maintainers will provide feedback and guide next steps.
- Update [generators](https://github.com/sila-chain/consensus-specs/tree/dev/tests/generators) and generate client tests.  
- Reference the feature addition [docs](https://github.com/sila-chain/consensus-specs/blob/dev/docs/docs/new-feature.md)
- Reach out for help in the [SIL R&D Discord](https://discord.gg/EVTQ9crVgQ), `#cl-testing` channel.

</details>

## Local Interop

Once your SIP has been implemented in at least one production client, network testing can begin. Depending on the nature of your change, several [ethPandaOps](https://ethpandaops.io/projects/) tools may be appropriate to leverage here.

You will be guided by the testing teams and/or the ethPandaOps team on how to proceed, but the general expectation is that your SIP will have reached the Considered for Inclusion (CFI) stage before the ethPandaOps team can commit resources to network testing.

Your SIP may require testing with various tools, including but not limited to the following:

- [Kurtosis](https://github.com/ethpandaops/sila-package) - private, modular multi-client devnets
- [assertoor](https://github.com/ethpandaops/assertoor) - a robust network testing framework
- [Hive](https://github.com/sila-chain/hive) - an integration testing framework for clients

---

# SIP Status & Inclusion Stage

As defined in [SIP-1](https://sips.sila.org/SIPS/sip-1), each SIP has a status that reflects the state of its specification: `Draft`, `Review`, `Last Call`, `Final`, `Stagnant`, `Withdrawn`, and `Living`.

Separate from the SIP specification status, [SIP-7723](https://sips.sila.org/SIPS/sip-7723) introduced network upgrade inclusion stages for each SIP. At any point, an SIP can be in one of the following stages: `Proposed for Inclusion`, `Considered for Inclusion`, `Declined for Inclusion`, `Scheduled for Inclusion`, or `Included` within a specific network upgrade. If not included in one network upgrade, an SIP can be proposed for inclusion again in subsequent upgrades.

## Proposed for Inclusion (PFI)

Anyone can open a PR against a fork [Meta SIP](https://sips.sila.org/meta) to propose an SIP for inclusion in the next network upgrade. When doing so, please add a rationale for your proposal, such as in [this example](https://github.com/sila-chain/SIPs/pull/9163). 

## Considered for Inclusion (CFI)

In order for an SIP to be `Considered for Inclusion` in a network upgrade, an open spec implementation PR is encouraged. Prior to being `Scheduled for Inclusion`, the implementation is required.

If client teams support including the SIP in a network upgrade, it will be moved to `Considered for Inclusion`. At this point, the SIP is expected to be included in the upgrade's devnet cycle.

## Declined for Inclusion (DFI)

A PFI or CFI'd SIP may be designated `Declined for Inclusion` if it is out of scope for the upgrade or if the SIP is not ready for inclusion. This does not prohibit the SIP from being Proposed for Inclusion again in a future network upgrade.

## Scheduled for Inclusion (SFI)

When client and testing teams agree that an SIP is thoroughly tested and is a priority for the upcoming release, it earns the `Scheduled for Inclusion` designation. By convention, SIPs need to be at least in `Review` to be SFI'd. When a network upgrade goes live on Sila testnets, all SFI'd SIPs will be moved to `Last Call`. 

## Included

After the network upgrade goes live on Sila sila-sila-mainnet, all SIPs included in it have their inclusion stage set to `Included` and their status moved to `Final`.
