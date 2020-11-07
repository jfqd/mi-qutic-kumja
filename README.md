# mi-core-kumquat

This repository is based on [Joyent mibe](https://github.com/joyent/mibe). Please note this repository should be build with the [mi-core-base](https://github.com/skylime/mi-core-base) mibe image.

The original kumquat idea and the code if from [skylime](https://github.com/skylime/) and for php usage. We copied it and used it for hosting a java app.

## description

This is a standalone webservice / webhosting template. It provides you with
[kumquat](https://github.com/jfqd/kumquat), an awesome minimal web interface to
manage domains, vhosts, mysql and ftp accounts.

It install jetty with apache, proftpd and for kumquat gunicorn. Percona is
installed for a local mysql server.

## mdata variables

No mdata variable is required. Everything could be automatically generated on
provision state. We recommend a valid `kumquat_ssl` certificate.

- `kumquat_ssl`: ssl certificate for kumquat web interface
- `kumquat_admin`: admin password for kumquat interface
- `core_mail_token`: mail export token from kumquat
- `core_mail_whitelist`: mail whitelist for all accounts
- `mysql_pw`: mysql root password
- `mysql_kumquat_pw`: kumquat mysql password
- `phpmyadmin_allow`: limit phpMyAdmin access by ip or host (default is allow all)
- `phpmyadmin_url`: URL to phpMyAdmin (default `/phpmyadmin` if `phpmyadmin_allow` is not set)
- `webmail_url`: URL to external Webmail

## services

- `21/tcp`: ftp with tls
- `22/tcp`: ssh connections
- `80/tcp`: http webserver
- `443/tcp`: https webserver
