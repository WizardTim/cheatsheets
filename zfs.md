[Back to Cheatsheets Index](README.md)
# ZFS Cheatsheet

---

#### List all ZFS file systems, volumes and snapshots

`zfs list`

Additional breakdown of disk space used by snapshots and the dataset  

`zfs list -o space`

List snapshots

`zfs list -t snapshot`

### Access a snapshot

`cd /pool/dataset/.zfs/snapshot/zfs-auto-snap_hrly-2000-01-01-0000`

---

#### Mount a ZFS dataset
A specific one

`sudo zfs mount <dataset>`

All available

`sudo zfs mount -a` or `sudo zfs mount -all`

_Note: You will likely be prompted for your root password and then your ZFS encryption password, read the prompt carefully, there is a limited number of attempts per import of the dataset_

_Note: You don't need to use load-key before using this mount command_

---

#### Get properties of a ZFS dataset 

List all properties of a dataset

`zfs get "all" <dataset>`

Get one particular property from a particular dataset

`zfs get <property> <dataset>`

List one particular property from all available datasets

`zfs get <property>`

---

#### List all ZFS file systems, volumes and snapshots and a breakdown disk space used by snapshots and the dataset  

`zfs get "all" <dataset>`

---

#### Load key (passphrase or keyfile) for a particular natively encrypted ZFS dataset

`sudo zfs load-key <dataset>`

_Note: You will likely be prompted for your root password and then your ZFS encryption password, read the prompt carefully, there is a limited number of attempts per import of the dataset_

---

#### List status of pools and their vdevs  

Once

`zpool status`

One particular pool

`zpool status <pool>`

Every n seconds

`zpool status <n>`

---


#### List key statistics for all pools  

`zpool list`

---

#### Pool management

Import a pool (pool new to machine)

`sudo zpool import <pool>`

Export a pool (pool leaving machine)

`sudo zpool export <pool>`

Offline a pool (pool down for maintenance)

`sudo zpool offline <pool>`

Destroy a pool (non-secure erase)

`sudo zpool destroy <pool>`

---

#### Filesystem management

Create a filesystem on a pool with default/inherited properties

`sudo zfs create <pool>/<filesystem>`

---

#### Device management

Offline a device (either by sdX or UUID, UUID `/dev/disk/by-id/` is strongly recommended)

`sudo zpool offline <pool> <device>`

Add a device for L2ARC cache

`sudo zpool add <pool> cache <device>`
