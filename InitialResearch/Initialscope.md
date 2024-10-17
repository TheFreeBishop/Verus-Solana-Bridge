# Initial Research
To see if it is even possible to do the bridge,  It would involve.

## EST1
- Look at the Solana proof system and document how they do proofs for transactions. Answer can we get a proof and how we would do it. E.g. For Verus its each transaction is hashed in a MMR using the blake2b hashing function, up to a stateroot, this is done in the daemon so there is no gas costs when processing any tx.  A transaction is made up from defined objects that are then hashed in a deterministic way. To get a proof one just gets the Merkle mountain range index the transaction was in and all the proof hashes, then hash it up to the stateroot.

NOTE:  Type into chat gpt  on solana if you sent some data into a smart contract, how could you for example in x number of blocks time get a proof to the state root that that data was in the account and mined into a particular block
This mentions: (Dont take this chatgpt as being true but as a guide) 
Steps to Retrieve Proof:
- Use getConfirmedTransaction to fetch the transaction and confirm it was included in a block.
- Use getBlock to verify the block details, including the slot and blockhash.
- Use getAccountInfo to verify the state of the account where the data was stored.
- Use logs (if enabled) to show that the contract updated the state at the time of the transaction.

## EST2
It doesnt mention how the transactions in a block are hashed to produce the blockhash, this would have to be done in Verus to verify any transaction occurred on solana when coming over to Verus. Also it mentions data is not persistent and we may need to use an indexer so the next point is. How would we implement indexers.

## EST3
Check to see how a state root can be stored in Solana from Verus e.g. on Ethereum a smart contract takes in the serialized notarization,  with a bunch of signatures for known notarizers. the Ethereum contract checks all the signatures are unique and there is 8 or more of the 15 witnesses signatures present in the proof, if all signatures are unique and are not known to the smart contract, then proceed to process the notarization, by checking it against the last one (i.e. are they chained together, is the block number > the previous etc.  If so store in global storage. Document how the Solana smart contract would store the notarizations in the contract, would the solanda 10MB of data limit be an issue if not why not.  How much rent would be needed to pay to store the data, how can we be sure the data is never lost? how can data accounts be updated by any of the 15 notaries

## EST4
Check to see how Solana would verify Verus signatures using ecrecover and define how.

## EST5
Check to see if solana is compatible with Verus transactions. Verus uses blake2b hashing algo so any code on solana would have to be able to deserialize transactions from their serialized form, as well as hash the initial data. Describe how a Verus transaction would be processed

## EST6
Check what hashing algo Solana uses and check how the Verus daemon would be modified to handle the hashing Algo.

## EST7
Define and choose programming language to be used for each module, bridge keeper software, accounts people would have to have, smart contract lauanguage?