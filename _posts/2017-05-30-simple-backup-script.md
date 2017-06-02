# Backup script Docker host

I use this very simple backup script for backing up my config files to my NAS

```
#!/bin/sh

echo Backup script for Docker volumes

# Set var
filename=$(date +%Y-%m-%d)
oldfiles=$(date +%Y-%m-%d -d "now -7 days")
backuplocation=/Backup

# Tar the entire docker mount
tar -zcf $filename.tar.gz /docker

# Remove files from 7 days ago
rm $backuplocation/$oldfiles.tar.gz
rm $backuplocation/$oldfiles.fstab

# Copy to backup location
cp $filename.tar.gz $backuplocation
cp /etc/fstab $backuplocation/$filename.fstab

# Remove tar file
rm $filename.tar.gz
```

Whatevah!
