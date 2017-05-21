# EBS + XFS File System - Attach a new EBS volume to your Linux Instance (centos)

### #1 - yum install xfsprogs

### #2 - mkfs.xfs /dev/sdf
-bash-3.2# mkfs.xfs /dev/sdf
meta-data=/dev/sdf isize=256 agcount=16, agsize=327680 blks
= sectsz=512 attr=0
data = bsize=4096 blocks=5242880, imaxpct=25
= sunit=0 swidth=0 blks, unwritten=1
naming =version 2 bsize=4096
log =internal log bsize=4096 blocks=2560, version=1
= sectsz=512 sunit=0 blks, lazy-count=0
realtime =none extsz=4096 blocks=0, rtextents=0

### #3 - 
-bash-3.2# echo "/dev/sdf /vol xfs noatime 0 0" | tee -a /etc/fstab
/dev/sdf /vol xfs noatime 0 0

### #4
mkdir -m 000 /vol

### #5
mount /vol


