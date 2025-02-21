# Ubuntu Commands

Made by nnq962

---

## CUDA TOOLKIT

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-6
```

## CUDNN

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get -y install cudnn
```

## ANACONDA

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Linux-x86_64.sh
sudo bash ./Anaconda3-2024.10-1-Linux-x86_64.sh
echo 'export PATH="/home/edulive/anaconda3/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
conda init
source ~/.bashrc
```

## FIX STEREO

```bash
pactl list short sinks
pactl set-card-profile alsa_card.pci-0000_00_1f.3 output:analog-stereo
```

## BỎ GÕ TIẾNG VIỆT

```bash
sudo add-apt-repository ppa:bamboo-engine/ibus-bamboo
sudo apt-get update
sudo apt-get install ibus-bamboo
```

## FIX SAI GIỜ WINDOWS

```bash
timedatectl set-local-rtc 1
```

## SSH

```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl status ssh
```

## SAMBA

```bash
sudo apt update
sudo apt install samba -y
sudo smbpasswd -a pc
sudo smbpasswd -e pc
sudo nano /etc/samba/smb.conf
```

📌 **Cấu hình trong **``:

```ini
[pc]
   path = /home/pc
   valid users = pc
   read only = no
   browsable = yes
   writable = yes
   create mask = 0777
   directory mask = 0777
```

## MONGODB

```bash
sudo apt-get install gnupg curl
curl -fsSL https://www.mongodb.org/static/pgp/server-8.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-8.0.gpg \
   --dearmor
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-8.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/8.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl start mongod
sudo systemctl status mongod
```

