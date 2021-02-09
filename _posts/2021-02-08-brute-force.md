---
title: "Brute force"
date: 2021-02-08
categories: algorithm
---

## Brute force

In cryptography, a brute-force attack means substituting all possible values ​​to crack a particular cipher. Most encryption methods are theoretically insecure against brute-force attacks, and encrypted information can be decrypted if there is enough time.

In the case of symmetric key encryption (a type of encryption algorithm, which means an algorithm that uses the same encryption key for encryption and decryption), the encrypted information can be restored by finding the key used in the encryption, and the length of the key used here The maximum time required for a brute force attack is determined according to. When the encryption key is n bits, there are a maximum of 2^n possible values.

</br>

For example, we could use brutal force to solve the following problem.
```
# You are a hecker. You have data that is encrypted by stealing the transmitted data, and you know that this data is in plain text.
# You need to find out the original data and the secret key (8bits).

data = '6e5253491a5e5b4e5b1a53491a5b5649551a4c5f48431a53574a55484e5b544e1a4e5f424e1a5e5b4e5b141a6a565f5b495f1a4e5b515f1a595b485f1a4d525f541a525b545e5653545d14'
```

</br>

Symmetric key cryptography can be implemented as follows.
```
import binascii

def encoder(data:str, key:str) -> bytes:
    encoded_data = []
    ## xor
    for ch in data:
        result = ord(ch) ^ int(key, 2)
        encoded_data.append(result)
    ## Convert binary data to hexadecimal representation
    encoded_data_hex = binascii.hexlify(bytes(encoded_data))
    return encoded_data_hex

def decoder(encoded_data:bytes, key:str) -> str:
    decoded_data = ''
    ## Converted hexadecimal string to binary data
    encoded_data_byte = binascii.unhexlify(encoded_data)
    ## xor
    for byte in encoded_data_byte:
        decoded_data += chr(byte ^ int(key, 2))
    return decoded_data


# We use 8bits key
key = '11001010'
# Suppose the data is long text
data = 'This data is very important text data. Take care when handling.'

# Encrypt data to be transmitted.
encoded = encoder(data, key)

# Encrypted data
print(encoded)

# A secret key is required for decryption.
print(decoder(encoded,key))
```

Result:
```
b'9ea2a3b9eaaeabbeabeaa3b9eabcafb8b3eaa3a7baa5b8beaba4beeabeafb2beeaaeabbeabe4ea9eaba1afeaa9abb8afeabda2afa4eaa2aba4aea6a3a4ade4'
This data is very important text data. Take care when handling.
```

</br>

More detailed code can be found through the following link.

<https://github.com/hotchya/basic-algorithm>

</br>


## References
+ <https://en.wikipedia.org/wiki/Brute-force_attack>
+ <https://en.wikipedia.org/wiki/Symmetric-key_algorithm>