[Back to Cheatsheets Index](README.md)
# hdparm Cheatsheet

### Caution: hdparm can permanently and irreversibly destroy data and physical hardware

---

#### Unlock a password protected ATA drive bricked by an interrupted/failed ATA secure erase initiated by [GNOME Disk Utility](https://en.wikipedia.org/wiki/GNOME_Disks) or udisks
Password used by GNOME Disks/udisks to lock the drive during the erase is literally `xxxx`.

`sudo hdparm --security-unlock "xxxx" /dev/<device>`

`sudo hdparm --security-disable "xxxx" /dev/<device>`

---
