# Socat Docker Image

This image includes the useful command socat to create a connection to external service.

## Examples

Run as socat on host system:

```bash
docker run --rm --name socat_mysql -p 3306 -d TCP4-LISTEN:3306,reuseaddr,fork TCP-CONNECT:the.real.mysql.domain:3306
```

Then you can `--link` to this container as service.

```bash
docker run --name pma -d --link socat_mysql:db -p 8080:80 phpmyadmin/phpmyadmin
```

