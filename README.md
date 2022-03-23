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
```
python3 ./yw_save.py --game yw --decrypt game1.yw game1_decrypted.yw
```
After editing, re-encrypt game1.yw with following command:
```
python3 ./yw_save.py --game yw --encrypt game1_decrypted.yw game1_encrypted.yw
```
Rename it and inject it with svdt.
```
mv game1.yw game1.yw.bak
mv game1_encrypted.yw game1.yw
```
Decrypting, encrypting and injecting works with:
- Yo-kai Watch (tested only on JP version, but it should work on other versions)
- Yo-kai Watch 2 Ganso / Honke
- Yo-kai Watch 2 Shin'uchi
- Yo-kai Watch Busters and Getto-gumi
- Yo-kai Watch 3

You can specify the game with "--game" option.
- --game yw (default) : Yo-kai Watch 1
- --game yw2 : Yo-kai Watch 2 Ganso / Honke 1.X and Shin'uchi
- --game yw2x : Yo-kai Watch 2 Ganso / Honke 2.X
- --game ywb : Yo-kai Watch Busters
- --game ywb_getto : Yo-kai Watch Busters Getto-gumi
- --game yw3 : Yo-kai Watch 3

(for details see https://github.com/YureiResearchInstitute/yw_save/blob/master/README.md )

I hope someone will make easy-to-use save editor...


#### Save editors
I eventually made simple save editors.
These save editors do decryption and encryption when needed (you don't have to use yw_save).

Yo-kai Watch:
https://github.com/YureiResearchInstitute/Yo-kai_Editor_1/releases

Yo-kai Watch 2 (Ganso, Honke, and Shin'uchi):
https://github.com/YureiResearchInstitute/Yo-kai_Editor_2/releases

Yo-kai Watch Busters:
https://github.com/YureiResearchInstitute/Yo-kai_Editor_Getto/releases

Yo-kai Watch 3:
https://github.com/YureiResearchInstitute/Yo-kai_Editor_3/releases

Note: You have to install Visual C++ 2013 redistributable package to run these editors.

https://www.microsoft.com/en-us/download/details.aspx?id=40784
choose vcredist_x86.exe.

**Error Reporting**

If you encounter an error, please check following before reporting:
1. You are using the correct version of save editor
2. (YW2 and above only) "head.yw" file exists in the same directory as "game*.yw" file

**Error codes**

- 1XX IO Error
  - 103 "head.yw" not found
- 2XX Decryption error
  - 201 AES CCM decryption failed
  - 202 Decryption failed
- 3XX Encryption error
- 4XX Save data parsing error
