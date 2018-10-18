# Gluon Plasma

Gluon Plasma is plasma for non-custodial exchanges. 

## Your feedback, especially security feedback, is VERY important.

# Benefits

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

etc. etc. most of the UX has been straightened out.

# Features

1. Account based
2. Small footprint
3. Instant finality
4. Fast withdrawals
5. Compact fraud-proofs for every transition
6. Non-Onerous safety
7. Congestion tolerant
8. Incentive balanced
9. Chain halt on data unavailability

# Outline

1. Gluon plasma starts with a known zero state where all balances are zero.
2. Deposits to the main chain of an asset by user increase the user’s assetbalance on the plasma sidechain by a corresponding amount.
3. Withdrawing funds from the plasma sidechain decrease the balance on thesidechain and enables withdrawal on the main chain.
4. Transfer of assets (trading) between users on the plasma sidechain requirematching signed orders of the users, countersigned by the operator.
5. All state changes require accompanying witnesses. Any invalid witness canbe used to halt the plasma sidechain and let users withdraw at leisure.
6. In the event of data unavailability, participants can vote to halt the sidechain,enabling users to withdraw on the main chain at leisure.

