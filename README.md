# INSTALL MONGODB

### UPDATE SYSTEM
```
sudo apt update && sudo apt upgrade -y
sudo reboot
```
### MULAI INTALL MONGODB

### Impor Kunci GPG MongoDB
```
sudo apt-get install gnupg curl -y
curl -fsSL https://www.mongodb.org/static/pgp/server-8.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-8.0.gpg --dearmor
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-8.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/8.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
```
### Mulai dan Aktifkan Layanan MongoDB
```
sudo systemctl start mongod
sudo systemctl enable mongod
mongod --version
```

## INSTALL NODE.JS

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
source ~/.bashrc    # atau: source ~/.zshrc
nvm install --lts     # mis. v20 LT
nvm alias default 'lts/*'
node -v
npm -v
```

# Install PM2 secara global
```
npm install -g pm2
pm2 -v
```

### Jika ingin update NODE.JS
```
### 3. Tambahkan NodeSource (versi LTS terbaru atau current)
### Untuk versi stable/LTS terbaru
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -

### 4. Install Node.js
sudo apt install -y nodejs
sudo apt install nodejs npm -y

### 5. Cek versi
node -v
npm -v
```

### Membuat titik Backup dan restore
```
# Install Timeshift
sudo apt update
sudo apt install timeshift -y
sudo timeshift --version
```
```
# Membuat snapshot manual
sudo timeshift --create --comments "Nama File" --tags D
```
```
# Melihat daftar file snapshop
sudo timeshift --list
```

### restore menggunakan nomor snapshot (1)
```
# Restore Snapshot
sudo timeshift --restore --snapshot 1
```

### delete file snapshot menggunakan nomor snapshot (2)
```
# Delete Snapshot
sudo timeshift --delete --snapshot 2
```
