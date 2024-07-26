# SSH
## What is SSH?
Secure Shell: A protocol, like HTTP, which allows users to communicate and exchange data between two computers over the internet. SSH uses encryption.

For example, HTTP communicates between browser and server.

*Tip:* DigitalOcean offers cheap virtual servers to host a website or staging environment.

## Using `apt` to Install Git and NPM
`apt` is like `npm` for installing packages on Ubuntu.

### Installing Git in Terminal When Connecting to Ubuntu Server
------------------------------------------------------------
`sudo apt-get install git`

Cloning a repository:
---------------------
`git clone`

Install npm:
------------
`sudo apt-get install nodejs`


## How Does SSH Work?
### Symmetrical Encryption / Asymmetrical Encryption / Hashing

**Symmetrical Encryption:**
SSH uses symmetric encryption, which uses one secret key. Anyone that has access to the key can decrypt the messages.

*Key Exchange Algorithm* is used to transfer the secret key.

**Asymmetrical Encryption:**
Uses two separate keys for encryption and decryption. A public key is linked to a private key. A message that is encrypted using a computer’s public key can only be decrypted using that computer’s private key.

**Diffie-Hellman Key Exchange:**
Generates a symmetric key for asymmetrical encryption exchange.

## Turning SSH into a Server

When creating a .pub, or public key, this can be shared with anyone 

Private key should never be shared 

### Setup SSH on GitHub for Windows
https://github.com/antonykidis/Setup-ssh-for-github/blob/master/Setup-ssh-on-github.pdf