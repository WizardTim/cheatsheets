[Back to Cheatsheets Index](README.md)
# badblocks
---
### Flags
* `-b` block size, 512 or 4096 unless you have a highly specialised enterprise drive (influences speed)
* `-c` cache size (influences speed)

---

#### Scan drive in read only mode
Safest test, no data will be written however physically damaged disks may be further damaged by continuous reads.

`badblocks -vs -b 4096 -c 65536 /dev/sda`

---

#### Scan drive in non-destructive read-write mode
Interrupting this with `CTRL+C` will be handled gracefully without data loss, however an ungraceful error can occur in IO or in OS resulting in data loss.

`badblocks -nvs -b 4096 -c 65536 /dev/sda`

---

#### Scan drive in DESTRUCTIVE multi-pass write mode (4-passes [0xAA, 0x55, 0xFF, 0x00])
This will overwrite all data. Note: Windows may think drives that have been zeroed have damaged filesystems, format on Linux to avoid this.
`badblocks -wvs -b 4096 -c 65536 /dev/sda`

---
