[Back to Cheatsheets Index](README.md)
# manage-bde Cheatsheet


---

#### View status of BitLocker encrypted volumes/disks

`manage-bde -status`

---


#### Force BitLocker cipher strength

By default Windows uses an XTS-AES 128-bit cipher, this can be changed to XTS-AES 256-bit by changing the group policy:

`Choose drive encryption method and cipher strength (Windows 10 [Version 1511] and later)`

located in:

`/Computer Configuration/Administrative Templates/Windows Components/BitLocker Drive Encryption/`

**Note:** it is impossible to change the cipher on an existing encrypted drive, the drive must be decrypted and then re-encrypted.
