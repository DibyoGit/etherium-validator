# etherium-validator

Install Docker and Compose:

sudo apt update
sudo apt install -y docker.io docker-compose
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ubuntu

sudo apt install git

Start Etherium client from the compose file in the repo:
docker-compose up -d

sudo wget -O /usr/local/bin/prysm.sh https://raw.githubusercontent.com/prysmaticlabs/prysm/master/prysm.sh
sudo chmod +x /usr/local/bin/prysm.sh


./prysm.sh validator accounts create --keystore-path=./keystore

Run beacon mode:
./prysm.sh beacon-chain --datadir=/data --http-web3provider=http://localhost:8545 --holeshky

Run prism validator:
./prysm.sh validator --datadir=/data --wallet-dir=./keystore --password-file=/path/to/password.txt --holeshky


