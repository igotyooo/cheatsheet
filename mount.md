### Mount after format ([source](https://joshstrange.com/ubuntu-formatting-a-3tb-drive/))
1. Find and choose your target drive name.</br>
`$ lsblk`</br>
`$ sudo parted /dev/sdX`</br>
2. In the parted interactive console, type</br>
`(parted) mklabel gpt`</br>
`(parted) unit TB`</br>
`(parted) mkpart primary 0.00TB 100%`</br>
`(parted) quit`</br>
3. Format the dirive.</br>
`$ sudo mkfs.ext4 /dev/sdX1`</br>
`$ sudo tune2fs -m 1 /dev/sdX1`</br>
4. Make a mount point.</br>
`$ mkdir <mount point>`</br>
5. Copy the UUID of your drive from the output of</br>
`$ sudo blkid`</br>
6. Add the following in `/etc/fstab`.</br>
`<UUID> <mount point> ext4 defaults 1 2`</br>
7. Mount.</br>
`$ sudo mount -a`</br>
8. Give authorithy if the mount point is unreachable for you.</br>
`$ chown -R dgyoo /iron`</br>
`$ chmod +w /iron`</br>

### Mount ONLY
1. Find your target drive name.</br>
`$ lsblk`</br>
2. Make a mount point.</br>
`$ mkdir <mount point>`</br>
3. Copy the UUID of your drive from the output of</br>
`$ sudo blkid`</br>
4. Add the following in `/etc/fstab`.</br>
`<UUID> <mount point> ext4 defaults 1 2`</br>
5. Mount.</br>
`$ sudo mount -a`</br>
