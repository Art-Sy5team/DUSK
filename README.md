# Tutorial Testnet DUSK Network 

- [Discord](https://discord.gg/dusknetwork) 
- [docs official ](https://dusk.network/pages/incentivized-testnet#Wallet) 
- [explorer](https://explorer.dusk.network/)
- [Rewards Detail](https://dusk.network/pages/incentivized-testnet )
- [Faucet](https://docs.google.com/forms/u/0/d/e/1FAIpQLScxABRnszbBEaTZAIg2TwfJVIq0kRggy8QK2MRBTO7vuyP_Ug/closedform)

## Spesifikasi Minimum
| Komponen  | Requirements minimal|
|-----------|---------------------|
|Sistem Operasi|Ubuntu 22 atau yang lebih tinggi |
|CPU           | 2 Cores                         |
|RAM           | 1 GB DDR4 RAM                   |
|Penyimpanan   | 20GB (SSD atau NVME)            |
|Koneksi       |10Mbps - 100Mbps                 |

## - Install dan buat file

```
sudo apt-get update
sudo apt install libssl-dev
sudo apt-get install -y tar wget curl
```
```
wget -q https://github.com/dusk-network/wallet-cli/releases/download/v0.12.0/ruskwallet0.12.0-linux-x64.tar.gz
```
```
tar -xf ruskwallet0.12.0-linux-x64.tar.gz
```
```
rm -rf ruskwallet0.12.0-linux-x64.tar.gz
```

## - open port 
ini bisa di setting di VPS masing-masing tapi ada juga yang tidak support di beberapa penyedia VPS
gunakan command ini untuk mengaktifkan port

```
sudo ufw allow 22
sudo ufw allow 9000:9005/udp
sudo ufw enable
```

### ke file rusk-wallet untuk membuat wallet

```
cd rusk-wallet0.12.0-linux-x64
```
```
./rusk-wallet
```

- Pilih `Create New Wallet` Klik Enter
- Buat password wallet  
- Ulangi Password 
- Copy dan Simpan Pharse 
- Lalu Pilih `y` Lalu **Enter** 
-  address anda akan muncul 
- Lalu [Faucet](https://docs.google.com/forms/u/0/d/e/1FAIpQLScxABRnszbBEaTZAIg2TwfJVIq0kRggy8QK2MRBTO7vuyP_Ug/closedform)

## Check saldo di wallet
ke file rusk-wallet dan jalankan command dibawah

```
cd rusk-wallet0.12.0-linux-x64
./rusk-wallet
```
## check dan backup wallet dusk

- Pilih `Replace your wallet with a lost one using the recovery phrase` dan `enter`
- Masukan Pharse Wallet kalian `Enter`
- Masukan Password Anda 2x dan `Enter`
- Balik ke VPS Arah Bawah Pilih `Back` dan `Enter`
- Arah Bawah Lagi Pilih `Exit` dan `Enter`


## install Rusk-Node

```
cd
curl --proto '=https' --tlsv1.2 -sSf https://dusk-infra.ams3.digitaloceanspaces.com/rusk/itn-installer.sh | sh
```

## - Buat folder consensus.keys
untuk menyimpan passwordanda
```
cd /root/.dusk/rusk-wallet
mv *.key /opt/dusk/conf/consensus.keys
```
```
echo 'DUSK_CONSENSUS_KEYS_PASS=<Ganti-password-anda>' > /opt/dusk/services/dusk.conf
```
`<Ganti-password-anda>` = **<> Ganti-password-anda** 

## - Mulai node dan daftar command berguna
### start NODE 

```
service rusk start
```
```
service dusk start
```

### check log NODE
```
tail -f /var/log/rusk.log
```
```
tail -f /var/log/dusk.log
```

### stop NODE 
```
service rusk stop
```
```
service dusk stop
```
### - Stake Token

```
cd
cd rusk-wallet0.12.0-linux-x64
./rusk-wallet
```

- Pilih `Acces Wallet` dan `Enter`
- Masukan Password Kalian dan `Enter`
- Lalu `Enter` 
- Arah Bawah Pilih `Stake Dusk` 
- Introduce the amount of DUSK to stake: isi `25000` atau set `defaul` langsung `Enter`
- Introduce the gas limit for this transaction: isi `2000000000`  dan `Enter`
- Introduce the gas price for this transaction: set `defaul` langsung `Enter`
- Ketik `y` dan `Enter`
- Done

## - Check status stake

```
./rusk-wallet
```

- Pilih `Acces Wallet` dan `Enter`
- Masukan Password Kalian dan `Enter`
- Lalu `Enter` lagi
- Arah Bawah Pilih `Check existing stake` dan `Enter`
- Done

## Delete NODE 

```
sudo service rusk stop
sudo systemctl disable rusk
sudo service dusk stop
sudo systemctl disbale dusk
sudo rm /etc/systemd/system/rusk* -rf
sudo rm /etc/systemd/system/dusk* -rf
sudo rm -rf /opt/dusk/
rm -rf /var/log/dusk.log
rm -rf /var/log/rusk.log
rm -rf rusk-wallet0.12.0-linux-x64
```

## Art-Team INFO
noted: ***art team*** here does not have any specific goals or intentions, they only collect data and share it with everyone.

untuk INFO Testnet lainya Silahkan join Discord 👇

[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/ArtSy5team)
[![Discord](https://img.shields.io/badge/discord-7289d9?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/EAKEdZU6c8)
[![Github](https://img.shields.io/badge/GitHub-171515?style=for-the-badge&logo=GitHub&logoColor=white)](https://github.com/Art-Sy5team)
[![trakteer](https://img.shields.io/badge/trakteer.id-e31e1e?style=for-the-badge&logo=ko-fi&logoColor=white)](https://trakteer.id/Art-Sy5team/tip)
