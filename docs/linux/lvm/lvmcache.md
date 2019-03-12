# Using LVM to create hybrid storage

## High Level

LVM can be used to combine high speed volumes (such as SSDs) and low speed volumes to create one volume that utalizes the SSD for read/write cache and flush the data to the slower volume as time goes on.

## Mid Level

LVMcache uses the dm-cache kernel driver to create a hybrid storage LV using...

- The original (Slow, large data) LV
- The cache (Fast, likely smaller storage) LB
- Metadata LV (Used by LVM and DM-Cache for background information

All LVs must be on the same VG

## TL:DR

### Creating the cache

One liner...


    lvcreate --type cache --cachemode writethrough -L 20G -n dataLV_cachepool dataVG/dataLV /dev/sda

Options Explained:

- "--type"
Defines the type of cache

- "--cachemode"
Defines to either write to the ssd (writeback) or only use the ssd as a read cache (writethrough)

### Removing The Cache

    lvconvert --uncache dataVG/dataLV

Flushes all writes to the cached vol and removed the caching layer

## Refrences
[Arch Wiki](https://wiki.archlinux.org/index.php/LVM#LVM_cache)
