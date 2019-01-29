
## Setup dev

Install grav-admin from zip
Install php
May need to manually install php-gd and turn this extension on in `/etc/php/php.ini`.

```bash
cd grav-admin/

rm -r user

ln -s ~/my/location/night-rules-skeleton ~/my/location/grav-admin/user

bin/gpm install problems
bin/gpm install error
bin/gpm install admin

ln -s ~/my/location/night-rules-theme ~/my/location/grav-admin/user/themes/night-rules
```

## Run dev

Run the simple dev server from `grav-admin/` :
```bash
php -S localhost:8000 system/router.php
```
