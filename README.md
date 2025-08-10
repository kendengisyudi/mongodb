# INSTALL MONGODB

### UPDATE SYSTEM
```
sudo apt update && sudo apt upgrade -y
sudo reboot
```
## INTALL MONGODB

### Impor Kunci GPG MongoDB
```
sudo apt-get install gnupg curl -y
curl -fsSL https://www.mongodb.org/static/pgp/server-8.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-8.0.gpg --dearmor
```
### Tambahkan Repository MongoDB untuk Ubuntu 22.04
```
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-8.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/8.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.0.list
```
### Perbarui Daftar Paket & Instal MongoDB
```
sudo apt-get update
sudo apt-get install -y mongodb-org
```
### Mulai dan Aktifkan Layanan MongoDB
```
sudo systemctl start mongod
sudo systemctl enable mongod
```
### Verifikasi Instalasi
```
mongod --version
```
