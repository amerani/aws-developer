# KMS (Key Management Service)
- create and control encryption keys
- IAM >> Encryption Keys
- Encryption Keys are regional

## Customer Master Key (CMK)
- alias (manager, encrypter)
- creation date
- description
- key state
- key material (external or AWS provided)
- CAN NEVER BE EXPORTED

### Key Adminstrative Permissions
- user who can manage keys

### Key Usage Permissions
- user who can encrypt and decrypt using key
- can be an external user

## KMS API Calls

### aws kms ecrypt
`aws kms encrypt --key-id 642bd7fa-e3d4-4a34-9333-94fee4678a3c --plaintext fileb://secret.txt --output text --query CiphertextBlob | base64 --decode > encryptedsecret.txt`  

### aws kms decrypt
`aws kms decrypt --ciphertext-blob fileb://encryptedsecret.txt --output text --query Plaintext | base64 --decode > decryptedsecret.txt`

### aws kms re-encrypt (decrypt and encrypt)
`aws kms re-encrypt --destination-key-id 642bd7fa-e3d4-4a34-9333-94fee4678a3c --ciphertext-blob fileb://encryptedsecret.txt | base64 > newencryption.txt`

### aws kms enable-key-rotation
`aws kms enable-key-rotation --key-id 642bd7fa-e3d4-4a34-9333-94fee4678a3c`

## KMS Envelope Encryption
Encrypted Data Key (Envelope Key)   
-> use Master Key to decrypt data key = plain text data key  
-> use plain text data key to decrypt actual data