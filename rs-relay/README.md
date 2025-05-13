# วิธีติดตั้ง (How to install)
สร้างโฟรเดอร์ RS-Relay
```sh
mkdir re-relay 
```
```sh
cd re-relay 
```
สร้างโฟรเดอร์เก็บข้อมูล
```sh
mkdir data
```
ดาวน์โหลดไฟล์ config.toml
```sh
wget -O config.toml https://raw.githubusercontent.com/scsibug/nostr-rs-relay/refs/heads/master/config.toml
```
แก้ไขไฟล์ config.toml
```sh
nano config.toml
```

```
[info]
# The advertised URL for the Nostr websocket.
relay_url = "wss://nostr.example.com/"

# Relay information for clients.  Put your unique server name here.
name = "nostr-rs-relay"

# Description
description = "A newly created nostr-rs-relay.\n\nCustomize this with your own info."

# Administrative contact pubkey
pubkey = "963a4d3b4993f9f0e79ce002ef2f4f80df55bd5eb0c1f077a3fdccdec8200652"
```

ดาวน์โหลดไฟล์ docker-compose.yaml
```sh
wget -O docker-compose.yaml https://raw.githubusercontent.com/notoshi404/nostr-relay-docker/refs/heads/main/rs-relay/docker-compose.yml
```
```sh
docker compose up -d
```

Browse to https://[IP Address]:8080
