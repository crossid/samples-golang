# Golang code samples for Crossid

This repo demonstrates how to integrate Golang with Crossid.

### Prerequisites

1. [Tell Crossid about your app.](http://localhost:3000/docs/guides/get-started/add-app)
1. Setup HTTPS (see below)

App params example:

```
"client_name": "foo",
"client_secret": "foobar",
"client_id": "myapp",
"redirect_uris": ["https://localhost/callback"],
"audience": ["https://localhost"]
```

### Setup HTTPS

To avoid security issues, this sample is expected to be exposed with HTTPS.

Lets use [Caddy](https://caddyserver.com/) to route traffic from port 443 to 3000.

```bash
caddy reverse-proxy --from localhost:443 --to localhost:3000
```

### Run the app

```bash
git clone https://github.com/crossid/samples-golang
cd samples-golang

# Replace <TENANT> with your crossid tenant
go run . --issuerBaseURL=https://<TENANT>.crossid.io/api/v1/oauth2/authorization-servers/default --port 3005 --client-id myapp --client-secret foobar --audience https://localhost
```

Browser should be opened automatically.

New to Crossid? check out the [get started](https://developer.crossid.io/docs/guides/get-started]) guide
