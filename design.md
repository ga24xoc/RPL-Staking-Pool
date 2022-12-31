# Roles

## Node Operator

A Rocketpool node operator, who is using Pool RPL for their node

This is represented by:
- a node operator account (according to Rocketpool)
- with the withdrawal address set to the RPL Staking Pool withdrawal contract

State for the node operator (in the RPL Staking Pool contract storage):
- Amount of Pool-Staked-RPL staked on the node
- Node operator's withdrawal address

## RPL Staker

Someone who has deposited RPL into the RPL Staking Pool

This is represented by:
- any account that holds the Pool-Staked-RPL token

# Protocol state

- Total staked RPL backing Pool-Staked-RPL (which also determines the protocol price of Pool-Staked-RPL)
- Unstaked RPL in the pool available to be staked on nodes

# Actions

## Deposit RPL into Pool

Exchange RPL for Pool-Staked-RPL

## Withdraw RPL from Pool

Exchaneg Pool-Staked-RPL for RPL (including any staking rewards)

## Stake Pool RPL onto a node

Increase the Pool-Staked-RPL balance of the node, and stake RPL on the node

## Unstake Pool RPL from a node

Decrease the Pool-Staked-RPL balance of the node, and unstake RPL from the node

## Register a node

Set the withdrawal address to the RPL Staking Pool contract and make the node eligible for staking Pool RPL

## Change withdrawal address

Change the underlying withdrawal address

## Unregister a node

Set the withdrawal address back to the underlying and exit eligibility for the pool
