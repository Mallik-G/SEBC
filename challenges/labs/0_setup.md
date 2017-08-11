### Cloud provider

AWS

### Instances
```
master: 52.48.249.86, ec2-52-48-249-86.eu-west-1.compute.amazonaws.com
worker1: 52.215.63.156, ec2-52-215-63-156.eu-west-1.compute.amazonaws.com
worker2: 34.251.176.180, ec2-34-251-176-180.eu-west-1.compute.amazonaws.com
worker3: 52.208.89.77, ec2-52-208-89-77.eu-west-1.compute.amazonaws.com
worker4: 34.251.191.26, ec2-34-251-191-26.eu-west-1.compute.amazonaws.com

```

### Linux release
```
cat /etc/centos-release 
CentOS Linux release 7.1.1503 (Core)
```

### filesystem capacity of first node
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      100G  825M  100G   1% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup

```

### Yum repolist command
```
sudo yum repolist enabled
```

with ansible that is
```
ansible -u centos -b -m command -a "yum repolist enabled" all
```

output:

```
34.251.191.26 | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                             repo name                             status
base/7/x86_64                       CentOS-7 - Base                       9,363
extras/7/x86_64                     CentOS-7 - Extras                       449
updates/7/x86_64                    CentOS-7 - Updates                    2,146
repolist: 11,958

52.215.63.156 | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                             repo name                             status
base/7/x86_64                       CentOS-7 - Base                       9,363
extras/7/x86_64                     CentOS-7 - Extras                       449
updates/7/x86_64                    CentOS-7 - Updates                    2,146
repolist: 11,958

34.251.176.180 | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                             repo name                             status
base/7/x86_64                       CentOS-7 - Base                       9,363
extras/7/x86_64                     CentOS-7 - Extras                       449
updates/7/x86_64                    CentOS-7 - Updates                    2,146
repolist: 11,958

52.208.89.77 | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                             repo name                             status
base/7/x86_64                       CentOS-7 - Base                       9,363
extras/7/x86_64                     CentOS-7 - Extras                       449
updates/7/x86_64                    CentOS-7 - Updates                    2,146
repolist: 11,958

52.48.249.86 | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                             repo name                             status
base/7/x86_64                       CentOS-7 - Base                       9,363
extras/7/x86_64                     CentOS-7 - Extras                       449
updates/7/x86_64                    CentOS-7 - Updates                    2,146
repolist: 11,958

```

### List passwd entries
```
sudo sh -c "cat /etc/passwd | grep -e nimbus -e igneous"
```

In ansible that is
```
ansible -u centos -b -m shell -a "cat /etc/passwd | grep -e nimbus -e igneous" all
```

output

```
52.215.63.156 | SUCCESS | rc=0 >>
nimbus:x:2800:2800::/home/nimbus:/bin/bash
igneous:x:2900:2900::/home/igneous:/bin/bash

34.251.176.180 | SUCCESS | rc=0 >>
nimbus:x:2800:2800::/home/nimbus:/bin/bash
igneous:x:2900:2900::/home/igneous:/bin/bash

52.208.89.77 | SUCCESS | rc=0 >>
nimbus:x:2800:2800::/home/nimbus:/bin/bash
igneous:x:2900:2900::/home/igneous:/bin/bash

34.251.191.26 | SUCCESS | rc=0 >>
nimbus:x:2800:2800::/home/nimbus:/bin/bash
igneous:x:2900:2900::/home/igneous:/bin/bash

52.48.249.86 | SUCCESS | rc=0 >>
nimbus:x:2800:2800::/home/nimbus:/bin/bash
igneous:x:2900:2900::/home/igneous:/bin/bash

```

### List group entries
```
sudo sh -c "cat /etc/group | grep -e rocks -e clouds"
```

in ansible that is
```
ansible -u centos -b -m shell -a "cat /etc/group | grep -e rocks -e clouds" all
```

output

```
34.251.176.180 | SUCCESS | rc=0 >>
rocks:x:1001:igneous
clouds:x:1002:nimbus

52.208.89.77 | SUCCESS | rc=0 >>
rocks:x:1001:igneous
clouds:x:1002:nimbus

34.251.191.26 | SUCCESS | rc=0 >>
rocks:x:1001:igneous
clouds:x:1002:nimbus

52.48.249.86 | SUCCESS | rc=0 >>
rocks:x:1001:igneous
clouds:x:1002:nimbus

52.215.63.156 | SUCCESS | rc=0 >>
rocks:x:1001:igneous
clouds:x:1002:nimbus

```
