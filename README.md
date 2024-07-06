## Instructions
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

The test forks mainnet so as to interact with contracts on a real network and also give a more realistic experience. Go to [Alchemy](https://alchemy.com) or [infura](https:/infura.io) 
to get `your_mainnet_rpc_url`.
```shell
$ forge test --fork-url <your_mainnet_rpc_url> --match-path test/<test_filename> 
```

#### Test Your RPC with HelloWorld Puzzle

Run the following command:
```shell
$ forge test --fork-url <your_mainnet_rpc_url> --match-path test/HelloWorld.t.sol
```
If the test passes, RPC is working, else, it might have exceeded its rate limit or typo in the url.

## Additional Resources
- [Foundry Docs](https://book.getfoundry.sh/)
- [UniswapV2 Docs](https://docs.uniswap.org/contracts/v2/overview)
- [Solidity Docs](https://soliditylang.org/)