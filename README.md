node-red-contrib-crypto-storage :packet:
=====================

This is a subflow node for encrypting / decrypting payloads, creating an encrypted store on the specified folder utiling AES for block and Rabbit for stream ciphering.

## Install

Run the following command in your Node-RED user directory - typically `~/.node-red`

        npm install node-red-contrib-crypto-storage

## Information
This subflow provides functionalities cipher functionalities for preserving the confidentiality of payloads.

## Cipher API
The __plaintext__ payload can be either a string or an object, you must define the __function__ to use (``encrypt``/``decrypt``), the cipher __key__ and the __type__ of cipher to use (``AES``*/Block Cipher* or ``Rabbit``*/Stream Cipher*).

:warn: In the case of ``AES``, the __mode__ (``CBC/CFB/OFB/CTR``) parameter must also be set!    

<img src="./docs/CipherAPI.png">

### Cipher Encrypt Payload
* Setting the payload of the **Cipher Encrypt** injector:

<img src="./docs/CE1.png">

### Cipher Encrypt Response
* Encryption response payload:

<img src="./docs/CE2.png">

### Cipher Decrypt Payload
* Setting the payload of the **Cipher Decrypt** injector:

<img src="./docs/DE1.png">

### Cipher Decrypt Response
* Decryption response payload:

<img src="./docs/DE2.png">

## Cipher Store API
The __plaintext__ payload can be either a string or an object, you must define the __function__ to use (``encrypt``/``decrypt``), the cipher __key__ and the __filename__ of the crypto storage. 

You firstly need to define the __path__ of the store in the properties of the subflow:

<img src="./docs/CS0.png">

:warn: In the case of ``AES``, the __mode__ (``CBC/CFB/OFB/CTR``) parameter must also be set!    

### Store Encrypt Payload
* Setting the payload of the **Store Encrypt** injector:

<img src="./docs/CSB1.png">

### Store Encrypt Response
* Store encryption response payload:

<img src="./docs/CSB2.png">

### Store Decrypt Payload
* Setting the payload of the **Store Decrypt** injector:

<img src="./docs/DSB1.png">

### Store Decrypt Response
* Store decryption response payload:

<img src="./docs/DSB2.png">

