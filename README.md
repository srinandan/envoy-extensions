
# custom-plugin

This sample implements Envoy's (external authorization)[https://www.envoyproxy.io/docs/envoy/latest/api-v2/config/filter/http/ext_authz/v2/ext_authz.proto] filter

## Testing locally

These steps work on Linux/Debian machines

Step 1: Run ext-authz server

```bash
go run ./server/main.go
```

Step 2: Run envoy

```bash
envoy -c envoy.yaml
```

Step 3: Test endpoint(s)

Pass no backend header
```bash
curl localhost:8080/httpbin/get -v
```

Pass mocktarget header
```bash
curl localhost:8080/httpbin/get -v -H "x-backend-url: mocktarget"
```

Pass postman header
```bash
curl localhost:8080/httpbin/get -v -H "x-backend-url: postman"
```
___

## Support

This is not an officially supported Google product
