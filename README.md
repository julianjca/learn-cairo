# Learning Cairo

## Docs

### How to compile

```
starknet-compile contract.cairo \
    --output contract_compiled.json \
    --abi contract_abi.json
```

### How to deploy contract

```
STARKNET_NETWORK=alpha-goerli starknet deploy --contract contract_compiled.json
```

Result:

```
Deploy transaction was sent.
Contract address: 0x07d70473346f47aad49e627acfdbf0976ef219274ff3373f8ec474742edadcfe
Transaction hash: 0x64f5fe8a5bc935dd49aff4169502ebe50d9ef37575388c64f507eda022f0b1f
```

### Interacting with the contract

```
starknet invoke \
    --address CONTRACT_ADDRESS \
    --abi contract_abi.json \
    --function increase_balance \
    --inputs 1234
```

Result:

```
Invoke transaction was sent.
Contract address: 0x07d70473346f47aad49e627acfdbf0976ef219274ff3373f8ec474742edadcfe
Transaction hash: 0x37e666ff2e488c42f82920d2a90342db0947dd0cc0eab6019d963c9920476c7
```

### Checking transaction status

```
starknet tx_status --hash TRANSACTION_HASH
```

### Checking balance

```
starknet call \
    --address 0x07d70473346f47aad49e627acfdbf0976ef219274ff3373f8ec474742edadcfe \
    --abi contract_abi.json \
    --function get_balance
```
