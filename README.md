# Bootstrap Rancher

Start Rancher with nginx SSL Proxy:

```
docker-compose up -d
```


Get API Key, secure Rancher with authentication:

```
curl -v -X POST -H 'Accept: application/json' -H 'Content-Type: application/json'  \
  -d '{	"type":"apikey",
	"accountId":"1a5",
	"name":"admin",
	"description":null,
	"created":null,
	"kind":null,
	"removed":null,
	"uuid":null
	}'\
  https://localhost:8443/v1/apikey

curl -X POST \
  -H 'Accept: application/json' -H 'Content-Type: application/json' \
  -d '{ "type": "localAuthConfig",
	"accessMode": "unrestricted",
	"enabled": true,
	"name": "",
	"username": "user",
	"password": "pass"
	}' \
  https://localhost:8443/v1/localAuthConfig
```
