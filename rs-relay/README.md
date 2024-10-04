# วิธีติดตั้ง (How to install)

~~~
git clome https://github.com/notoshi404/nostr-relay-docker.git
~~~

แก้ไขไฟล์ config.toml
~~~
sudo nano /nostr-relay-docker/rs-relay/config.toml
~~~

~~~
[info]
# The advertised URL for the Nostr websocket.
relay_url = "wss://nostr.example.com/"

# Relay information for clients.  Put your unique server name here.
name = "nostr-rs-relay"

# Description
description = "A newly created nostr-rs-relay.\n\nCustomize this with your own info."

# Administrative contact pubkey
pubkey = "963a4d3b4993f9f0e79ce002ef2f4f80df55bd5eb0c1f077a3fdccdec8200652"
~~~

~~~
sudo docker compose up -d
~~~

Browse to https://[IP Address]:8080