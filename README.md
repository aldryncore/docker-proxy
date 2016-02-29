# nginx Proxy

[![](https://badge.imagelayers.io/aldryn/docker-proxy:latest.svg)](https://imagelayers.io/?images=aldryn/docker-proxy:latest 'Get your own badge on imagelayers.io')

This docker image will proxy all HTTP requests on port 80 to the root path specified in the `PROXY_UPSTREAM` environment variable.

The entire URI will be sent to the redirected path like this:

When `PROXY_UPSTREAM` is set to `https://www.mydomain.com`:
```
/ => https://www.mydomain.com/
/asdf => https://www.mydomain.com/asdf
/asdf?asdf=1 => https://www.mydomain.com/asdf?asdf=1
```

## Example

`docker run -p 3000:80 -e "PROXY_UPSTREAM=https://www.mydomain.com" aldryn/docker-proxy`
