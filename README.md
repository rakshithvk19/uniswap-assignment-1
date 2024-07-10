# Objective

The objective of this assignment is to familiarize the students with the basic architecture and functionality of uniswapV2 and DEX’s in general.It has multiple code snippets that the students need to complete along with the following the best code practices which are enforced by passing test cases.

Detailed explanation of what is expected in the code snippet is provided in each of the contract code.
Students are also provided with a few research questions regarding the architecture of the uniswapV2 to help them understand why the code in modelled in a particular way. 

# Outcome

Students get to understand the functionality of Adding Liquidity, Burning Liquidity, Swapping tokens and the architecture of Uniswap V2.

# Instructions
- Git clone the assignment.
- Install Foundry and the code dependencies.
  ```shell
  forge install
  ```
- Complete the pseudo code present in the `src` direcctory. Each `.sol` file represents a concept used in UniswapV2.
- Each file also has a few research questions found [here](./Research%20Questions.md) that encourages you to explore regarding the design of the code.
- Once the pseudo code is completed, run the tests written for each particular file.
- Make sure all the test cases are passing. The test cases are written emphasising the best code practises in solidity.

### How to run tests

- The test forks mainnet so as to interact with contracts on a real network and also give a more realistic experience. Go to [Alchemy](https://alchemy.com) or [infura](https:/infura.io) 
to get `your_mainnet_rpc_url`.
- Once you get the rpc-url, create a `.env` file and add it.
- Run the following script to save your `.env` file in foundry.
  ```shell
  $ source .env
  ```
- Run tests for a particular question using the below script.   
```shell
$ forge test --fork-url <your_mainnet_rpc_url> --match-path test/<test_filename> 
```
- Do not update the test cases written to solve your code, rather write your code to pass the test cases.
- To debug the errors faced while running the tests, increase the verbosity `-vvvv` to get the stack trace of the test execution.
  ```shell
  $ forge test --fork-url <your_mainnet_rpc_url> --match-path test/<test_filename> -vvvv
  ```

#### Test Your RPC with HelloWorld Puzzle

Run the following command:
```shell
$ forge test --fork-url <your_mainnet_rpc_url> --match-path test/HelloWorld.t.sol
```
If the test passes, RPC is working, else, it might have exceeded its rate limit or typo in the url.

## Suggested Order for solving the assignment questions
- [AddLiquid](./src/AddLiquid.sol)
- [AddLiquidWithRouter](./src/AddLiquidWithRouter.sol)
- [BurnLiquid](./src/BurnLiquid.sol)
- [BurnLiquidWithRouter](./src/BurnLiquidWithRouter.sol)
- [SimpleSwap](./src/SimpleSwap.sol)
- [SimpleSwapWithRouter](./src/SimpleSwapWithRouter.sol)


## Additional Resources
- [Foundry Docs](https://book.getfoundry.sh/)
- [UniswapV2 Docs](https://docs.uniswap.org/contracts/v2/overview)
- [Solidity Docs](https://soliditylang.org/)