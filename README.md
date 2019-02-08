
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
bin/gpm install pagination

ln -s ~/my/location/night-rules-theme ~/my/location/grav-admin/user/themes/night-rules
```

## Run dev

Run the simple dev server from `grav-admin/` :
```bash
php -S localhost:8000 system/router.php
```

watch scss modifications :
```bash
cd user/themes/night-rules-theme
scss --watch scss:css
```

## Deploy with YUNOHOST

install grav as a yunohost app

```bash
# from grav folder in /var/www/

# remove base user folder
rm -r user

# clone the new user folder
git clone https://github.com/Axolotle/night-rules-website.git user

bin/gpm install problems
bin/gpm install error
bin/gpm install admin
bin/gpm install pagination

# add the theme
cd user/theme/
git clone https://github.com/Axolotle/night-rules-theme night-rules

# reset files and folders ownership
chown -R grav:grav /var/www/grav/user

# change the admin route
mkdir user/config/plugins
cp user/plugins/admin/admin.yaml user/config/plugins/
# then change the base route in user/config/plugins/admin.yaml
```
