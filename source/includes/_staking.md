# Staking

## staking-history

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking_history' \
--header 'Content-Type: application/json' \
--data-raw '{
     "row": 20,
     "page": 0,
     "address": "165LPQijvZdnmxcuCfxGWvcoSVtoJnCFm1UjjijzsSGGAk22"
}'
```

### URL Request

`POST /api/scan/staking_history`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| row | int | yes     |
| page| int | yes     |
| address| string | yes     |


> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "count": 1,
            "history": [
                {
                    "Id": 11,
                    "account": "76be05272d7fea694b92d50599b36b315e7c88640f828409433e36b88ca8aa15",
                    "era": 1,
                    "session_id": 60595,
                    "block_timestamp": 12119,
                    "reward_type": "validator",
                    "reward": "85.616438356"
                }
            ]
        }
    }
```



## bond-list

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/wallet/bond_list' \
--header 'Content-Type: application/json' \
--data-raw '{
     "row": 20,
     "page": 1,
     "status":"bonded",
     "address": "165LPQijvZdnmxcuCfxGWvcoSVtoJnCFm1UjjijzsSGGAk22"
}'
```

### URL Request

`POST /api/wallet/bond_list`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| row | int | yes     |
| page| int | yes     |
| status| string | yes (unbonding,bonded)    |
| address| string | yes     |
| locked| int | no (1,0)    |

-----

## validators

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking/validators' \
--header 'Content-Type: application/json' \
--data-raw '{
    "key": 20
}'
```

### URL Request

`POST /api/scan/staking/validators`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| key | string | no     |
| order| string | no (desc,asc)    |
| order_field| string | no(rank_validator,bonded_nominators,bonded_owner,count_nominators,validator_prefs_value)     |


> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "count": 21,
            "list": [
                {
                    "rank_nominator": 0,
                    "nominator_stash": "a960aaa0a8c07792120d95ac8831739cbe4290be9b20659a5dfa02e8c26b6329",
                    "bonded": "21027084300",
                    "hash": ""
                }
            ]
        }
    }
    
```

## waiting-validator

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking/waiting' \
--header 'Content-Type: application/json' \
--data-raw '{
    "key": 20
}'
```

### URL Request

`POST /api/scan/staking/waiting`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| key | string | no     |
| order| string | no (desc,asc)    |
| order_field| string | no(bonded_nominators,bonded_owner,count_nominators,validator_prefs_value)     |


> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "list": [
                {
                    "rank_validator": 0,
                    "nickname": "",
                    "validator_stash": "d0bd030f88d88e9746e7e684a210d0e1b8b7db04d6a3dad1da047e7200c21e10",
                    "validator_controller": "00126b7ee6fbdefcbe0d727cd78a1eadaa3b1964ea886595a07482c7dc60d61a",
                    "bonded_nominators": "63446148148558871",
                    "bonded_owner": "500000000000",
                    "count_nominators": 24,
                    "validator_prefs_value": 1000000000
                }
            ],
            "count":124
        }
    }
    
```

## voted

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking/voted' \
--header 'Content-Type: application/json' \
--data-raw '{
    "address": "15fTw39Ju2jJiHeGe1fJ5DtgugUauy9tr2HZuiRNFwqnGQ1Q"
}'
```

### URL Request

`POST /api/scan/staking/voted`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| order| string | no (desc,asc)    |
| order_field| string | no(bonded_nominators,bonded_owner,count_nominators,validator_prefs_value)     |
| address | string | yes     |

> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "list": [
                {
                    "rank_validator": 0,
                    "nickname": "",
                    "validator_stash": "d0bd030f88d88e9746e7e684a210d0e1b8b7db04d6a3dad1da047e7200c21e10",
                    "validator_controller": "",
                    "bonded_nominators": "62412203064989607",
                    "bonded_owner": "500000000000",
                    "count_nominators": 21,
                    "validator_prefs_value": 1889624577,
                    "bonded": "21027084300"
                }
            ]
        }
    }
    
```

## nominators

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking/nominators' \
--header 'Content-Type: application/json' \
--data-raw '{
    "row": 20,
    "page": 0,
    "address": "165LPQijvZdnmxcuCfxGWvcoSVtoJnCFm1UjjijzsSGGAk22"
}'
```

### URL Request

`POST /api/scan/staking/nominators`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| address | string | yes     |
| row | int | yes     |
| page| int | yes     |
| order| string | no (desc,asc)    |
| order_field| string | no(rank_nominator,bonded)     |


> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "list": [
                {
                    "rank_validator": 0,
                    "nickname": "",
                    "validator_stash": "d0bd030f88d88e9746e7e684a210d0e1b8b7db04d6a3dad1da047e7200c21e10",
                    "validator_controller": "00126b7ee6fbdefcbe0d727cd78a1eadaa3b1964ea886595a07482c7dc60d61a",
                    "bonded_nominators": "63446148148558871",
                    "bonded_owner": "500000000000",
                    "count_nominators": 24,
                    "validator_prefs_value": 1000000000
                }
            ],
            "count":"1111"
        }
    }
    
    
```

## era-stat

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking/era_stat' \
--header 'Content-Type: application/json' \
--data-raw '{
    "row": 20,
    "page": 0,
    "address": "165LPQijvZdnmxcuCfxGWvcoSVtoJnCFm1UjjijzsSGGAk22"
}'
```

### URL Request

`POST /api/scan/staking/era_stat`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| address | string | yes     |
| row | int | yes     |
| page| int | yes     |


> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "count": 1,
            "list": [
                {
                    "Id": 90,
                    "account": "0cb65fa997169ce0476e1e7c12717d4b2e74f1577ddae002dfb6763f57f2d803",
                    "era": 1,
                    "start_block_num": 1,
                    "end_block_num": 1000000,
                    "reward": "20",
                    "slash": "0",
                    "block_produced": "658988,659064"
                }
            ]
        }
    }
    
```


## validator

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/staking/validator' \
--header 'Content-Type: application/json' \
--data-raw '{
    "stash": "165LPQijvZdnmxcuCfxGWvcoSVtoJnCFm1UjjijzsSGGAk22"
}'
```

### URL Request

`POST /api/scan/staking/validator`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| stash| string | yes(stash address)     |



> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "list": [
                {
                    "rank_validator": 0,
                    "nickname": "",
                    "validator_stash": "d0bd030f88d88e9746e7e684a210d0e1b8b7db04d6a3dad1da047e7200c21e10",
                    "validator_controller": "00126b7ee6fbdefcbe0d727cd78a1eadaa3b1964ea886595a07482c7dc60d61a",
                    "bonded_nominators": "63446148148558871",
                    "bonded_owner": "500000000000",
                    "count_nominators": 24,
                    "validator_prefs_value": 1000000000
                }
            ]
        }
    }
```


## bond-stat

### URL Request

`POST /api/scan/staking/validator/bond_stat`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| row | int | yes     |
| page| int | yes     |
| stash  | string | yes     |

-----

## reward-slash

```shell
curl --location --request POST 'https://polkadot.subscan.io/api/scan/account/reward_slash' \
--header 'Content-Type: application/json' \
--data-raw '{
    "row": 20,
    "page": 1,
    "address": "15fTw39Ju2jJiHeGe1fJ5DtgugUauy9tr2HZuiRNFwqnGQ1Q"
}'
```

### URL Request

`POST /api/scan/account/reward_slash`

### payload

| Name          | Type   | Require |
| ------------- | ------ | ------- |
| row | int | yes     |
| page| int | yes     |
| address  | string | yes     |

> Example Response

```json

    {
        "code": 0,
        "message": "Success",
        "ttl": 1,
        "data": {
            "count": 2,
            "list": [
                {
                    "event_index": "1780256-3",
                    "block_num": 1780256,
                    "extrinsic_idx": 3,
                    "module_id": "staking",
                    "event_id": "Reward",
                    "params": "[{\"type\":\"AccountId\",\"value\":\"0x6cf4b9ce8d60ca73a35f036cd58afbc52ecea4d691484586967ae1ed45a1c423\",\"valueRaw\":\"6cf4b9ce8d60ca73a35f036cd58afbc52ecea4d691484586967ae1ed45a1c423\"},{\"type\":\"Balance\",\"value\":\"129823168189\",\"valueRaw\":\"bd56103a1e0000000000000000000000\"}]",
                    "extrinsic_hash": "0x7484200dc749d42f6233186081a47fc977b45deec7f95468e0e68d277acf033a",
                    "event_idx": 5
                },
                {
                    "event_index": "1780256-3",
                    "block_num": 1780256,
                    "extrinsic_idx": 3,
                    "module_id": "staking",
                    "event_id": "Reward",
                    "params": "[{\"type\":\"AccountId\",\"value\":\"0x6cf4b9ce8d60ca73a35f036cd58afbc52ecea4d691484586967ae1ed45a1c423\",\"valueRaw\":\"6cf4b9ce8d60ca73a35f036cd58afbc52ecea4d691484586967ae1ed45a1c423\"},{\"type\":\"Balance\",\"value\":\"151198365253\",\"valueRaw\":\"45f61f34230000000000000000000000\"}]",
                    "extrinsic_hash": "0x7484200dc749d42f6233186081a47fc977b45deec7f95468e0e68d277acf033a",
                    "event_idx": 6
                }
            ]
        }
    }


```