# Overview

`TokenLocker` allows users to deposit mUSD into the contract. Once the contracts mUSD balance reaches the minimum threshold, any user who had previously deposited may call the `batchExecute` function to send the pool of funds to the `SavingsContract`. The execution timestamp is cached to enable locking functionality. `Withdraw` may only be called by users with deposit history and will revert if called before the execution timestampe + 6 months (183 days).

## Getting Started

You'll need to have foundry installed to run tests

```shell
curl -L https://foundry.paradigm.xyz | bash
```

Run `foundryup` to install the latest version

## Installing Dependencies

Run while in `test/savings/foundry-tests`

```shell
forge install
```

Compile:

```shell
forge build
```

## Running Tests

The tests will only run on a fork of Ethereum mainnet. Foundry makes it easy to run tests against a fork and does not require exposing endpoints in an environment variable.

It is recommended to run tests with all 5 verbosit flags to get a full view of stack traces and event logs.

```shell
forge test --fork-url <your mainnet endpoint> -vvvvv
```
