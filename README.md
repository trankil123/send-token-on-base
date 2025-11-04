# Send Token on L2

Deploying Send token to Base using Optimism Standard Bridge.

## Deploying

### Provide ETH to Send Deployer on Anvil

```shell
cast send --rpc-url http://localhost:8546 \
            --unlocked \
            --from 0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266 \
            0x647eb43401e13e995d89cf26cd87e68890ee3f89 \
            --value 10ether
```

### Deploy SendToken on Anvil using `forge create`

```shell
forge create src/SendToken.sol:SendToken \
  --rpc-url http://localhost:8546 \
  --from 0x647eb43401e13e995d89cf26cd87e68890ee3f89 \
  --keystore ~/.foundry/keystores/send_deploye
```

### Deploy SendToken on Anvil using `forge script`

```shell
forge script ./script/DeployOptimismSendToken.s.sol:DeployOptimismSendTokenScript \
  -vvvv \
  --rpc-url http://localhost:8546 \
  --sender 0x647eb43401e13e995d89cf26cd87e68890ee3f89 \
  --froms 0x647eb43401e13e995d89cf26cd87e68890ee3f89 \
  --keystores ~/.foundry/keystores/send_deployer
```

## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

- **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
- **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
- **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
- **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

<https://book.getfoundry.sh/>

## Usage

### Build

```shell
forge build
```

### Test

```shell
forge test
```

### Format

```shell
forge fmt
```

### Gas Snapshots

```shell
forge snapshot
```

### Anvil

```shell
anvil
```

### Deploy

```shell
forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
cast <subcommand>
```

### Help

```shell
forge --help
anvil --help
cast --help
```
.
