1. key:98400f6a67af07025f5959af35ed653d649f745b8f54bf3f07bef9bd605ee946
2. spec:[sync-spec.toml](sync-spec.toml)
3. 1000000 cell 
4. prepare data:[data.tar.gz](..%2F..%2F..%2F..%2Fckb-bench%2Fdevtools%2Fci%2Fansible%2Ffiles%2Fbig-tx%2Fdata.tar.gz)
5. with pending tx data:
4. deploy big cycle contract ([loop_contract](loop_contract)) link:(https://github.com/gpBlockchain/ckb-test-contracts/tree/main/rust/acceptance-contracts/contracts/loop_contract)
```angular2html

const current_deploy_config: ScriptConfig = {
    CODE_HASH: '0xf14ce40e6d7190441246dbafaea9a9b187987edd8580dc699945470630fe2535',
    HASH_TYPE: 'type',
    TX_HASH: '0x4bef9489823c6e51646863b83ab03ac256f6b404450cf0042f5705cce7a24e10',
    INDEX: '0x0',
    DEP_TYPE: 'code'
}
```
5. lock contract 
```angular2html

SECP256K1_BLAKE160: {
    CODE_HASH: "0x9bd7e06f3ecf4be0f2fcd2188b23f1b9fcc88e5d4b65a8637b17723bbda3cce8",
    HASH_TYPE: "type",
    TX_HASH: "0xace5ea83c478bb866edf122ff862085789158f5cbff155b7bb5f13058555b708",
    INDEX: "0x0",
    DEP_TYPE: "depGroup",
    SHORT_ID: 0,
}
```

6. 
generate 8000 big cycle tx
```shell
CKB_BENCH_OWNER_PRIVKEY=98400f6a67af07025f5959af35ed653d649f745b8f54bf3f07bef9bd605ee946   ./ckb-bench bench     --rpc-urls http://172.31.45.113:8010     --n-users 100     --n-inout 1     --bench-time-ms 300000000000     --tx-interval-ms 0 --concurrent-requests 4     --is-smoking-test --add-tx-params contract.json | grep -v sign > run.log 2>&1 &

```
