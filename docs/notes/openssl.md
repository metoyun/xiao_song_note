---
title: openssl
---

# openssl 生成随机字符串

``` sh

# example 生成16位base64字符
openssl rand -base64 16
# example 生成16位hex字符
openssl rand -hex 16

# openssl 命令集 

# Standard commands
# asn1parse         ca                certhash          ciphers           
# crl               crl2pkcs7         dgst              dh                
# dhparam           dsa               dsaparam          ec                
# ecparam           enc               errstr            gendh             
# gendsa            genpkey           genrsa            nseq              
# ocsp              passwd            pkcs12            pkcs7             
# pkcs8             pkey              pkeyparam         pkeyutl           
# prime             rand              req               rsa               
# rsautl            s_client          s_server          s_time            
# sess_id           smime             speed             spkac             
# ts                verify            version           x509              

# Message Digest commands (see the `dgst' command for more details)
# gost-mac          md4               md5               md_gost94         
# ripemd160         sha1              sha224            sha256            
# sha384            sha512            streebog256       streebog512       
# whirlpool         

# Cipher commands (see the `enc' command for more details)
# aes-128-cbc       aes-128-ecb       aes-192-cbc       aes-192-ecb       
# aes-256-cbc       aes-256-ecb       base64            bf                
# bf-cbc            bf-cfb            bf-ecb            bf-ofb            
# camellia-128-cbc  camellia-128-ecb  camellia-192-cbc  camellia-192-ecb  
# camellia-256-cbc  camellia-256-ecb  cast              cast-cbc          
# cast5-cbc         cast5-cfb         cast5-ecb         cast5-ofb         
# chacha            des               des-cbc           des-cfb           
# des-ecb           des-ede           des-ede-cbc       des-ede-cfb       
# des-ede-ofb       des-ede3          des-ede3-cbc      des-ede3-cfb      
# des-ede3-ofb      des-ofb           des3              desx              
# rc2               rc2-40-cbc        rc2-64-cbc        rc2-cbc           
# rc2-cfb           rc2-ecb           rc2-ofb           rc4               
# rc4-40            

```