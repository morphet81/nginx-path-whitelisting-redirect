# Nginx partial white listing

This snippet project demonstrates how to redirect the traffic on a specif path when the origin IP address is not authorized.
- `endpoints.my` serves
  - an API on `/api/v1`
    - `/api/v1/GetUser`
    - `/api/v1/GetAccount`
  - the API documentation on `/api/v1/doc`
  - static content on `/static`
- All trafic on `endpoints.my` to access static content and the documentation is authorized to anyone
- All trafic on `endpoint.my` to access the API is redirected to `apim.my` if the origin IP is not authorized

## Setup (Mac OS)

### 1. Setup hosts

Open `/etc/hosts` file and add `endpoints.my` and `apim.my`
```bash
...
127.0.0.1       apim.my
127.0.0.1       endpoints.my
```

### 2. Start the container

Run `docker-compose up`