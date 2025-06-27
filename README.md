install:
wget https://github.com/XTLS/Xray-core/releases/latest/download/Xray-linux-64.zip
unzip Xray-linux-64.zip
chmod +x xray
sudo mv xray /usr/local/bin/

start:
xray run -config trojan-linux.json

test tunnel SOCKS5:
proxychains curl https://ipinfo.io

solv proxychains:
sudo vim /etc/proxychains4.conf

change from this;
[ProxyList]
socks4 127.0.0.1 9050

to this;
[ProxyList]
socks5 127.0.0.1 1080



