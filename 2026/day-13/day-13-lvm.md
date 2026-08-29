# Day 13 – Linux Volume Management (LVM)

Today I learned about **LVM (Logical Volume Management)** in Linux.

LVM helps to manage disk storage easily. We can create, extend and mount logical volumes without depending only on fixed partitions.

## LVM Structure


Disk → PV → VG → LV → Filesystem → Mount Point

### Main Components

* **PV (Physical Volume)** – Disk used by LVM.
* **VG (Volume Group)** – Pool made from one or more PVs.
* **LV (Logical Volume)** – Storage created from VG.
* **Filesystem** – Used to store files.
* **Mount Point** – Directory where the volume is accessed.

---

## Task 1 – Check Storage


lsblk
pvs
vgs
lvs
df -h


These commands show disks, Physical Volumes, Volume Groups, Logical Volumes and available disk space.


## Task 2 – Create Physical Volume

For practice I used a loop device.

pvcreate /dev/loop0
pvs


## Task 3 – Create Volume Gro

vgcreate devops-vg /dev/loop0
vgs

Here devops-vg is my Volume Group name.


## Task 4 – Create Logical Volume

Created a 500 MB Logical Volume:


lvcreate -L 500M -n app-data devops-vg
lvs


## Task 5 – Format and Mount

Format the volume with ext4:


mkfs.ext4 /dev/devops-vg/app-data


Create mount directory:



mkdir -p /mnt/app-data


Mount it:


mount /dev/devops-vg/app-data /mnt/app-data


Check:


df -h /mnt/app-data


Test:


echo "LVM Practice - Day 13" > /mnt/app-data/test.txt
cat /mnt/app-data/test.txt




## Task 6 – Extend Volume

Initially the LV was 500 MB. I increased it by 200 MB.


lvextend -L +200M /dev/devops-vg/app-data


Resize the ext4 filesystem:


resize2fs /dev/devops-vg/app-data


Check the new size:


df -h /mnt/app-data



## Useful Commands

| Command     | Use                    |
| ----------- | ---------------------- |
| pvs       | Check Physical Volumes |
| vgs       | Check Volume Groups    |
| lvs       | Check Logical Volumes  |
| pvcreate  | Create PV              |
| vgcreate  | Create VG              |
| lvcreate  | Create LV              |
| lvextend  | Increase LV size       |
| resize2fs | Resize ext4 filesystem |
| df -h     | Check disk space       |
| lsblk     | Check block devices    |


## What I Learned

1. LVM makes Linux storage management more flexible.
2. I learned how to create PV, VG and LV.
3. I learned how to extend a Logical Volume and resize its filesystem.



## Git Commands

git add 2026/day-13/

git commit -m "Add Day 13 LVM practice"

git push origin master




PV → VG → LV → ext4 → /mnt/app-data


## #90DaysOfDevOps 

# #DevOpsKaJosh 

# #TrainWithShubham
