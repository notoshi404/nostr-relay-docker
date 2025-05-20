How to install **bostr2** 
======

สร้างโฟรเดอร์ bostr2
```sh
mkdir bostr2 && cd bostr2
```

ดาวน์โหลดไฟล์ config.yaml
```sh
wget -O config.yaml https://raw.githubusercontent.com/Yonle/bostr2/refs/heads/master/config.example.yaml
```

แก้ไขไฟล์ config.yaml
```sh
nano config.yaml
```
```
# your bostr address.
my_address: wss://bostr.example.com

# If relays is provided, then tracker could be optional
relays:
# - wss://relay.example1.com
# - wss://relay.example2.com

# If trackers is provided, then relays could be optional
trackers:
# - wss://tracker.example1.com
# - wss://tracker.example2.com

nip_11:
  name: bostr2
  description: Nostr relay bouncer
  software: git+https://codeberg.org/Yonle/bostr2
  pubkey: 0000000000000000000000000000000000000000000000000000000000000000
  contact: unset
.
.
```

สร้างไฟล์ docker-compose.yaml
```sh
nano docker-compose.yaml
```
```
services:
  bostr2:
    image: notoshi/bostr2:latest
    container_name: bostr2
    ports:
      - "8080:8080"
    volumes:
      - ./config.yaml:/app/config.yaml
    restart: unless-stopped
```

Run container
```sh
docker compose up -d
```
---

## [bostr2](https://github.com/Yonle/bostr2)