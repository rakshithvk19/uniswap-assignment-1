## AddLiquid.sol
This question focuses on providing liquidity to an existing pool in the ratio provided.
Here are a few questions to think about and research.
1. Why does Uniswap use state variables like `balance0` and `balance1` to capture the value of amount of tokens the pool stores? Why can't it use ERC20's `balanceOf()` each time to fetch the balance of each token held in the pool?
2. If the pool addresses are already present in onchain, what are the implications of transfering tokens to that pool? Can the tokens transferred recovered back?