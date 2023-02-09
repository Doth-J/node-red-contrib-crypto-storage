# node-red-contrib-crypto-storage :package: 

## Information :information_source:
This is a subflow node for encrypting / decrypting payloads and creating encrypted stores on the specified folder utilizing AES for Block Ciphering and Rabbit for Stream Ciphering preserving the confidentiality of payloads.

## Install :zap:
Run the following command in your Node-RED user directory - typically `~/.node-red`

        npm install node-red-contrib-crypto-storage

## Cipher API :closed_lock_with_key:

- :arrow_right: Encrypt: **POST localhost:1880/encrypt** 
- :arrow_right: Decrypt: **POST localhost:1880/decrypt** 
  
The __plaintext__ payload can be either a string or an object, you must define the __function__ to use (``encrypt``/``decrypt``), the cipher __key__ and the __type__ of cipher to use (``AES``*/Block Cipher* or ``Rabbit``*/Stream Cipher*).

:warning: In the case of ``AES``, the __mode__ (``CBC/CFB/OFB/CTR``) parameter must also be set!    

![CipherAPI](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CipherAPI.PNG)

---

### Cipher Encrypt Payload :key: :arrow_right:
* Setting the payload of the **Cipher Encrypt** injector:

![CE1](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CE1.PNG)

---

### Cipher Encrypt Result :lock: :back: 
* Encryption response payload:

![CE2](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CE2.PNG)

---

### Cipher Decrypt Payload :key: :arrow_right:
* Setting the payload of the **Cipher Decrypt** injector:

![DE1](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/DE1.PNG)

---

### Cipher Decrypt Result :unlock: :back: 
* Decryption response payload:

![DE2](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/DE2.PNG)

## Cipher Store API :toolbox:

- :arrow_right: AES: **POST localhost:1880/blockStore** 
- :arrow_right: Rabbit: **POST localhost:1880/streamStore**
   
The __plaintext__ payload can be either a string or an object, you must define the __function__ to use (``encrypt``/``decrypt``), the cipher __key__ and the __filename__ of the crypto storage. 

![CipherStoreAPI](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CipherStoreAPI.PNG)

You firstly need to define the __path__ of the store in the properties of the subflow:

:warning: In the case of ``AES``, the __mode__ (``CBC/CFB/OFB/CTR``) parameter must also be set!    

![CSO](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CS0.PNG)

---

### Store Encrypt Payload :key: :arrow_right: :toolbox:
* Setting the payload of the **Store Encrypt** injector:

![CSB1](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CSB1.PNG)

---

### Store Encrypt Result :lock:  :back: :toolbox: 
* Store encryption response payload:

![CSB2](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/CSB2.PNG)

---

### Store Decrypt Payload :key: :arrow_right: :toolbox:
* Setting the payload of the **Store Decrypt** injector:

![DSB1](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/DSB1.PNG)

---

### Store Decrypt Result :unlock: :back: :toolbox: 
* Store decryption response payload:

![DSB2](https://github.com/Doth-J/node-red-contrib-crypto-storage/blob/master/docs/DSB2.PNG)

