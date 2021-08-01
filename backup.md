# BACKUP

## Gnome Settings

### General Settings
```
dconf dump / > full-backup
mkdir -p ~/Documents/system-backup/
mv full-backup ~/Documents/system-backups/
```

### Icons and Themes
```
mv ~/.icons ~/Documents/system-backups/
mv ~/.themes ~/Documents/system-backups/
tar -cvpf system-backups.tar.gz ~/Documents/system-backups
```

### Restore Backup
```
tar --extract --file system-backups.tar.gz -C ~/ --strip-components=2
cd system-backups
dconf load / < full-backup
mv .icons ~/.icons 
mv .themes ~/.themes 
```