How to install **strfry** 
======

สร้างโฟรเดอร์ strfry
```sh
mkdir strfry && cd strfry
```
```sh
mkdir strfry-db
```
ดาวน์โหลดไฟล์ strfry.conf
```sh
wget -O strfry.conf https://raw.githubusercontent.com/notoshi404/nostr-relay-docker/refs/heads/main/strfry/strfry.conf
```

แก้ไขไฟล์ strfry.conf
```sh
sudo nano strfry.conf
```
```
.
.
relay {
    # Interface to listen on. Use 0.0.0.0 to listen on all interfaces (restart required)
    bind = "0.0.0.0"

    # Port to open for the nostr websocket protocol (restart required)
    port = 7777

    # Set OS-limit on maximum number of open files/sockets (if 0, don't attempt to set) (restart required)
    nofiles = 0

    # HTTP header that contains the client's real IP, before reverse proxying (ie x-real-ip) (MUST be all lower-case)
    realIpHeader = ""

    info {
        # NIP-11: Name of this server. Short/descriptive (< 30 characters)
        name = "strfry"

        # NIP-11: Detailed information about relay, free-form
        description = "This is a strfry instance."

        # NIP-11: Administrative nostr pubkey, for contact purposes
        pubkey = "[Public_Key(hex)]"

        # NIP-11: Alternative administrative contact (email, website, etc)
        contact = ""

        # NIP-11: URL pointing to an image to be used as an icon for the relay
        icon = ""

        # List of supported lists as JSON array, or empty string to use default. Example: [1,2]
        nips = ""
    }
.
.
```
```sh
docker pull notoshi/strfry:1.0.4u
```
ดาวน์โหลดไฟล์ docker-compose.yaml
```sh
wget -O docker-compose.yaml https://raw.githubusercontent.com/notoshi404/nostr-relay-docker/refs/heads/main/strfry/docker-compose.yaml
```
### docker-compose.yaml
```
services:
  strfry:
    container_name: strfry
    image: notoshi/strfry:1.0.4u
    ports:
        - 7777:7777
    volumes:
        - ./strfry-db:/app/strfry-db
        - ./strfry.conf:/etc/strfry.conf
```
```sh
docker compose up -d
```
## [strfry](https://github.com/hoytech/strfry)
> Version 1.0.4
.