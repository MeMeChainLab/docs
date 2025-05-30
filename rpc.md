# MemeChain JSON-RPC API Documentation

## Overview
This document provides a comprehensive reference for MemeChain's JSON-RPC API interface, detailing methods for interacting with blockchain data and transaction processing. The API follows JSON-RPC 2.0 specifications and supports core blockchain operations including:

* Address/account operations
### GetBlockByHash

**Description**：

Get block information based on block hash

**Request**：

* id          Unique request identifier
* jsonRpc     JSON-RPC version
* params      Parameters:
  * blockHash Block hash

**Response**：

* id            Unique request identifier
* jsonRpc       JSON-RPC version
* method        Name of the called method of the called method
* result        Return information
  * code        Return value number
    * 0	        Success
    * -1        Block hash error
  * message     Human-readable status message
  * blockInfo   Block information (see Block information description for details)

example

```json
//req
{
  "id":"1",
  "jsonRpc":"2.0",
  "params":{"blockHash":"0xb51f9199b387ce0b45c847c85f86fa3db3eb5e15b50b4a267dd9f582cd4bc256"}
}
//ack
{
  "id": "1",
  "jsonRpc": "2.0",
  "method": "GetBlockByHash",
  "result": {
    "blockInfo": {
      "block": {
        "blockSigns": [
          {
            "pub": "MCowBQYDK2VwAyEACE2DupNwSIpn854yGLj7QF/YHd6eAeLOhHYObzcbCTM=",
            "sign": "oKx5qKFORpeQ5XyrbR6bzPQyUFyB2W7iW9kVZ7QkFUK6KYpb+1Hc4asO8ra63C572FhXpBMvda5aF74TjA1ECg==",
            "addr": "0x85240c8dF5011d5967FA4566D3e2Ad5575A51856"
          },
          {
            "pub": "MCowBQYDK2VwAyEA8jzU4KuMjBgESW8u9aX5coT+KtfpcGWwAoRixNrjem4=",
            "sign": "y3RwfXf1OVzH3GJkIicRhdAev6N8NxSVniMf6/hLQ25TUBkBezig0Q8/IWVR8DWbfg2HqPCw0DpaIA4BHmJpDw==",
            "addr": "0x9Ed0009A37D251706c4f14a85f755eabaCE99Ae9"
          },
          {
            "pub": "MCowBQYDK2VwAyEAfuNxn5WIsxqDXkc57Vl2ZFsbAv50UEKMkzeP2Po1udU=",
            "sign": "BSx8AoB99luZEMPQtsVWDCBgo1JsxHh4cw1cVf91OBITpJWLHos7iYKZ2PTp1ZFbtF+98s1mrDq8UtH4E30pCA==",
            "addr": "0xd27384462Bfe9d37c8e27b732c2aBbcA99B2026f"
          },
          {
            "pub": "MCowBQYDK2VwAyEAIyogP9HbFhQLJPXWTJvr7oacfOj7V7jbwr+tWuLUpeo=",
            "sign": "oZSfjyABTAmYMs8JDeH9BGcsxQ3ih9VnDSgyj4LTYIWw+wtoQS6lWW01Hh4r3E3NCicwGaYHeOtVa0S65Kr6AQ==",
            "addr": "0x066F1A3f2E6C25a21B1a8B342E8CEA91Df585835"
          },
          {
            "pub": "MCowBQYDK2VwAyEAKblncGE2av+phdWRpUGHta3wagpb+xMdnZ3HBy1sTsM=",
            "sign": "hHw9F2rO+LwXRYsLOUk4MAidRp0esVEU+iRuOSIjvods6Df37yscTOmqj5xsTPB2FBbT2jknObpceaUrdRv+Aw==",
            "addr": "0x3aeeFE155376a47E63bB93fE4e95e67aF42B68eC"
          },
          {
            "pub": "MCowBQYDK2VwAyEANI0XsAkIjo1T9QSBucwrNMklWOohtZccqub4OWUNrWU=",
            "sign": "g0+kMIf5ekUL4imH/A0XeOLQxHoQuVzRVfoBSotNlYx1KgcARhUNVXx7ysxrh27lif1wTG0RwCNliISFEsJfAA==",
            "addr": "0x5F4c7cFD9B2095c947B9be84F6A57D08e44eF791"
          },
          {
            "pub": "MCowBQYDK2VwAyEAbALWvBTB+PQv2StB5NEYON6WVj1eYwHxGfI0G/UFFmk=",
            "sign": "zcw8ob5dNOBV8InDEe1xkcJc5CnxZJYEwBNfHsbFUYi7/RYhmA4AO8SwFRAavc6i36TEJ3FhkKAERSwK8C+mCQ==",
            "addr": "0x277Ff39E8176A582A392265ca619bdb6477674a5"
          }
        ],
        "bytes": 1765,
        "data": null,
        "hash": "0xb51f9199b387ce0b45c847c85f86fa3db3eb5e15b50b4a267dd9f582cd4bc256",
        "height": 65,
        "merkleRoot": "0xbfc73f1c66c7c552cbdb3d02cc1c434b1efaf35fd3916350b5d8a38f92c96fc7",
        "prevHash": "0xb03385ae8fce992887c56f38966636a7e31cc273b599a2e4197a31878a7fcaf5",
        "time": 1724827704568873
      },
      "tx": [
        {
          "consensus": 7,
          "gasTx": 0,
          "type": "Tx",
          "data": {
            "txInfo": {
              "lockAmount": 100000000000,
              "lockType": "lockNet"
            }
          },
          "identity": "0x85240c8dF5011d5967FA4566D3e2Ad5575A51856",
          "info": "",
          "time": 1724827704568873,
          "txHash": "0xbfc73f1c66c7c552cbdb3d02cc1c434b1efaf35fd3916350b5d8a38f92c96fc7",
          "txType": 9,
          "utxo": [
            {
              "assetType": "X",
              "gasUtxo": 0,
              "multiSigns": [
                {
                  "pub": "xIVI+gfNGHAVrISn879D49+XV3HKT8kaHk7VnlAilvuQF67GYAeXqEoLapIjP0TBTcpsDHmZTqQUzjXVnJu0BQ==",
                  "sign": "xIVI+gfNGHAVrISn879D49+XV3HKT8kaHk7VnlAilvuQF67GYAeXqEoLapIjP0TBTcpsDHmZTqQUzjXVnJu0BQ=="
                }
              ],
              "owner": [
                "0xffFd42e045737b11570B7981c2648ea532a10B23"
              ],
              "vin": {
                "preVout": {
                  "hash": [
                    "0x36b19c533a49ec05a06be9c99c4e1c2e1609f9679aa75989c8ae0999ca63562a"
                  ]
                },
                "vinSigns": [
                  {
                    "pub": "MCowBQYDK2VwAyEAnVwyI7Xwk4lVNwi4j7ogCoHyy40isQmMumbM58JKTTU=",
                    "sign": "jXugdh1gM05AT73xU5WYP6THqX7ghdi4heKe04XjdsJQ/QhR6DxwkA5SLUO//lFswiiWFMf6gf697uVewJ4MAw=="
                  }
                ]
              },
              "vout": [
                {
                  "addr": "lockVirtualStake",
                  "value": 100000000000
                },
                {
                  "addr": "0xffFd42e045737b11570B7981c2648ea532a10B23",
                  "value": 9759599999665600
                },
                {
                  "addr": "VirtualBurnGas",
                  "value": 26100
                }
              ]
            }
          ],
          "verifySigns": [
            {
              "pub": "MCowBQYDK2VwAyEACE2DupNwSIpn854yGLj7QF/YHd6eAeLOhHYObzcbCTM=",
              "sign": "NTJntLI0ILj7hPFP1n5xmRj1eAOUKxEqec8cXLxGjjhJ74r8Qqn7fIwIsDbuQI8BGCD/D1Ikp9muLq/1eMACCw==",
              "addr": "0x85240c8dF5011d5967FA4566D3e2Ad5575A51856"
            }
          ]
        }
      ]
    },
    "code": 0,
    "message": "success"
  }
}
```

### GetBalance

**Description**：

Retrieves the asset balance of a specified blockchain address.

**Request**：

* id Unique request identifier
* jsonRpc  JSON-RPC version
* params Parameters:
  * addr  Address to query
  * asset Asset type identifier 
  

**Response**：

* id          Unique request identifier
* jsonRpc     JSON-RPC version
* method      Name of the API method called
* result      Return information
  * code      Status code: 
     0  	    Success
    -1        address is invalid
    -2        search balance failed
  * message   Human-readable status message
  * balance   Account balance in smallest unit
  * addr      Address that was queried
  * assetType Type of asset queried 

**example**:

```json
//req
{
    "id": "1",
    "jsonRpc": "2.0",
    "params": {
        "addr": "0xffFd42e045737b11570B7981c2648ea532a10B23",
        "assetType": "X"
    }
}
//ack
{
  "id": "1",
  "jsonRpc": "2.0",
  "method": "GetBalance",
  "result": {
    "addr": "0xffFd42e045737b11570B7981c2648ea532a10B23",
    "assetType": "X",
    "balance": "9759699999691700",
    "code": 0,
    "message": "success"
  }
}
```



### GetBlockHeight

**Description**：

Retrieves the current height of the blockchain (latest confirmed block number).

**Request**：

* id       Unique request identifier
* jsonRpc  JSON-RPC version

**Response**：

* id          Unique request identifier
* jsonRpc     JSON-RPC version
* method      Echoes the Name of the called method
* result      Result payload:
  * code      Status code:
    -  0      Success
    -  -1     GetBlockTop error
  * message   Human-readable status message
  * top       Latest block height 

**example**:

```json
//req
{
    "id":"1",
    "jsonRpc":"2.0",
}
//ack
{
  "id": "1",
  "jsonRpc": "2.0",
  "method": "GetBlockHeight",
  "result": {
    "code": 0,
    "message": "success",
    "height": "590"
  }
}
```



### GetVersion

**Description**：

Retrieves version information of the client, network protocol, database, and configuration.

**Request**：

* id       Unique request identifier
* jsonRpc  JSON-RPC version

**Response**：

* id                Unique request identifier
* jsonRpc           JSON-RPC version
* method            Name of the called method of the called method
* result            Version details:
  * code            Status code    
    -  0  	        Success
  * message         Human-readable status message
  * clientVersion   Client software version
  * netVersion      Network protocol version
  * configVersion   Configuration schema version 
  * dbVersion       Database schema version

**example**:

```json
//req
{
    "id":"1",
    "jsonRpc":"2.0",
}
//ack
{
    "id": "1",
    "jsonrpc": "",
    "method": "GetVersion",
    "result": {
        "clientVersion": "1_0.0.1_d",
        "code": 0,
        "configVersion": "1.0.0",
        "dbVersion": "1_0.0.1_d",
        "message": "success",
        "netVersion": "0.0"
    }
}



### GetBlockTransactionCountByHash

**Description**：

Returns the number of transactions in a block that matches the hash of a given block

**Request**：

* id            Unique request identifier
* jsonRpc       JSON-RPC version
* params        Parameters:
  * blockHash   Block hash

**Response**：

* id            Unique request identifier
* jsonRpc       JSON-RPC version
* method        Name of the called method of the called method
* result        Return information
  * code        Status code
    *   0  	    Success
    *  -1       GetBlockByBlockHash error
    *  -2       block parse string fail
  * message     Human-readable status message
  * txCount     Number of transactions in the block for a specified block hash

**example**:

```json
//req
{
    "id":"1",
    "jsonRpc":"2.0",
    "params":{"blockHash":"0x12e52383dc0fedc40bdab13fc1afd851d7123facf030f90163c03f87411650f1"}
}
//ack
{
  "id": "1",
  "jsonRpc": "2.0",
  "method": "GetBlockTransactionCountByHash",
  "result": {
    "code": 0,
    "message": "success",
    "txCount": "1"
  }
}
```
### GetAccounts

**Description**：

Returns a list of addresses owned by the client

**Request**：

* id       Unique request identifier
* jsonRpc  JSON-RPC version

**Response**：

* id              Unique request identifier
* jsonRpc         JSON-RPC version
* method          Name of the called method of the called method
* result          Return information
  * code          Status code: 
    - 0  	        Success
  * message       Human-readable status message
  * acccountList  List of addresses owned by the client

**example**: 

```json
//req
{
    "id":"1",
    "jsonRpc":"2.0",
}
//ack
{
  "id": "1",
  "jsonRpc": "2.0",
  "method": "GetAccounts",
  "result": {
    "acccountLists": [
      "0x6a72ad3e9762d67D45a311954CdC6ad4693203a9",
      "0x87dE53fdC1e5AA53eB9Cb839C2EF664Cab0f4C01",
      "0x9d394DFB4475Eaef15A27396568e5028f13C3F85",
      "0xD4c60A4866BeE49e0642feC293ee8560C237b758",
      "0xf535227CCA5487776e666374c839de8b7005892B"
    ],
    "code": 0,
    "message": "success"
  }
}
```



### GetChainId

**Description**：

Return chain ID

**Request**：

* id           Unique request identifier
* jsonRpc      JSON-RPC version

  

**Response**：

* id           Unique request identifier
* jsonRpc      JSON-RPC version
* method       Name of the called method of the called method
* result       Return information
  * code       Status code: 
    -  0  	   Success
  * message    Human-readable status message
  * chainId    Chain ID

**example**:

```json
//req
{
    "id":"1",
    "jsonRpc":"2.0",
}
//ack
{
  "id": "1",
  "jsonRpc": "2.0",
  "method": "GetChainId",
  "result": {
    "chainId": "0x1080c0ce",
    "code": 0,
    "message": "success"
  }
}
```


