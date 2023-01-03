# socks5-v2ray-bridge
Deploy Socks5 Proxy Bridge with V2ray Upstream.

## Topology

Our topology is:

`[Client] => [Socks5 (Bridge)] => [v2ray (Upstream)]`

Client uses socks5 proxy to connect to socks5 proxy bridge server. And bridge server connects to upstream server.

## Getting started

### On **Upstream** server:
**You'll need a Domain pointing to your upstream server**

To deploy a v2ray upstream server, go to this [link](https://www.oilandfish.com/posts/v2ray.html#1-3) and deploy a v2ray server.

### On **Bridge** server:

First, download v2ray-core:

```
mkdir v2ray; cd v2ray
wget 'https://github.com/v2ray/v2ray-core/releases/download/v4.28.2/v2ray-linux-64.zip'
unzip v2ray-linux-64.zip
```

And copy `socks5-v2ray-bridge/config.json` to `v2ray/config.json` and **change the placeholders**.
Placeholders are for **IP, Domain, UUID of upstream server, and alterid**.

Then, while you're in `v2ray` directory, run command below to start socks5 bridge server.

```
./v2ray -config=config.json
```

You can also change `port` and `listen` address for your desired needs.
You're done! Now you can connect to your **bridge server's IP** and port **1080** using a socks5 proxy client!
