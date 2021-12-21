# NFT Genesis Process (Keys)

NFT (token ID) genesis is as follows

![](https://lh4.googleusercontent.com/JwpSUy3l2ZCF4eOOqvyrhYKXI9q65LoKHvXYC3sbPRFlYO4T2bWtYFJbxyya1UQM72FqthifDM5Dp2Z8bWc\_fi\_S8NPGW7vn-xkvopi5-XqYK-y5vJSepI93rUNqo24bt3N67IB5)

Genesis mint consists of the following steps:&#x20;

* generation of 10,000 pseudo-random numbers.&#x20;
* Each of 10,000 original numbers is then hashed to derive RIPEMD-160 hash (a 20-byte string) that uniquely represents an NFT.&#x20;
* Obtained artifact hashes are fed into feature extraction process that looks for certain math-related occurrences inside decimal representation of hash, such as: \
  \-- Repeated number patterns (111, 222, etc.) \
  \-- Fibonacci numbers \
  \-- Prime numbers of special (rare) types&#x20;
* Extracted features, together with artifact type and artifact hash form the final Token ID which will identify artifacts on blockchain
