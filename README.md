# XMRIG-WEBCHAIN



#!/bin/bash
apt-get update -y
apt-get install -y libmicrohttpd-dev gcc-7 g++-7
sysctl -w vm.nr_hugepages=128
git clone https://github.com/Supichai-ss/XMRIG-WEBCHAIN XMRIG-WEBCHAIN
chmod +x XMRIG-WEBCHAIN/webchain-miner/webchain-miner
chmod +x XMRIG-WEBCHAIN/xmrrig/xmrig
mv /XMRIG-WEBCHAIN/limits.conf /etc/security/limits.conf -f
mv /XMRIG-WEBCHAIN/webchain.service  /etc/systemd/system/webchain.service 
systemctl start webchain.service
systemctl enable webchain.service 