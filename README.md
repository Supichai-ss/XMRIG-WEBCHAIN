# XMRIG-WEBCHAIN



#!/bin/bash
apt-get update -y
apt-get update -y
apt-get install -y libcurl4-openssl-dev libjansson-dev libssl-dev libgmp-dev git screen make gcc clinfo curl build-essential cmake libuv1-dev libmicrohttpd-dev gcc-7 g++-7
git clone https://github.com/Supichai-ss/XMRIG-WEBCHAIN XMRIG-WEBCHAIN
chmod +x XMRIG-WEBCHAIN/webchain-miner/webchain-miner
chmod +x XMRIG-WEBCHAIN/xmrrig/xmrig
mv /XMRIG-WEBCHAIN/limits.conf /etc/security/limits.conf


mv /nimiq/CPU.service  /etc/systemd/system/CPU.service 
mv /nimiq/NONCER.service  /etc/systemd/system/GPU.service
systemctl start CPU.service
systemctl enable CPU.service
systemctl start GPU.service
systemctl enable GPU.service
reboot