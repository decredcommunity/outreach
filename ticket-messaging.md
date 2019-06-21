Decred Ticket-Holder Voting
 
Decred employs a hybrid PoW (Proof of Work) + PoS (Proof of Stake) consensus system. Not only does this make the network more secure than a conventional proof-of work system, but the staking component allows everyone in the community, not just miners, to participate in making the rules.
 
Decred’s governance is based on the principle of ticket-holder voting. Ticket holders forego liquidity and time-lock, or “stake”, their dcr in order to acquire the right to participate through voting in three ways: 
1. On-chain to approve the work of the miners for each block
2. On-chain consensus rule change proposals
3. Off-chain project management-Politeia system manages budget and policy
 
Decred rewards stakeholders with 30 percent of DCR block reward, which they receive when their tickets vote on the work of a miner in each block. Ticket holders are not compensated for voting on consensus changes or in Politeia--those are rights acquired through “staking”.
 
Ticket Acquisition and Pricing 
* Within each Decred block, an average of 5, and up to 20 tickets are available for purchase (current price here: stats.decred.org). This is done in a Decrediton or dcrwallet. 
* Tickets are auctioned for a market price, which is determined by an algorithm that aims to keep the ticket pool size (the total amount of tickets in the PoS system) at 40,960. The target size was selected to ensure that tickets would have a 99.5% chance of voting before they expire.
* The ticket price goes up or down according to the demand for tickets and the number of tickets currently in the pool. 
The algorithm adjusts the ticket price every 144 blocks. 
* When purchased, in addition to the ticket price, a ticket fee is taken to incentivize the miner to include the transaction in the block.
* Tickets are sold as immature and enter the mempool. They cannot vote for 256 blocks (about 20 hours based upon 5 minute blocks).
* After 256 blocks, a ticket matures, enters the Ticket Pool, and is eligible for voting.
 
Block Voting
* Each block pseudorandomly calls five (5) tickets to vote to approve the work of the miners. 
* When a ticket is called to vote, the ticket-owning wallet must be online or the ticket will be marked as “missed” and the owner will not receive a reward for that ticket. 
* In practice, Solo Voters often run voting wallets on a number of servers on different continents, to minimize the chance of their tickets missing a call to vote.
* Alternatively, stakers can delegate the act of voting to a Voting Service Provider (VSP), who ensures that uptime is high to not miss votes.
* When a ticket votes, the funds (ticket price + block reward component — ticket fee) will enter immature status for another 256 blocks, after which they are again available. The block reward for each ticket is 6% of the total block reward (Thirty percent/five tickets).
* The average ticket age 28 days when called. Tickets are staked (locked up) for up to 142 days, at which point, a ticket expires if it has not been called, and the funds are returned to the wallet. 
* The ticket price is always refunded, no matter if your ticket votes, misses, or expires. 
 
 
On-Chain Consensus Change Process
Tickets are also used to vote on consensus rules, which are technical changes to the way the network protocol works. Every full node participating in the Decred network must enforce these rules when considering the validity of blocks and transactions.
 
Some examples of possible rule changes include:
* Increase the maximum block size.
* Change the algorithm PoS uses to determine the ticket price.
* Vote on major new features for DCR (e.g. Lightning Network, enhanced privacy).
* Change the PoW algorithm.
* Anything the community decides would be in the best interest of Decred.
 
Nodes attempting to use consensus rules differing from the majority of the network will not be able to properly validate the blockchain. They will not be able to participate and will eventually end up operating on their own separate network (e.g. hard fork). Decred’s built-in upgrade mechanism allows consensus rules to be changed across the entire network in a coordinated fashion. This enables the rules to be changed predictably, without fracturing the network. The process is as follows:
 
1. A proposal is made in Politeia describing and explaining the changes. See Off-Chain Voting on Politeia for details on this process)
2. Once approved, new node software reflective of the changes is developed and released. It will lie dormant until formally voted upon on chain by PoS voters.
3. Proof-of-Work miners and Proof-of-Stake miners must upgrade to the new software. This is considered complete when 95% of the most recent 1,000 blocks are work mined and 75% of the most recent 1,000 blocks are stake mined with the latest version. 
4. When this happens, on-chain consensus voting is opened up on the next rule change interval (RCI). A RCI is a fixed period of 8,064 blocks (~4 weeks). During this period, all participants in the Decred network must upgrade their software to the latest version.
5. On-Chain Consensus Voting
	* During the RCI, ticket holders will set their voting preferences within their wallet (yes, no, or abstain).
	* For each block, five tickets are randomly pulled to vote on the consensus change per their vote settings. Given the 8,064 blocks of the RCI, a maximum of 40,320 votes will be made.
	* This vote block interval was deliberately selected to be close to 40,960, allowing for a good sampling of the voters and ensuring the vote reflects the stakeholder preferences.
	* The quorum requirement is 10%, meaning at least 10% of all called tickets must be cast as non-abstain for the outcome to be valid. 
		* If quorum is not met, the agenda vote remains active for the next RCI.
		* If the quorum requirement is met and more than 75% of the votes are in favor, the proposal passes
		* If quorum is met and 75% vote No, the agenda fails and does not activate.
		*If quorum is met and neither No nor Yes fail to receive 75% support, the agenda vote remains active for the next RCI.
6. Rule activation-If quorum is met and 75% or more vote yes, a lock-in period begins.   During the next 8,064 blocks, all participants in the network MUST upgrade their software to the latest version. Any nodes still running the old software will no longer be able to participate.
 
The process allows proof-of-stake voters to exercise sovereignty over whether or not to accept the proposed changes. All full nodes participating in the network will automatically activate the new rules on the first block after this period. 

Off-Chain Voting on Politeia
Politeia is an off-chain governance system that enables the stakeholders to manage the spending of Decred’s Treasury and Decred’s policy. Proposals to date include new software features, marketing expenditures, partner integrations, contractor management, bug bounty, and research.Politeia uses dcrtime to cryptographically verify identities and record all activity, managing the submission, discussion and voting of proposals.
	* The principle of stakeholder voting is the foundation of Decred’s approach to decision-making. 
	* While tickets are live, they can be used to cast a vote for or against each open Politeia proposal.
	* Any DCR holder can submit a proposal on how to allocate the project’s self-funded Treasury or to guide policy. 
 
How Politeia Works
* A proposal is submitted, then reviewed by Politeia admins to ensure completeness and spam. 
* Valid proposals are published publicly on Politeia. They are open for discussion. 
* Community members are able to ask questions and make comments in a public forum using dcrtime to cryptographically verify identities. 
* In response to community feedback, an owner can edit a proposal. 
* If a proposal becomes clearly inactive (proposal owner stops commenting or does not authorize the start of voting), an admin may mark the proposal as ‘Abandoned.’ 
* Abandoned proposals appear in the ‘Abandoned’ tab on Politeia. They are publicly viewable, but cannot be edited, commented on, or authorized to vote. An admin can mark a proposal as abandoned at any time before the proposal owner authorizes voting. 
* Once the proposal owner authorizes voting on a proposal, it cannot be abandoned unless the proposal owner revokes voting on the proposal.
* When the proposal owner authorizes voting to start, an admin will initiate the voting process.
* The ticket-voting interval is 2016 blocks (~1 week). 
* A snapshot of the live ticket pool is taken at 256 blocks prior to the start of voting. 
* Every ticket in the pool when this snapshot was taken can vote 'Yes' or 'No' on the proposal using their Decrediton wallet or cli. 
* Tickets bought after the snapshot cannot vote on the proposal. If a ticket is called to vote on-chain during the ticket-voting interval (to validate blocks or vote on consensus rule changes), it still has until the end of the ticket-voting interval to vote on the proposal.
* When the ticket-voting period ends, the proposal is formally approved or rejected. A quorum of 20% of the eligible tickets is required to vote 'Yes' or 'No,.' and a proposal needs 60% 'Yes' votes to be approved.
 
###
