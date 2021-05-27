[Back to Cheatsheets Index](README.md)
# badblocks

---

#### Scan drive in read only mode

`badblocks -vs -b 4096 -c 65536 /dev/sda`

---

#### Scan drive in non-destructive read-write mode

`badblocks -nvs -b 4096 -c 65536 /dev/sda`

---

#### Scan drive in DESTRUCTIVE multi-pass write mode (4-passes [0xAA, 0x55, 0xFF, 0x00])

`badblocks -wvs -b 4096 -c 65536 /dev/sda`

---
