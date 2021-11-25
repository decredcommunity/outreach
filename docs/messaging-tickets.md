---
author: margaret_mei, bee
published_utc: 2019-05-31
updated_utc: 2019-06-21
---

# Decred Ticket-Holder Voting

Decred employs a hybrid PoW (Proof-of-Work) + PoS (Proof-of-Stake) consensus system. Not only does this make the network more secure and resistant to 51% attacks than a conventional Proof-of-Work system, but the staking component allows those holding the coins, not just miners, to participate in changing the consensus rules.

Decred's governance is based on the principle of ticket-holder voting. Ticket holders forego liquidity and time-lock, or "stake", their DCR to acquire the right to participate in three types of voting:

1. Block Voting, On-chain. Tickets are selected and tallied per block. Y/N to approve the previous block. If >50% disapproves, it erases the miner reward and treasury budget, and returns the transactions to the mempool.
2. Consensus Voting, On-chain. Tickets are selected per block and tallied per rule change interval. Y/N to approve proposed changes to the consensus rules. If >75% approves with 10% quorum, they activate automatically after a lock-in period.
3. Politeia Voting, Off-chain. This is used to make project-level management decisions related to budget and policy. Tickets are selected via snapshot and tallied after 2,016 blocks, about seven days. Y/N to approve proposals. If >60% approves with 20% quorum, they pass.

Decred rewards stakeholders with 30 percent of DCR block reward, which they receive when their tickets vote on the work of a miner in each block. Ticket holders are not compensated for voting on consensus changes or in Politeia - those are rights acquired through "staking".

## Ticket Acquisition and Pricing

Within each Decred block, stakeholders can purchase tickets (current price here: [explorer.dcrdata.org](https://explorer.dcrdata.org/)) using Decrediton or dcrwallet.

Tickets are auctioned for a market price, which is determined by an algorithm that aims to keep the ticket pool size (the total amount of tickets in the PoS system) at 40,960. The target size was selected to ensure that tickets would have a 99.5% chance of voting before they expire.

- The ticket price goes up or down according to the demand for tickets and the number of tickets currently in the pool.
- The algorithm adjusts the ticket price every 144 blocks. (~12 hours, as 144 blocks x 5 minutes per block ~= 12 hours)
- When purchased, in addition to the ticket price, a ticket fee is taken to incentivize the miner to include the transaction in the block.
- Tickets are sold as immature and enter the mempool. They cannot vote for 256 blocks (about 20 hours based upon 5 minute blocks).
- After 256 blocks, a ticket matures, enters the Ticket Pool, and is eligible for voting.

## Block Voting

Block voting is a mechanism for stakeholders to check or approve the work of the miners on the previous block. If a block is rejected by voters the regular transaction tree is stripped out, but voters still get their reward.

- Each block pseudorandomly calls five (5) tickets to vote to approve the work of the miners.
- When a ticket is called to vote, the ticket-owning wallet must be online or the ticket will be marked as "missed" and the owner will not receive a reward for that ticket.
- In practice, Solo Voters often run voting wallets on a number of servers on different continents, to minimize the chance of their tickets missing a call to vote.
- Alternatively, stakers can delegate the act of voting to a Voting Service Provider (VSP), who ensures that uptime is high to not miss votes. VSPs are non-custodial, and the user sets their own voting preferences.
- When a ticket votes, the funds (ticket price + block reward component - ticket fee) will enter immature status for another 256 blocks, after which they are again available. The block reward for each ticket is 6% of the total block reward (thirty percent/five tickets).
- The average ticket age 28 days when called. Tickets are staked (locked up) for up to 142 days, at which point, a ticket expires if it has not been called, and the funds are returned to the wallet.
- The ticket price is always refunded, no matter if your ticket votes, misses, or expires.

## On-Chain Consensus Change Process

Tickets are also used to vote on consensus rules, which are technical changes to the way the network protocol functions. Every full node participating in the Decred network must enforce these rules when considering the validity of blocks and transactions.

Some examples of possible rule changes include:

- Increase the maximum block size.
- Change the algorithm PoS uses to determine the ticket price.
- Vote on major new features for Decred (e.g. Lightning Network, enhanced privacy).
- Change the PoW algorithm.
- Anything the community decides would be in the best interest of Decred.

Nodes attempting to use consensus rules differing from the majority of the network will not be able to properly validate the blockchain. Decred's built-in upgrade mechanism allows consensus rules to be changed across the entire network in a coordinated fashion. The rules are changed predictably, without hard forks and the associated possibility of a community split. Since blocks require 3 of out 5 votes to be valid, any attempt to split from the chain without majority stakeholder support is futile.

The process is as follows:

1. A proposal is made in Politeia describing and explaining the changes. See Off-Chain Voting on Politeia for details on this process.
2. Once approved in Politieia, new node software reflective of the changes is developed and released. It will lie dormant until formally voted upon on chain by PoS voters.
3. Proof-of-Work miners and Proof-of-Stake voters must upgrade to the new software. This is considered complete when 95% of the most recent 1,000 blocks are work mined and 75% of the voters cast in a single stake version have the latest vote version.
4. When this happens, on-chain consensus voting is opened up on the next rule change interval (RCI). A RCI is a fixed period of 8,064 blocks (~4 weeks). During this period, all participants in the Decred network must upgrade their software to the latest version.
5. On-Chain Consensus Voting
   - During the RCI, ticket holders will set their voting preferences within their wallet (yes, no, or abstain).
   - For each block, five tickets are randomly pulled to vote on the consensus change per their vote settings. Given the 8,064 blocks of the RCI, a maximum of 40,320 votes will be made.
   - This vote block interval was deliberately selected to be close to 40,960, allowing for a good sampling of the voters and ensuring the vote reflects the stakeholder preferences.
   - The quorum requirement is 10%, meaning at least 10% of all called tickets must be cast as non-abstain for the outcome to be valid.
     * If quorum is not met, the agenda vote remains active for the next RCI.
     * If the quorum requirement is met and more than 75% of the votes are in favor, the proposal passes.
     * If quorum is met and 75% vote No, the agenda fails and does not activate.
     * If quorum is met and neither No nor Yes fail to receive 75% support, the agenda vote remains active for the next RCI.
6. Rule activation: If quorum is met and 75% or more vote yes, a lock-in period begins. During the next 8,064 blocks, all participants in the network MUST upgrade their software to the latest version. Any nodes still running the old software will no longer be able to participate.

The process allows Proof-of-Stake voters to exercise sovereignty over whether or not to accept the proposed changes. All full nodes participating in the network will automatically activate the new rules on the first block after this period.

## Off-Chain Voting on Politeia

Politeia is an off-chain governance system that enables the stakeholders to manage Decred's budget and Decred's policy. Proposals to date include new software features, marketing expenditures, partner integrations, contractor management, bug bounty, and research. Politeia uses dcrtime to cryptographically verify identities and record all activity, managing the submission, discussion and voting of proposals.

- The principle of individual stakeholder voting is the foundation of Decred's approach to decision-making.
- Tickets can be used to cast a vote for or against each open Politeia proposal.
- Any DCR holder can submit a proposal on how to allocate the project's self-funded Treasury or to guide policy.

### How Politeia Works

- A proposal is submitted, then reviewed by Politeia admins to ensure it is nominally well-informed and does not contain any notably objectionable content.
- A complete proposal explains what, why, by whom, and over what timeframe.
- Valid proposals are published publicly on Politeia, and open for discussion.
- Community members are able to ask questions and make comments in a public forum.
- Comments and proposals are time-stamped into the Decred blockchain using dcrtime utility and cryptographic keys linked to user accounts to verify identities.
- In response to community feedback, an owner can edit a proposal.
- Once voting starts, the ticket-voting interval is 2,016 blocks (~1 week).
- A snapshot of the live ticket pool is taken at 256 blocks prior to the start of voting.
- Every ticket in the pool when this snapshot was taken can vote 'Yes' or 'No' on the proposal using their Decrediton wallet or command line dcrwallet.
- Tickets bought after the snapshot cannot vote on the proposal.
- If a ticket is called to vote on-chain during the ticket-voting interval to validate a block or vote on consensus rule changes, it still has until the end of the ticket-voting interval to vote on the proposal.
- When the ticket-voting period ends, the proposal is formally approved or rejected. A quorum of 20% of the eligible tickets is required to vote 'Yes' or 'No,' and a proposal needs 60% 'Yes' votes to be approved.
