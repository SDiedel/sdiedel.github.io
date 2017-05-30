# Backup script Docker host

I use this very simple backup script for backing up my config files to my NAS

```
#!/bin/sh

# Backup script for Docker volumes

# Set vars
filename=$(date +%Y-%m-%d)
backuplocation=/Backup

# Tar the entire docker mount
tar -zcf $filename.tar.gz /docker

# Copy to backup location
cp $filename.tar.gz $backuplocation
cp /etc/fstab $backuplocation/$filename.fstab

# Remove tar file
rm $filename.tar.gz
```

Whatevah!
