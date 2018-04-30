# httpd Reverse Proxy Test

Proof of concept `apache2`/`httpd` reverse proxy.

http(s) Requests to host port `8080` are routed to container `reverseproxy:80`, which proxies the request to container `httpd:80`.

The `start` bash script facilitates this. It creates the following:

## bridge network `reverse-proxy-net`

Attached to containers

- `reverseproxy`
- `httpd`

## httpd container `--name httpd`

- `htdocs/` mounted to `/usr/local/apache2/htdocs`
- Serving on `reverse-proxy-net:80`
- default `/usr/local/apache2/conf/`

## httpd container `--name reverseproxy`

- Reverse proxy `conf/` mounted to `/usr/local/apache2/conf`
- Port `80` exposed as `8080` on host through default bridge
