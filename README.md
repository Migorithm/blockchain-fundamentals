

## Why not just database?
- No admin
- Most blockchains are engineered to be permissionless
- Only have insert operations - inherently immutable
  - This implies that blockchains are not recursive in nature: no repeat


## Web3? 
This is quite a confusing term. This essentially means "internet of blockchains."
Until web 2.0, we had client-server architecture applications. 
As the blockchain promises more decentralized internet, now it's called web3.


## Blocks
![blocks](images/blocks.png)

- Genesis block: The first block that has no previous hash is called genesis block. 
- Hash: each block holds two hashes - previous one and its own. 
- Nonce: this stands for "number only used once." Nonce needs to be consistent with the hash for the block to be valid. If it doesn't, the following blocks go out of sync.


## Hashes
SHA-256 stands as the most popular choice within blockchains due to its robust hash security features and the notable fact that it remains unbroken to this day. 
Four properties of SHA-256:
- One-way: The hash generated from SHA-256 is 256 bits (or 32 bytes) in length and is irreversible - You cannot get plaintext back.
- Deterministic: Every time you send a particular data through the algorithm, you will get the same predictable result. This means that the hash doesn’t change for the same data.
- Avalanche effect: Changing one character of the data, completely changes the hash and makes it unrecognizable.
- Withstand collision: Collision in hashing means the algorithm produces the same hash for two different values. SHA-256 has an extremely low probability of collision

These SHA-256 properties explain why blockchains are the way they are.


## Transactions 
Let's take an example transaction fields from Bitcoin
- Version: This specifies which rules the transaction follows
- Input counter:  This is the number of inputs in the transaction (this is just a count)
- Inputs: This is the actual input data
- Output counter: This is similar to the input counter, but it’s for keeping a count of the transactions’ output
- Output: This is the actual output data from the transaction
- Blocktime: This is simply a Unix timestamp that records when the transaction happened.

Initially, blockchains were designed to record financial transactions. But transactions in the context of blockchains means:
"anything that changes the state of the blockchain"


## Distributed system and decentralization
Tranditional distributed systems had nodes and node recovery. It may sound just the same as decentralization. 
However, the former one still belongs to the centralized authority or the company. With decentralized systems, the node can be owned by
another entity, person or a company other than the company that developed the blockchain.

In fact, having nodes owned by different companies is encouraged in blockchain network. This nodes are usually monetized to stay in the network
and to uphold the security of the network.


## Nodes, validators, collators
Once a new block(set of transactions) is added, which is known as mining, this event is advertised to the entire network.
The rest of the nodes in the network now act as validators that confirm the outputs of the transactions. Once it reaches consensus, 
that block becoems "right" one to be added to the chain. Another node could be listening to all the new transactions and those tranasctions could be then collated onto a block.

The following criteria vary from blockchain to blockchain in terms of the following:
- The number of transactions that the block will store
- The mechanism that nodes use to collate the transactions (time-based or number-based)
- The validation mechanism
- The consensus mechanisms

Among these, consensus mechanism is something that is most often innovated upon.


## Consensus
Let's understand the following concepts:
- Proof of work (PoW): Nodes need to solve a particular cryptography problem. The node with the highest processing power is able to solve faster than others. So, this essentially increases electricity consumption and not considered efficient - Examples are Bitcoin and Dogecoin. 

- Proof of authority(PoA): transactions and blocks are verified by identified validators, typically chosen due to their reputation or authority. Unlike PoW, PoA offers efficiency by requiring validators to be accountable for their actions. Commonly used in private or consortium blockchains. However, it is centralized in its nature so it may raise concerns reharding censorship resistance.

- Proof of stake: nodes need to buy **stakes** in the network. Basically, they buy the cryptocurrency native to the network. Only a few nodes with a majority stake get to participate in the mining activity in some cases. This is highly energy efficient and this is the reason why Ethereum switched from PoW to PoS. But still this is less decentralized. The main benefit of PoS is that since nodes have a stake in the system, they are de-incentivized to add unscrupulous blocks to the chain. When a node tries to add the wrong block, the rest of the nodes do not validate this block, and if such a scenario takes place, these nodes are then penalized where the amount of native cryptocurrency owned by the node that is taken away can differ depending on the seriousness of the violation. Generally, this penalty entails a partial loss of funds rather than a complete forfeiture of all holdings. Some examples are Cardano, Ethereum, and Polkadot.

## Mining
When producing hash, it factors in:
- Hash from last block
- Data from transactions
- Nonce that starts from 0

This suggests that you cannot get the hash "smartly."

## Forking
We learned how SHA-256's properties provide immutability for blockchains. This means all transactions are immutable and cannot be reversed unless actual, new transactions are made that counteract the first one. 

Or, the only way to reverse previous transaction is to create an entire copy of the chain where the particular transaction didn't take place. This process is called **forking**.
**Forking** can be used when rules for the blockchain need to be modified.(Some blockchains such as Polkadot have invented mechanisms to have forkless upgrades.)

Most of the time, Forks occur intentionally, but it can happen unintentionally when multiple miners discover a block simultaneously. The reconcilation happens as additional blocks are appended, making one chain longer than the others. In this case, the network disregards blocks that are not part of the longest chain, labeling them as "orphaned."

## Governance
Every blockchain follows a unique way of governance, but, in general, blockchains are governed by token holders that can be users, developers, investors, the founding team, or nodes. Governance tokens are issued to reward the loyalty of token holders and are usually issued when they have a high stake in the network. 

Each governance token is equal to one vote, so this leads to a very fair and just system, as the holders with more stake in the network get more influence.
This may lead to "whale problem" where some network participants end up holding most of the tokens. In most cases whales are the founding team, and votes are cast to push
agenda of the founding team.
