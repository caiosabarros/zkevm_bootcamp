## Class 1
1. Bitcoin network uses a probabilistic finality mechanism. As older the tx is, the more probable it is not invalid in the network. Ethereum and most of the current blockchains use the deterministic mechanism for finality. This means: validators validate right away whether a tx is valid or invalid. If not valid, it's not included in a block.
## Class 2
1. Solana has parallel txs. (interesting)
2. State Channels are a two-people mechanism to avoid multiple txs - therefore, avoiding multiple gas spends...Therefore, two users perform different txs and only send the result of all their different txs to the L1. This is useful for micropayments, since micropayments would require bigger gas fees than the payments being made.
3. Blocks in L2s rollups are only rolled-back iff the validity/fraud proof has proved invalidity/fraud of the block. There's a time in between the block being sent to the L1 and since it's been included in the L2, where a fraud/validity proof can be sent. Basically, these proofs are sent BEFORE the block is finalized on L1, to ensure the roll-back can happen. In general, a few hours for validity proofs to be sent before batch of txs from L2 is included on L1.
4. To clarify, the canonical bridge is the only way to withdraw money from L2. If you use other bridges, it's not a withdrawal, it's an exchange.
5. Celestia on Ethereum is where the DA concept comes in: it has all the data and makes it so that anyone can read it at anytime. For forever? Don't know about its longevity.
6. Sidechains are different from shardings in which sidechains are a different chain than the mainnet and have they own security issues. Wehreas, sharding is spliting the mainnet to allow tx parallel processing
7. Why don't we use IPFS instead of Celestia for Data Availability? Here's an answer: 
- an answer from the Matter Labs team:
"IPFS does not guarantee data will be kept around, it's a naming protocol. Filecoin does help with this somewhat, but that doesn't cover consensus that the data is accurate, just that it exists. Data availability from networks like Celestia aim to provide longevity (won't be deleted) and validity"
8. Why bother using ZK in rollups when they're not exactly needed? (question from a classmate) Answer by moderator: it's more about the "succinct" quality of zero knowledge proofs which compresses information.
9. Why Optimistic rollups are more used (currently) when compared to zk rollups? An answer from a classmate: "optimistic rollups are 'low tech' or dumb. hence were deployed very fast. zk on the other hand is harder to build, with all the circuits, etc. and was very compute intensive till a couple of years ago (but improving fast). hence optimistic rollups deployed first. however interestingly, optimistic fraud proofs implementation has taken longer than expected, so zk roll ups are gonna be more competitive faster..."

## Class 3:
- The EVM is stack-based, has mutable (Storage) and immutable(VirtualROM, which is contract's bytecode, for example) components
- The program counter tracks where we are in the bytecode of a smart contract, tracking which opcode is to be executed next.
- HH (Homormophic Encryption) refers to making calculations on encrypted data and the decrpyted result of that is as if we had performed computation in the secret itself, but in HH we do not reveal the secret.
- q: "Don't we need transaction data from the very first rollup block to compute state root?"

for zkEVMs, the proof shows validity of execution trace of a transaction, so a zkEVM like zkSync simply sends account updates to L1 (along with the proof of correct execution). These account updates can be used to compute state root in the case of sequencer failure.

## Questions:
1. Why is there a consensus mechanism if there's a built EVM compiler that does not let me move more money than I have, etc?

## Resources:
- https://notes.ethereum.org/KbEyHiaSRQW_KS7dDK0OFw (shards quick explanation)
- From Coogan: {
Hey all! One of the more challenging things for me has been finding the right resources for learning about the maths behind zkps. It can be really challenging, so I'm looking for interesting ways of presenting mathematical material to make them easier to learn.

Good examples would be something like:

https://www.youtube.com/@3blue1brown

Numberphile and Computerphile YT courses

https://www.masterclass.com/classes/terence-tao-teaches-mathematical-thinking
}
https://github.com/yt-dlp/yt-dlp (YT premium for free?
https://blog.matter-labs.io/introducing-the-zk-stack-c24240c2532a #the a at the end might have been a typo.
https://blog.celer.network/2023/08/04/the-pantheon-of-zero-knowledge-proof-development-frameworks/
https://docs.google.com/presentation/d/1UN2SYeWnK6zwDHOUy_B9JG6HNDd1sZwHEhx7M1MVRZo (zkevm security slides) - guy's from matter labs :D
https://zksync.mirror.xyz/HJ2Pj45EJkRdt5Pau-ZXwkV2ctPx8qFL19STM5jdYh 
https://www.youtube.com/watch?v=Sk-S8-n6Jo4c - ZK attack
https://twitter.com/yezhang1998/status/1627713360967139329 -- how to build  zkEVM

https://www.rollup.codes/

# RESOURCES
https://www.notion.so/encodeclub/85393f2cf9d449e0a433ae62799c1fde?v=95eeea778a10438b82ec83fbafc3eed8 (Wild database with lots of courses, lectures and stuff)
