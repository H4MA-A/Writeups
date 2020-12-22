# vulnconCTF2020
  
Team: Fword

## Overview

```
Title                      Category             Points  Flag
-------------------------- -------------------  ------- -----------------------------
Corruptbattle              Reverse Engineering  100     vulncon{0xE209470e1289D4CE5F23aa7e486228c46C4D99a4}
HashMe                     Reverse Engineering  100     vulncon{r3ver5eM4s7er}
```


## Reverse Engineering 100: Corruptbattle

**Challenge**  
Can you find my unique blockchain address inside a corrupted and scrambled program , remember the blockchain address is of 42 chars.

![alt text](https://github.com/H4MA-A/Writeups/blob/main/vulnconCTF2020/1.png)

**Solution**  
For this challenge, we are provided with a binary, and based on the description we have to find a blockchain address that is 42 chars long

So we start analyzing the binary


![alt text](https://github.com/H4MA-A/Writeups/blob/main/vulnconCTF2020/2.png)

it‘s a 64 bit ELF binary so we open IDA and we start checking the disassembly


![alt text](https://github.com/H4MA-A/Writeups/blob/main/vulnconCTF2020/3.png)

We notice that there is more than one function called main so after having a look we notice that in the function main_one the binary is loading a hex

![alt text](https://github.com/H4MA-A/Writeups/blob/main/vulnconCTF2020/4.png)

We take that string and with python, we check the length:

![alt text](https://github.com/H4MA-A/Writeups/blob/main/vulnconCTF2020/5.png)

So its length is 42 so we submit and its the flag 

**Flag**  
```
vulncon{0xE209470e1289D4CE5F23aa7e486228c46C4D99a4}
```

## Web Exploitation 10: Elemental
**Challenge**  
Just put in the password for the flag! [Link](http://yrmyzscnvh.abctf.xyz/web1/)

**Solution**  
Web page with a password field, password was in source as a comment, entering it in field gave the flag

**Flag**  
```
ABCTF{insp3ct3d_dat_3l3m3nt}
```
