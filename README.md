# Farming-as-a-Service Smart Contract

## Description
This project is a **Farming-as-a-Service** smart contract built using **Move** for the **Aptos blockchain**. It enables users to create farming pools and stake tokens securely and transparently.

## Vision
Our goal is to provide a decentralized and efficient farming protocol where users can stake tokens with ease. By leveraging the security and efficiency of the Aptos blockchain, we aim to create a seamless experience for yield farming and staking.

## Future Scope
- **Reward Distribution**: Implement automatic reward distribution for stakers.
- **Unstaking Mechanism**: Allow users to withdraw their staked tokens.
- **Governance Integration**: Enable community-based governance for managing farming pools.
- **Multi-Token Support**: Extend the contract to support multiple staking tokens.

## Contract Details

### 1. `create_farming_pool(owner: &signer)`
- Initializes a new farming pool for the `owner`.
- Sets the initial `total_staked` to `0`.
- Uses `move_to` to store the pool under the owner's account.

### 2. `stake_tokens(staker: &signer, pool_owner: address, amount: u64) acquires FarmingPool`
- Transfers `amount` of **AptosCoin** from the `staker` to the `pool_owner`.
- Updates `total_staked` value in the `FarmingPool`.

## How It Works
1. A user calls `create_farming_pool` to set up a new staking pool.
2. Other users can call `stake_tokens` to deposit their tokens into the pool.
3. The smart contract maintains the total amount of tokens staked in each pool.

## Dependencies
- `aptos_framework::signer`
- `aptos_framework::coin`
- `aptos_framework::aptos_coin::AptosCoin`

## Example Usage
1. **Create a farming pool:**
   ```move
   create_farming_pool(&signer);
   ```
2. **Stake tokens in a pool:**
   ```move
   stake_tokens(&signer, pool_owner_address, 100);
   ```

## License
This contract is open-source and free to use under the MIT License.

