### tasks
```
root@localhost:~# mkdir linux_test
root@localhost:~# touch file1.txt linux
root@localhost:~# touch file1.txt linux_test
root@localhost:~# touch file2.txt linux_test
root@localhost:~# touch script.sh linux_test
root@localhost:~# echo "Welcome to linux" > file1.txt
root@localhost:~# cp file1.txt welcome.txt
root@localhost:~# mv file2.txt /tmp
root@localhost:~# useradd testuser
root@localhost:~# passwd testuser
New password: 
BAD PASSWORD: The password fails the dictionary check - it is based on a dictionary word
Retype new password: 
Sorry, passwords do not match.
passwd: Authentication token manipulation error
passwd: password unchanged
root@localhost:~# passwd testuser
New password: 
BAD PASSWORD: The password fails the dictionary check - it is based on a dictionary word
Retype new password: 
passwd: password updated successfully
root@localhost:~# groupadd interns
root@localhost:~# usermod -aG testuser interns
usermod: user 'interns' does not exist
root@localhost:~# usermod -aG interns testuser
root@localhost:~# touch secret.txt 
root@localhost:~# chmod 600 secret.txt
root@localhost:~# chown testuser secret.txt
root@localhost:~# find /etc -type f -name .conf 
root@localhost:~# find /var/log -type f -name ".log" > /dev/null wc-l
find: paths must precede expression: `wc-l'
root@localhost:~# find /var/log -type f -name "*.log" > /dev/null wc-l
find: paths must precede expression: `wc-l'
root@localhost:~# ip -a address
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: ens160: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:0c:29:bc:24:37 brd ff:ff:ff:ff:ff:ff
    altname enp3s0
    altname enx000c29bc2437
    inet 192.168.1.71/24 brd 192.168.1.255 scope global dynamic noprefixroute ens160
       valid_lft 85398sec preferred_lft 85398sec
    inet6 2404:7c80:8c:cba8:20c:29ff:febc:2437/64 scope global dynamic noprefixroute 
       valid_lft 85931sec preferred_lft 3131sec
    inet6 fe80::20c:29ff:febc:2437/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
root@localhost:~# hostname
localhost.localdomain
root@localhost:~# ping google.com
PING google.com (2404:6800:4013:807::64) 56 data bytes
64 bytes from lcdelw-in-f100.1e100.net (2404:6800:4013:807::64): icmp_seq=1 ttl=114 time=22.8 ms
64 bytes from lcdelw-in-f100.1e100.net (2404:6800:4013:807::64): icmp_seq=2 ttl=114 time=255 ms
64 bytes from lcdelw-in-f100.1e100.net (2404:6800:4013:807::64): icmp_seq=3 ttl=114 time=48.8 ms
64 bytes from lcdelw-in-f100.1e100.net (2404:6800:4013:807::64): icmp_seq=4 ttl=114 time=16.0 ms
64 bytes from lcdelw-in-f100.1e100.net (2404:6800:4013:807::64): icmp_seq=5 ttl=114 time=41.9 ms
^C
--- google.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4017ms
rtt min/avg/max/mdev = 16.009/76.803/254.517/89.661 ms
root@localhost:~# nmcli connection add type ethernet con-name lab-connection ifname eth0 ip4 192.168.1.71/24 gw4 192.168.1.255
Connection 'lab-connection' (c6eb7e16-8045-40ff-94d5-71c1cf3619f3) successfully added.
root@localhost:~# nmcli modify lab-connection ipv4 dns" 8.8.8.8"
Error: argument 'modify' not understood. Try passing --help instead.
root@localhost:~# nmcli  conn modify lab-connection ipv4 dns" 8.8.8.8"
Error: invalid <setting>.<property> 'ipv4'.
root@localhost:~# nmcli  conn modify lab-connection ipv4.dns" 8.8.8.8"
Error: value for 'ipv4.dns 8.8.8.8' is missing.
root@localhost:~# nmcli  conn modify lab-connection ipv4.dns "8.8.8.8"
root@localhost:~# lsblk
NAME          MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sr0            11:0    1  9.5G  0 rom  /run/media/root/RHEL-10-1-BaseOS-x86_64
nvme0n1       259:0    0  100G  0 disk 
├─nvme0n1p1   259:1    0    1M  0 part 
├─nvme0n1p2   259:2    0    1G  0 part /boot
└─nvme0n1p3   259:3    0   99G  0 part 
  ├─rhel-root 253:0    0 61.3G  0 lvm  /
  ├─rhel-swap 253:1    0  7.8G  0 lvm  [SWAP]
  └─rhel-home 253:2    0 29.9G  0 lvm  /home
nvme0n2       259:4    0   20G  0 disk 
nvme0n3       259:5    0   20G  0 disk 
nvme0n4       259:6    0   20G  0 disk 
nvme0n5       259:7    0   20G  0 disk 
root@localhost:~# fdisk /dev/nvme0n2

Welcome to fdisk (util-linux 2.40.2).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table.
Created a new DOS (MBR) disklabel with disk identifier 0x55a34a92.

Command (m for help): n
Partition type
   p   primary (0 primary, 0 extended, 4 free)
   e   extended (container for logical partitions)
Select (default p): p
Partition number (1-4, default 1): 1
First sector (2048-41943039, default 2048): 
Last sector, +/-sectors or +/-size{K,M,G,T,P} (2048-41943039, default 41943039): +100M

Created a new partition 1 of type 'Linux' and of size 100 MiB.

Command (m for help): w
The partition table has been altered.
Calling ioctl() to re-read partition table.
Syncing disks.

root@localhost:~# mkfs.ext4 /dev/nvme0n2
mke2fs 1.47.1 (20-May-2024)
Found a dos partition table in /dev/nvme0n2
Proceed anyway? (y,N) y
Creating filesystem with 5242880 4k blocks and 1310720 inodes
Filesystem UUID: 2b72cdd1-90e8-4888-b754-1a8e9b05fd9d
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
	4096000

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done   

root@localhost:~# mkdir -p /mnt/testdisk
root@localhost:~# mount /dev/nvme0n2 /mnt/testdisk
root@localhost:~# fstab
bash: fstab: command not found...
root@localhost:~# vim fstab
root@localhost:~# vim /etc/fstab
root@localhost:~# vim /etc/fstab
root@localhost:~# vim /etc/fstab
root@localhost:~# pvcreate /dev/nvme0n3
  Physical volume "/dev/nvme0n3" successfully created.
root@localhost:~# vgcreate vg_test /dev/nvme0n3
  Volume group "vg_test" successfully created
root@localhost:~# lvcreate -L 200M -n lv_data  
  No command with matching syntax recognised.  Run 'lvcreate --help' for more information.
  Nearest similar command has syntax:
  lvcreate    --type error -L|--size Size[m|UNIT] VG
  Create an LV that returns errors when used.

root@localhost:~# --help
bash: --help: command not found...
root@localhost:~# lvcreate --help
  lvcreate - Create a logical volume

  Create a linear LV.
  lvcreate -L|--size Size[m|UNIT] VG
	[ --type linear ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a striped LV.
  lvcreate -i|--stripes Number -L|--size Size[m|UNIT] VG
	[ --type striped ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a raid1 or mirror LV.
  Implicit type is defined by lvm.conf global/mirror_segfault_default.
  lvcreate -m|--mirrors Number -L|--size Size[m|UNIT] VG
	[ --type raid1|mirror ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[    --mirrorlog core|disk ]
	[    --minrecoveryrate Size[k|UNIT] ]
	[    --maxrecoveryrate Size[k|UNIT] ]
	[    --raidintegrity y|n ]
	[    --raidintegritymode String ]
	[    --raidintegrityblocksize Number ]
	[    --integritysettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a raid LV (a specific raid level must be used, e.g. raid1).
  lvcreate    --type raid -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -m|--mirrors Number ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[    --minrecoveryrate Size[k|UNIT] ]
	[    --maxrecoveryrate Size[k|UNIT] ]
	[    --raidintegrity y|n ]
	[    --raidintegritymode String ]
	[    --raidintegrityblocksize Number ]
	[    --integritysettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a raid10 LV.
  lvcreate -m|--mirrors Number -i|--stripes Number -L|--size Size[m|UNIT] VG
	[ --type raid10 ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[    --minrecoveryrate Size[k|UNIT] ]
	[    --maxrecoveryrate Size[k|UNIT] ]
	[    --raidintegrity y|n ]
	[    --raidintegritymode String ]
	[    --raidintegrityblocksize Number ]
	[    --integritysettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a COW snapshot LV of an origin LV.
  lvcreate -s|--snapshot -L|--size Size[m|UNIT] LV
	[ --type snapshot ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -c|--chunksize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a thin pool.
  lvcreate    --type thin-pool -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -T|--thin ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --thinpool LV_new ]
	[    --discards passdown|nopassdown|ignore ]
	[    --errorwhenfull y|n ]
	[    --pooldatavdo y|n ]
	[    --compression y|n ]
	[    --deduplication y|n ]
	[    --vdosettings String ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a cache pool.
  lvcreate    --type cache-pool -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -H|--cache ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a thin LV in a thin pool.
  lvcreate -V|--virtualsize Size[m|UNIT]    --thinpool LV VG
	[ --type thin ] (implied)
	[ -T|--thin ]
	[ COMMON_OPTIONS ]

  Create a thin LV that is a snapshot of an existing thin LV.
  lvcreate -s|--snapshot LV
	[ --type thin ] (implied)
	[ COMMON_OPTIONS ]

  Create a thin LV that is a snapshot of an external origin LV.
  lvcreate    --type thin    --thinpool LV LV
	[ -T|--thin ]
	[ COMMON_OPTIONS ]

  Create a LV that returns VDO when used.
  lvcreate    --type vdo -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -V|--virtualsize Size[m|UNIT] ]
	[    --vdo ]
	[    --vdopool LV_new ]
	[    --compression y|n ]
	[    --deduplication y|n ]
	[    --vdosettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach the specified cachepool
  which converts the new LV to type cache.
  lvcreate    --type cache -L|--size Size[m|UNIT]    --cachepool LV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -H|--cache ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach the specified cachevol
  which converts the new LV to type cache.
  lvcreate    --type cache -L|--size Size[m|UNIT]    --cachevol LV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach a cachevol created from
  the specified cache device, which converts the
  new LV to type cache.
  lvcreate    --type cache -L|--size Size[m|UNIT]    --cachedevice PV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachesize Size[m|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach the specified cachevol
  which converts the new LV to type writecache.
  lvcreate    --type writecache -L|--size Size[m|UNIT]    --cachevol LV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach a cachevol created from
  the specified cache device, which converts the
  new LV to type writecache.
  lvcreate    --type writecache -L|--size Size[m|UNIT]    --cachedevice PV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[    --cachesize Size[m|UNIT] ]
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Common options for command:
	[ -a|--activate y|n|ay ]
	[ -A|--autobackup y|n ]
	[ -C|--contiguous y|n ]
	[ -M|--persistent y|n ]
	[ -j|--major Number ]
	[ -k|--setactivationskip y|n ]
	[ -K|--ignoreactivationskip ]
	[ -n|--name String ]
	[ -p|--permission rw|r ]
	[ -r|--readahead auto|none|Number ]
	[ -W|--wipesignatures y|n ]
	[ -Z|--zero y|n ]
	[    --addtag Tag ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --setautoactivation y|n ]
	[    --ignoremonitoring ]
	[    --metadataprofile String ]
	[    --minor Number ]
	[    --monitor y|n ]
	[    --nosync ]
	[    --noudevsync ]
	[    --reportformat basic|json|json_std ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
root@localhost:~# lvcreate -L 200M -n lv_data  vg_test
  Logical volume "lv_data" created.
root@localhost:~# mkfs.ext4 /dev/vg_test/lv_data
mke2fs 1.47.1 (20-May-2024)
Creating filesystem with 204800 1k blocks and 51200 inodes
Filesystem UUID: 187ab41c-00eb-4f5b-ac4a-2825d7c708d3
Superblock backups stored on blocks: 
	8193, 24577, 40961, 57345, 73729

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: done 

root@localhost:~# mount /dev/vg_test/lv_data /mnt/lv_data
mount: /mnt/lv_data: mount point does not exist.
       dmesg(1) may have more information after failed mount system call.
root@localhost:~# mount /dev/vg_test/lv_data mnt/lv_data
mount: mnt/lv_data: mount point does not exist.
       dmesg(1) may have more information after failed mount system call.
root@localhost:~# mkdir -p /mnt/lv_data
root@localhost:~# mount /dev/vg_test/lv_data mnt/lv_data
mount: mnt/lv_data: mount point does not exist.
       dmesg(1) may have more information after failed mount system call.
root@localhost:~# mkdir -p mnt/lv_data
root@localhost:~# mount /dev/vg_test/lv_data mnt/lv_data
root@localhost:~# vim /etc/fstab
root@localhost:~# vim /etc/fstab
root@localhost:~# vim /etc/fstab
root@localhost:~# ^C
root@localhost:~# 
```
