# httpd test

`start` creates docker container with:

- `conf/` mounted to `/usr/local/apache2/conf`
- `htdocs/` mounted to `/usr/local/apache2/htdocs`

By default these locations are used for configuration and files to be served, respectively.
