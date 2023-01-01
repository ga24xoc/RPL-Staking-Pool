# Terminology

<dl>
<dt>RPL Staking Pool (RSP)</dt>
<dd>The name of the project.</dd>

<dt>Pool-Staked-RPL (tRPL)</dt>
<dd>The token representing RPL that has been staked, or is waiting to be staked, on a Rocket Pool node from the RPL Staking Pool.</dd>

<dt>Pool RPL</dt>
<dd>RPL that has been deposited in the RPL Staking Pool (minting tRPL).</dd>
</dl>

# Roles

## Node Operator

A Rocket Pool node operator who is using Pool RPL to collateralise their node.

This is represented by:
- a node operator account (according to Rocket Pool)
- with the withdrawal address set to the RSP withdrawal contract

State for the node operator (in RSP contract storage):
- Amount of Pool RPL staked on the node
- Node operator's withdrawal address

## RPL Staker

A holder of Pool-Staked-RPL (tRPL). This is someone who has either deposited RPL into the RPL Staking Pool to mint tRPL, or who has traded into holding tRPL.

This is represented by:
- any account that holds the Pool-Staked-RPL token tRPL

# Protocol state

- Total staked Pool RPL, including rewards, that is backing Pool-Staked-RPL (tRPL)
- Total supply of tRPL
- Exchange rate between RPL and tRPL: determined by the two values above
- Unstaked Pool RPL in the pool available to be staked on nodes or redeemed by burning tRPL

# Contracts

## RSP Withdrawal Contract

Designed to be the withdrawal address for Node Operators that stake Pool RPL.
When it receives ETH and RPL rewards it sends all the ETH to the corresponding Node Operator's underlying withdrawal address, and splits the RPL between the underlying withdrawal address and the RSP Pool.

## tRPL Token Contract

## RSP Storage+Pool Contract

Stores the RSP protocol state. In particular:
- The underlying withdrawal address for each Node Operator
- The amount of Pool RPL each Node Operator is currently staking
- The amount of unstaked Pool RPL available for staking or withdrawal (this contract's RPL balance)

# Actions

## Deposit RPL into Pool

Exchange RPL for Pool-Staked-RPL

## Withdraw RPL from Pool

Exchange Pool-Staked-RPL for RPL (including any staking rewards)

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
