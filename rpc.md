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


continue
