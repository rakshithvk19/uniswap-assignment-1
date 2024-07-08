## AddLiquid.sol
This question focuses on providing liquidity to an existing pool in the ratio provided.
Here are a few questions to think about and research.
1. Why does Uniswap use state variables like `balance0` and `balance1` to capture the value of amount of tokens the pool stores? Why can't it use ERC20's `balanceOf()` each time to fetch the balance of each token held in the pool?
2. If the pool addresses are already present in onchain, what are the implications of transfering tokens to that pool? Can the tokens transferred recovered back?
3. In this question we are using wETH instead of ETH, So what is wEth(Wrapped ETH)? What is it used for and how is it different from ETH? Is that a coin or a token?

## AddLiquidityWithRouter.sol
1. If one explores the official GitHub repo of UniswapV2, we find 3 contracts present in the periphery contracts. We find an older version of router contract called `UniswapV2Router01.sol`. What was the reason for not using `UniswapRouter01.sol` and why is another `UniswapV2Migrator.sol` present? Google for audit reports of UniswapV2.
2. In the assignment, the `IUniswapV2Router` has `amountTokenMin` and `amountETHMin` as params for `addLiquidityETH` method, what is the reason for having this parameter? What does it protect againest?

## BurnLiquidity.sol
1. Foundry is a smart contracts development framework that is written in rust. It offers a set of tools called FOUNDRY CHEAT CODES which is used to test how your contract reacts to specific conditions in on the blockchain. What are the set of cheatcodes used for this exercise and what does it simulate?
2. Beforing burning the LP tokens, we need to transfer it back to the LP tokens for it burn. Would we use ERC20's `transfer()` or `trasferFrom()` to perform this action? Why are we using one over the other? 
3. What is the significance of `sync()` in `IUniswapV2Pair`? What issues does it potentially prevent?