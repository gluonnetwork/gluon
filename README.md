# Gluon Plasma

Gluon Plasma is plasma for non-custodial exchanges. 

<p align="center"><img src="https://rawgit.com/bharathrao/gluon (fetch/master/svgs/592291f659f40ecacb466c9762a854d7.svg" align=middle width=792.96855pt height=154.52052pt/></p>

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
2. Deposits to the main chain of an asset by user increase the user’s asset balance on the plasma sidechain by a corresponding amount.
3. Withdrawing funds from the plasma sidechain decrease the balance on the sidechain and enables withdrawal on the main chain.
4. Transfer of assets (trading) between users on the plasma sidechain require matching signed orders of the users, countersigned by the operator.
5. All state changes require accompanying witnesses. Any invalid witness can be used to halt the plasma sidechain and let users withdraw at leisure.
6. In the event of data unavailability, participants can vote to halt the sidechain,enabling users to withdraw on the main chain at leisure.

# Protocol
### Warning: This is not safe without the fraud proofs. Read full paper.


## Deposit

1. Account A transfers quantity N of asset Z to plasma contract C.
2. C computes the designated G-block G in which this deposit would be committed on the plasma sidechain.
3. C computes and stores hash H of(A, Z, N, G, nonce).
4. Operator X creates a ledger entry D referencing H and crediting N amount of Z to A. A can trade once D is published.
5. Operator X commits an ordered Merkle root depositRoot of all deposits for G-block G. Any ignored deposits need to be reclaimed by the user.

## Reclaim Deposit 
1. A submits (A, Z, N, G, nonce) with exclusion proof (H /∈ depositRoot).
2. C computes hash H of (A, Z, N, G, nonce) and verifies that H has not already been reclaimed and has been excluded from depositRoot of G.
3.C marks H as reclaimed and transfers quantity N of asset Z to account A.

## Withdrawal

1. Account A submits a signed withdrawal request for quantity N of asset Z to operator X off-chain.
2. Operator X creates a Withdraw ledger entry W that reflects the new reduced balance of(A, Z) and publishes it. A can withdraw once W is in a confirmed G-block.
3.A submits W with inclusion proof(W∈ledgerRoot) to plasma contract C.
4. C verifies W is valid and has not been already processed. C stores hash of W to prevent duplicate withdrawals and sends N quantity of Z to A on main chain.
5. If W is not published within a reasonable time (griefing attack by X), A should cancel all open orders for Z and proceed to Exit Asset Balance.

## Exit Asset Balance

1. Account A submits ledger entry E for Asset Z with inclusion proof (E∈balanceRoot) of the last confirmed G-block to plasma contract C.
2. C registers the exit claim for E in G-block Gi.
3. Operator X cancels all open orders  and prevents further activity for(A, Z).
4. After k G-blocks, A submits proof of unchanged balance in the unconfirmed G-block Gi+k. (e∈G.balanceRoot;e∈Gi+k.balanceRoot).
5. C transfers balance of Z to A on main chain and marks(A, Z) as Exited by storing ExitBlock(A, Z) =Gi+k thus preventing all further activity for(A, Z).

### See full paper for rest.


