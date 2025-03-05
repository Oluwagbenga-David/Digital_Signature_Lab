#Digital Signature Lab

This repository contains steps and files related to digital signatures using OpenSSL

Step 1: Generate and view a private key
$ openssl genpkey -algorithm RSA -out private_key.pem

Step 2: Generate and view a public key
$ openssl pkey -in private_key.pem -pubout -out public_key.pem

Step 3: Create a new document that will be digitally signed
echo Please transfer 2,000,000 US Dollars to Mr. Jester by 6pm today! > document.txt

Step 4:Use the private key to digitally sign the new document
openssl dgst -sha256 -sign private_key.pem -out signature document.txt

Step 5: Verify the authenticity and integrity of the document.
openssl dgst -sha256 -verify public_key.pem -signature signature document.txt
