# 23 - SP APIs

SP should provide plenty of APIs to facilitate users to look up information, download the objects, recover the data, and send transactions onto the Greenfield blockchain. This section will be extended as time goes on.

All SPs should provide APIs listed in this section.

### 23.1 Universal Endpoint

#### 23.1.1 URI Standard

All objects can be identified and accessed via a universal path:

_gnfd://\<bucket\_name>\<object\_name>_?\[parameter]\*

_where:_

* _"gnfd://" is the fixed leading identifier, which is mandatory_
* _bucket\_name is the bucket name of the object, which is mandatory_
* _object\_name is the name of the object, which is mandatory_
* _parameter is a list of key-value pair for the additional information for the URI, which is optional_

This path should be 1:1 mapped to an object. It is worth mentioning here that if we want to refer to the same object even if it was deleted and recreated, we can add the `If-Match-Checksum` parameter to the URI. E.g _gnfd://mybucket/myobject?If-Match-Checksum=qUiQTy8PR5uPgZdpSzAYSw0u0cHNKh7A+4XSmaGSpEc=_.

#### 23.1.2 HTTPS REST API

Each SP will register multiple endpoints to access their services, e.g. "SP1" may ask their users to download objects via [https://greenfield.sp1.com/download](https://greenfield.sp1.com/download).

The most important endpoint is the one for users to download objects. To download an object, users can just substitute the "gnfd://" in the URI standard with the SP endpoint. For example, to access gnfd://mybucket/foo/bar.jpg, users can just visit SP1 at [https://greenfield.sp1.com/download/mybucket/foo/bar.jpg](https://greenfield.sp1.com/download/mybucket/foo/bar.jpg).

When SP1 receives the request to this path, SP1 should understand the users want to download the object at gnfd://mybucket/foo/bar/my-cool-object-id. SP1 should first get which SP is the current primary SP of this object, if it's SP1 herself, SP1 should start sending the data to the user; otherwise, SP1 will send an HTTP 302 to redirect the request to the primary SP's download endpoint.

#### 23.1.3 P2P RPC

Please note that both Greenfield blockchain full nodes (including validators) and SPs will provide P2P RPCs to access different data.

Greenfield blockchain full node RPC will be access points to read and change the blockchain data, e.g. users can check the current block height and validator set information, or send transactions to create a bucket.

SP P2P RPCs are under a different P2P protocol mostly for data reading, which is designed based on the BitTorrent protocol. Any client software that wants to use this feature must build in this P2P protocol.

One thing to note is that Greenfield enforces permission and access control so that the data forwarded to the P2P network should be encrypted with the users' public keys.

### 23.2 List Operations

There are multiple operations related to "list" some information about Greenfield. For example, list all objects under a bucket, list all the members in a group or list all the objects associated with a payment account. These operations are usually too heavy to be supported directly via a Greenfield blockchain full node RPCs. Here SPs should provide these functions via corresponding APIs so that the users have a better experience to store, check, download, and manage the objects.
