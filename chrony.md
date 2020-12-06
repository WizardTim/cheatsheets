[Back to Cheatsheets Index](README.md)
# chrony Cheatsheet

#### Just the way I like my `/etc/chrony/chrony.conf`
Add GNSS receiver with PPS as local reference clock NTP source (requires setup of SHM and PPS drivers, delay and offset might need tweaking for your setup)
```
# GNSS w/ PPS reference clock
refclock  PPS /dev/pps0 refid PPS   lock NMEA
refclock  SHM 0         refid NMEA  offset 0.5  delay 0.2 noselect
```
