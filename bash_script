#!/bin/bash

#DISPLAY OPTIONS
echo "1) Encrypt the file "
echo "2) Decrypt the file "



#ASK OPTION
echo
read -p "Enter option(1/2): " option


#CHECK
if (($option==1)); then
        read -p "Enter file name for encryption: " file_name
        read -p "Enter file name for storing output: " output_filename
        read -p "Enter public key file: " pub_key
        echo
        openssl pkeyutl -encrypt -in $file_name -out $output_filename -inkey $pub_key -pubin
elif (($option==2)); then
        read -p "Enter file name to be decrypted: " file_name
        read -p "Enter file name for storing output: " output_filename
        read -p "Enter private key file " priv_key
        read -s -p "Enter pass phrase for $priv_key " priv_key_password
        echo
        openssl pkeyutl -decrypt -in $file_name -out $output_filename -inkey $priv_key -passin "pass:$priv_key_password"
else
        echo "Invalid Input"
fi
