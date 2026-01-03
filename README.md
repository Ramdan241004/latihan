# latihan

```sh
cat << EOF > /etc/fstab
fs-04b7a1ef0ac7a1730.efs.us-east-1.amazonaws.com:/ /var/www/efs nfs4 nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 0 0
EOF
```

```env
cat << EOF > /var/www/efs/modul2.smkn1panjalu.cloud/.env
APP_NAME="Portal - SMK Cloud Provider"
APP_ENV=production
APP_KEY=
APP_DEBUG=true
APP_URL=https://modul2.smkn1panjalu.cloud
LOG_CHANNEL=stack
LOG_LEVEL=debug
DB_CONNECTION=mysql
DB_HOST=modul2.cyiuuaul582u.us-east-1.rds.amazonaws.com
DB_PORT=3306
DB_DATABASE=modul2
DB_USERNAME=modul2
DB_PASSWORD=12345678
BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DRIVER=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120
MEMCACHED_HOST=127.0.0.1
MEMCACHED_PORT=
REDIS_HOST=modul2.fuofdh.clustercfg.use1.cache.amazonaws.com
REDIS_PASSWORD=null
REDIS_PORT=6379
MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS=null
MAIL_FROM_NAME="${APP_NAME}"
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false
PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_APP_CLUSTER=mt1
MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
EOF
```

```sh
cat << 'EOF' > /var/www/efs/modul2.smkn1panjalu.cloud/public/health
OK
EOF
```

```sh
cat <<EOF > /etc/apache2/sites-available/modul2.smkn1panjalu.cloud.conf
<VirtualHost *:80>
    ServerName modul2.smkn1panjalu.cloud
    DocumentRoot /var/www/efs/modul2.smkn1panjalu.cloud/public

    <Directory /var/www/efs/modul2.smkn1panjalu.cloud/public>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog \${APACHE_LOG_DIR}/error.log
    CustomLog \${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
EOF
```
