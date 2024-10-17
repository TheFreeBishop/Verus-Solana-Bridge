## Scope
Look at the Solana proof system and document how they do proofs for transactions. Answer can we get a proof and how we would do it. E.g. For Verus its each transaction is hashed in a MMR using the blake2b hashing function, up to a stateroot, this is done in the daemon so there is no gas costs when processing any tx. A transaction is made up from defined objects that are then hashed in a deterministic way. To get a proof one just gets the Merkle mountain range index the transaction was in and all the proof hashes, then hash it up to the stateroot.
NOTE: Type into chat gpt on solana if you sent some data into a smart contract, how could you for example in x number of blocks time get a proof to the state root that that data was in the account and mined into a particular block This mentions: (Dont take this chatgpt as being true but as a guide) Steps to Retrieve Proof:

Use getConfirmedTransaction to fetch the transaction and confirm it was included in a block.
Use getBlock to verify the block details, including the slot and blockhash.
Use getAccountInfo to verify the state of the account where the data was stored.
Use logs (if enabled) to show that the contract updated the state at the time of the transaction.

## Findings


.........