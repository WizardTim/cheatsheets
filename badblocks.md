[Back to Cheatsheets Index](README.md)
# badblocks
Further in depth documentation on [ArchWiki](https://wiki.archlinux.org/title/badblocks) and [man.archlinux.org](https://man.archlinux.org/man/badblocks.8).

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
Interrupting this with a single `CTRL+C` will be handled gracefully without data loss, however an ungraceful error can occur in the drive itself, IO or in OS resulting in data loss.

`badblocks -nvs -b 4096 -c 65536 /dev/sda`

---

#### Scan drive in DESTRUCTIVE multi-pass write mode (4-passes [0xAA, 0x55, 0xFF, 0x00])
This will overwrite all data.
`badblocks -wvs -b 4096 -c 65536 /dev/sda`
*Note: after the drive is overwritten Windows may think drive is damaged and may prevent you from formatting it in the Disk Management GUI, ensure to format the drive with a new partition table (GPT or MBR) in Linux before use on Windows.*
*Note: this should not be used as a replacement for a secure erase.*
---
