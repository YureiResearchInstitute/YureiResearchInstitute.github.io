### yw_save - Yo-kai Watch save data decrypter / encrypter
#### ...and save editors (see below)

https://github.com/YureiResearchInstitute/yw_save

This script decrypts and encrypts save data of Yo-kai Watch.

- You need Python 3.x to run this script.
- You need PyCrypto to handle saves of Yo-kai Watch 2 and Busters.

~~Currently injecting doesn't work on Yo-kai Watch Busters.~~

(2016-03-18T19:11:06+09:00) Yo-kai Watch Busters savadata encrypting is now supported!

#### Usage
First dump game1.yw (the number depends on your save slot) with svdt.

Decrypt game1.yw with following command:
```python
python3 ./yw_save.py --game yw --decrypt game1.yw game1_decrypted.yw
```
After editing, re-encrypt game1.yw with following command:
```python
python3 ./yw_save.py --game yw --encrypt game1_decrypted.yw game1_encrypted.yw
```
Rename it and inject it with svdt.
```
mv game1.yw game1.yw.bak
mv game1_encrypted.yw game1.yw
```
