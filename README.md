
## lsdisk

Formats the output of `lsblk` and `df` together, for a more
information-dense human display of the disks of a system.

* Example: disks with usb key:

``` shell
$> lsdisk
Name         Mount     Info                       Size     Used% Used Avail Serial and  UUID
/dev/sda               sata ATA Samsung SSD 850   500G                      K2KSDN5KASDKJDG
├─ /dev/sda1 /boot/efi ├─ bootefi vfat            ├─ 268M  13%   33M  233M   451F-9C7C
└─ /dev/sda2 /         └─ linuxroot ext4          └─ 500G  90%   420G 47G    6f59f043-e360-46fd-ab1b-7752b1f33ac6
/dev/sdb               sata ATA SanDisk SDSSDHP2  256G                      923987547292
├─ /dev/sdb1           ├─ EFI System vfat         ├─ 537M                    40A6-82CD
├─ /dev/sdb2           ├─ Linux swap swap         ├─ 2.15G                   98bb9e1c-96e9-451f-9c7c-36e6c1f2b170
└─ /dev/sdb3           └─ Linux filesystem ext4   └─ 253G                    98bb9e1c-96e9-451f-9c7c-36e6c1f2b170
/dev/sdc               usb Kingston DT Rubber 3.0 15.7G                     29123SKASM1239123LASIMD2
└─ /dev/sdc1           └─ vfat                    └─ 15.7G                   2564-4F6A
```

* Example: disks with lvm:

``` shell
$> lsdisk
Name                                 Mount         Info                        Size        Used% Used Avail Serial UUID
/dev/sda                                           sata ATA WDC WD299848KF-0   500G                         WD-OSENED938472
├─ /dev/sda1                         /boot         ├─ ext4 hostnam_boot        ├─ 524M     29%   134M 336M   af4ad6e1-5fe8-4ee1-93c9-ccf1af5eeebc
└─ /dev/sda2                                       └─ LVM2_member              └─ 500G                       e2d8a68a-49e0-4eb8-8fb3-d5201430cb14
   ├─ /dev/mapper/vg_hostnam-lv_swap [SWAP]           ├─ swap                     ├─ 4.19G                   2379c9a8-0a92-497c-95ce-809effb6a5c6
   ├─ /dev/mapper/vg_hostnam-lv_root /                ├─ ext4 vg_hostnam-lv_ro    ├─ 53.7G 18%   9.0G 42G    cd67599f-fa4d-4e01-8f83-aa1603d1203b
   └─ /dev/mapper/vg_hostnam-lv_home /home            └─ ext4 vg_hostnam-lv_ho    └─ 442G  6%    23G  391G   c2339c64-90f1-48f2-85a0-8782c7928833
/dev/sdb                                           sata ATA WDC WD19023ASD-0   500G                         WD-SXJDHW407873
└─ /dev/sdb1                         /media/d1     └─ d1 ext4                  └─ 500G     83%   386G 81G    589960b7-e23b-446c-9286-68f36a038fa4
/dev/sdc                                           sata ATA SAMSUNG HD293IL    1T                           SOSDIOWJD29482
└─ /dev/sdc1                         /media/d2     └─ ext4                     └─ 1T       74%   689G 246G   adcf3229-8058-4e1f-83ab-80088dd4d542
```
