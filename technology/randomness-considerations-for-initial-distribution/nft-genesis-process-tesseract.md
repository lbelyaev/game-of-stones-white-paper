# NFT Genesis Process (Tesseract)

NFT (token ID) genesis process for Genesis Tesseracts is as follows

![](https://lh6.googleusercontent.com/j63qe1zjDcgqA6Uz\_dWr7ZfEm1R4oTG\_dalP1R9gw3sqrFzteum8cW75DDHFo688OwZeczHvWNz1gUkI1WuOF2OL\_BPw79\_2BjuMNue90FhThaS8zvwQkGYQt4wfE0vZpHp2aDf\_)

Genesis mint consists of the following steps:&#x20;

* generation of 10,000 pseudo-random numbers (variants) that are used as inputs of the context-free art generation tool ([https://www.contextfreeart.org](https://www.contextfreeart.org)) (using a specific program for each type of artifact). Art generation process yields 10,000 original pictures of the artifacts (they will be considered etalon images) and will be used in NFT metadata as their image representation.&#x20;
* Each of 10,000 original pictures is then hashed to derive RIPEMD-160 hash (a 20-byte string) that uniquely represents an NFT.&#x20;
* Obtained artifact hashes are fed into feature extraction process that looks for certain math-related occurrences inside decimal representation of hash, such as: \
  \-- Repeated number patterns (111, 222, etc.) \
  \-- Fibonacci numbers \
  \-- Prime numbers of special (rare) types&#x20;
* Extracted features, together with artifact type and artifact hash form the final Token ID which will identify artifacts on blockchain
