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

## BurnLiquidityWithRouter.sol
1. In UniswapV2, to burn your LP tokens and get back the liquidity provided, somewhere in the code we need to transfer the LP tokens from our contract to the pair contract for it to burn and transfer back our share of liquidity provided. Where in the UniswapV2 codebase do we find the function that does this? Hint: Check the periphery contracts.
2. In the previous question, i.e `BurnLiquidity.sol` we didn't have to call ERC20's `approve` to anyone to use LP tokens on our behalf, while in this question, we have `approve` to someone to perform necessary actions to burn our liquidity. Why did we use `approve` here and not in the previous question?

## SimpleSwap.sol
1. The `swap()` function in `UniswapV2Pair.sol` has multiple sanity and security checks in places to make sure there are no errors involved. What is the significance of line 169 in the contract i.e `require(to != _token0 && to != _token1, 'UniswapV2: INVALID_TO');`? What are the possible errors faced if this line of code is not present in the contract?
2. What is the reason to use two local variables `_token0` and `_token1` at line 167 and 168, inside the `swap()` in `UniswapV2Pair.sol` rather than just using the `token0` and `token1` state variable?
3. Let's suppose we decide to increase the swap fee from 0.3% to 0.5%. What changes in the `swap()` would we make to reflect this fee change? 