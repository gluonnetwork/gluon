<p align="center"><img src="svgs/Gluon-Badge-520-Filled.svg" align=middle width="100px"/></p>

# Gluon Plasma

####Gluon Layer2 is a plasma variant for non-custodial exchanges and DeFi.
</br>
<b>Whitepaper:</b> 📝<a href="Gluon-Layer2.pdf">Gluon-Layer2.pdf</a></br>
<b>Grants/Bounties:</b> 💻<a href="https://gluon.network/developers/">gluon.network/developers</a></br>
<b>Issues/PRs:</b> 🐛<a href="https://github.com/gluonnetwork/whitepaper/issues/new">Improvements welcome</a></br>
<b>Community:</b> 💬<a href="https://discord.com/invite/xpsjfwn">#Developers channel</a></br>

## Benefits

1. No need to be online at time of match/payment
2. No bonds (to withdraw, etc)
3. No challenges
4. No exit games
5. No limit on number of coins
6. No main chain limit on trades in a plasma block
7. No increased gas cost for increased volume
8. No large waiting periods to withdraw (typical values: 10 mins or 60 mins)
9. No unfungibility hassles (like change providers)
10. No increase in size of proof with coin movement
11. No priority queue and stampede to exit
12. No need for everyone to verify the whole plasma chain periodically

## Features

1. Account based
2. Small footprint
3. Instant finality
4. Fast withdrawals
5. Compact fraud-proofs for every transition
6. Non-Onerous safety
7. Congestion tolerant
8. Incentive balanced
9. Chain halt on data unavailability

## Use Cases
### DEX
Gluon is purpose built for Decentralized Exchanges. Leverj, a decentralized futures exchange powered by Gluon, demonstrates the High Frequency Trading (HFT) and scalability is able to rival a centralized exchange. Anyone can look at the Leverj code base, and create a decentralized exchange that is congestion tolerant and performant.

### AMM
AMM or automated market makers are powered by a set of smart contracts that provide liquidity to markets. Gluon is looking to incentivize AMMs to join and provide liquidity as AMMs can provide liquidity across exchanges built on the Gluon Network meaning you’re not limited to one implementation.

### NFT Exchange
NFTs are becoming increasingly popular, platforms like opensea and rarible are rapidly scaling. However, they still require high fees to trade items. Unfortunately this adds an unpredictable additional cost on top of the item. This can skew profits, and makes it unnecessarily more expensive to trade. Using Gluon an NFT creator could mint their token and make it available on the Gluon chain for gasless trading. If a user decides to take out ownership and move to another market or hold it in a standard Ethereum wallet, they can execute the withdrawal function and will now have full control on the Ethereum mainnet.

### Tokenized Energy Market
Virtually any tokenized market with incentives can utilize Gluon. An energy market is one such case, where nodes or individuals who sell or lease power from solar panels for instance can quickly exchange with micro-transactions. Since this type of marketplace is high frequency, it makes sense to move to an alternative than the Ethereum mainnet. In this way you have the interoperability and fungibility of ERC20 tokens while running the main energy trading functionality on Gluon.

## Outline

1. Gluon plasma starts with a known zero state where all balances are zero.
2. Deposits to the main chain of an asset by user increase the user’s asset balance on the plasma sidechain by a corresponding amount.
3. Withdrawing funds from the plasma sidechain decrease the balance on the sidechain and enables withdrawal on the main chain.
4. Transfer of assets (trading) between users on the plasma sidechain requires matching signed orders of the users, countersigned by the operator.
5. All state changes require accompanying witnesses. Any invalid witness can be used to halt the plasma sidechain and let users withdraw at leisure.
6. In the event of data unavailability, participants can halt the sidechain, enabling users to withdraw on the main chain at leisure.

### See full paper for full specification and fraud proofs.
