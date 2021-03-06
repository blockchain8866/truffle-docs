# 测试合约

## 测试框架

Truffle comes standard with an automated testing framework to make testing your contracts a breeze. This framework lets you write simple and manageable tests in two different ways:

* In [Javascript](/docs/getting_started/javascript-tests) and [TypeScript](/docs/getting_started/javascript-tests#typescript-file-support), for exercising your contracts from the outside world, just like your application.
* In [Solidity](/docs/getting_started/solidity-tests), for exercising your contracts in advanced, bare-to-the-metal scenarios.

Both styles of tests have their advantages and drawbacks. See the next two sections for a discussion of each one.

## 测试用例目录

All test files should be located in the `./test` directory. Truffle will only run test files with the following file extensions: `.js`, `.ts`, `.es`, `.es6`, and `.jsx`, and `.sol`. All other files are ignored.

## 测试合约命令

To run all tests, simply run:

```
$ truffle test
```

Alternatively, you can specify a path to a specific file you want to run, e.g.,

```none
$ truffle test ./path/to/test/file.js
```

## ”干净的“ 测试环境

Truffle provides a clean room environment when running your test files. When running your tests against [Ganache](https://truffleframework.com/ganache) or Truffle Develop, Truffle will use advanced snapshotting features to ensure your test files don't share state with each other. When running against other Ethereum clients like [go-ethereum](https://github.com/ethereum/go-ethereum), Truffle will re-deploy all of your migrations at the beginning of every test file to ensure you have a fresh set of contracts to test against.

## 速度和可靠性考虑

Both Ganache and Truffle Develop are significantly faster than other clients when running automated tests. Moreover, they contain special features which Truffle takes advantage of to speed up test runtime by almost 90%. As a general workflow, we recommend you use Ganache or Truffle Develop during normal development and testing, and then run your tests once against go-ethereum or another official Ethereum client when you're gearing up to deploy to live or production networks.
