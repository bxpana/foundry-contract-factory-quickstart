https://docs.zksync.io/build/zksync-101/contract-factory

`forge build --zksync` works:
```
[⠃] Using zksolc-1.5.1
[⠊] Compiling (zksync)
[⠔] Compiling 22 files with ZkSolc 0.8.24
[⠒] ZkSolc 0.8.24 finished in 6.67s
Compiler run successful!
```

`forge create src/CrowdfundFactory.sol:CrowdfundingFactory --factory-deps src/CrowdfundingCampaign.sol:CrowdfundingCampaign --account myKeystore --sender 0x8Ee042243f2d2ce5EFBEa796fE9e11e78B95Fdf1 --rpc-url zkSyncSepoliaTestnet --chain 300 --zksync`

Does not work, gives me:
```
error: unexpected argument '--factory-deps' found

  tip: a similar argument exists: '--force'

Usage: forge create --force <CONTRACT>

For more information, try '--help'.
```

there is no need to pass `--factory-deps` anymore, but tried:

```
forge create src/CrowdfundFactory.sol:CrowdfundingFactory --account myKeystore --sender 0x8Ee042243f2d2ce5EFBEa796fE9e11e78B95Fdf1 --rpc-url zkSyncSepoliaTestnet --chain 300 --zksync
```

and got:

```
error: unexpected argument '--sender' found

  tip: a similar argument exists: '--ledger'

Usage: forge create --account <ACCOUNT_NAME> --ledger <CONTRACT>

For more information, try '--help'.
```