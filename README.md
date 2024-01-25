# ig-datalogger

Log temperature and mass scale data

Installing node on rpi (use nvm)
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
nvm install node
node -v
npm -v
which node # gets the /path/to/node
sudo su
cd /usr/sbin
ln -s /path/to/node node
```

Installing influxdb on rpi
```bash
wget -qO- https://repos.influxdata.com/influxdb.key | sudo apt-key add -
source /etc/os-release
echo "deb https://repos.influxdata.com/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
sudo apt update && sudo apt install -y influxdb

sudo systemctl unmask influxdb.service
sudo systemctl enable influxdb.service
sudo systemctl start influxdb
```

Installing the repo
```bash
npm install
```

Rebuilding the sources
```bash
npm rebuild
```

For newer versions of yarn
```bash
yarn rebuild
```

Running in test mode
```bash
cd src
node ../bin/run server -t
```

Running in production mode on port 80
```bash
cd src
node ../bin/run server 80
```
