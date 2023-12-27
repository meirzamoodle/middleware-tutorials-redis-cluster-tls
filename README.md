# Setting up a Redis Cluster with TLS

Create a redis cluster using TLS for client and inter-nodes communications. Read the full post at <https://medium.com/@ozcankasal/setting-up-a-redis-cluster-with-tls-e02d53d9faa7>

![cluster topology](files/redis-cluster-topology.png)

This repo uses a self-signed CA certificate (`tls/ca.crt`) to create signed client certificates. You can create your own self-signed CA certificate using the following commands.

```bash
openssl genrsa 4096 > ca.key
```

```bash
openssl req -new -x509 -nodes -sha256 -key ca.key -days 3650 -subj "/C=TR/CN=example" -out ca.crt
``` 

# Usage

1. Download the project `git clone git@github.com:meirzamoodle/middleware-tutorials-redis-cluster-tls.git`
2. `cd middleware-tutorials-redis-cluster-tls` 
3. `docker-compose up --build`
