# MemeChain JSON-RPC API Documentation

## Overview
This document provides a comprehensive reference for MemeChain's JSON-RPC API interface, detailing methods for interacting with blockchain data and transaction processing. The API follows JSON-RPC 2.0 specifications and supports core blockchain operations including:

* Address/account operations

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


