#Digital Signature Lab

This repository contains steps and files related to digital signatures using OpenSSL

Step 1: Generate a private key

$ openssl genpkey -algorithm RSA -out private_key.pem

Step 2: Generate a public key

$ openssl pkey -in private_key.pem -pubout -out public_key.pem

Step 3: Create a new document that will be digitally signed

$ echo "This is a lab to test how digital signature works. Do not modify!" > document.txt

Step 4:Use the private key to digitally sign the new document

$ openssl dgst -sha256 -sign private_key.pem -out signature document.txt

Step 5: Verify the authenticity and integrity of the document.

$ openssl dgst -sha256 -verify public_key.pem -signature signature document.txt

Note: You can view file content with cat command.
