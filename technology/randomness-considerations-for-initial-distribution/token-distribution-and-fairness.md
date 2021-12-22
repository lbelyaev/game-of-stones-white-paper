# Token distribution and fairness

One of the major factors of success of a NFT project is fair and unbiased distribution of mass-minted NFTs. Our approach is as follows:&#x20;

* Pre-sell 20,000 of ‘Genesis mint tickets’ (or the minimum threshold number, as decided)&#x20;
* Commit on-chain several important genesis parameters (for further audit/verification purposes)&#x20;
* Perform off-chain genesis generation of the artifacts. Compute a Merkle tree of all generated Token IDs, in the order of their generation, and commit the Merkle root of the tree on-chain. This will serve the proof of having initial random distribution of Token IDs&#x20;
* Using Chainlink VRF Oracle, obtain and commit on-chain a random number, that will be used as a shift position for Token IDs distribution&#x20;
* Using gas-saving batch transactions mint NFTs on-chain, using the following: \
  \-- Ordered list of generated TokenIDs in the off-chain Genesis pool (committed on-chain via Merkle root) \
  \-- Ordered list of Genesis mint tickets, as they arrived on-chain \
  \-- Obtained shift position (0 - 19,999) for a random offset to select TokenID corresponding to entry ticket’s serial number \
  \-- Each NFT Mint transaction also contains Merke proof that confirms that Token ID was part of genesis generation&#x20;

The shift of minting order is analogous to shifting of a card deck (by a third person) after it has been shuffled by dealer.

The described process is detailed in the diagram below.

![](<../../.gitbook/assets/image (1) (1) (1).png>)
