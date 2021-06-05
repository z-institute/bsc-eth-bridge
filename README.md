## Run the project

```
npm install
truffle compile
```

## Steps

1. Deploy contract

```
truffle migrate --reset --network ethTestnet
truffle migrate --reset --network bscTestnet

```

2. Check token balance before transfer (the first one should be 1000 and the second one should be 0)

```
truffle exec scripts/eth-token-balance.js --network ethTestnet
truffle exec scripts/bsc-token-balance.js --network bscTestnet
```

3. Run the bridge script (keep the script opened in a separate terminal)

```
node scripts/eth-bsc-bridge.js
```

4. Transfer token (the bridge will listen to the event and do the bridging after transfer)

```
truffle exec scripts/eth-bsc-transfer.js --network ethTestnet
```

5. Check token balance after transfer

```
truffle exec scripts/eth-token-balance.js --network ethTestnet
truffle exec scripts/bsc-token-balance.js --network bscTestnet
```
