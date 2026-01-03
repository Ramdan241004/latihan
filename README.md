# latihan

```sh
cat << EOF > /etc/fstab
fs-04b7a1ef0ac7a1730.efs.us-east-1.amazonaws.com:/ /var/www/efs nfs4 nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 0 0
EOF
```
