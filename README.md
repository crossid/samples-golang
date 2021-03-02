# Golang code samples for Crossid

This repo demonstrates how to integrate Golang with Crossid.

### Setup HTTPS

To avoid security issues, this sample is expected to be exposed with HTTPS.

Lets use [Caddy](https://caddyserver.com/) to route traffic from port 443 to 3000.

```bash
caddy reverse-proxy --from localhost:443 --to localhost:3000
```

Then run:

```bash
git clone https://github.com/crossid/samples-golang
cd samples-golang

# Replace <TENANT> with your crossid tenant
go run . --issuerBaseURL=https://<TENANT>.crossid.io/oauth2/default
```

Browser should be opened automatically.

New to Crossid? check out the [get started](https://developer.crossid.io/docs/guides/get-started]) guide