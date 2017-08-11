### The full teragen command and output

```
sudo -u nimbus time yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Ddfs.block.size=67108864 -Dmapreduce.job.maps=16 -Dmapred.map.tasks.speculative.execution=false -Dmapreduce.map.memory.mb=805 65536000 tgen
```

### The result of the time command

```
7.15user 0.39system 1:34.74elapsed 7%CPU (0avgtext+0avgdata 197288maxresident)k
0inputs+1944outputs (0major+77619minor)pagefaults 0swaps

```

### The command and output of hdfs dfs -ls /user/nimbus/tgen

```
Found 17 items
-rw-r--r--   3 nimbus nimbus          0 2017-08-11 09:48 /user/nimbus/tgen/_SUCCESS
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00000
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00001
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00002
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:47 /user/nimbus/tgen/part-m-00003
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00004
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:47 /user/nimbus/tgen/part-m-00005
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00006
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00007
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00008
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00009
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00010
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00011
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00012
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00013
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00014
-rw-r--r--   3 nimbus nimbus  409600000 2017-08-11 09:48 /user/nimbus/tgen/part-m-00015```

### The command and output of hadoop fsck -blocks /user/nimbus

```
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-9-214.eu-west-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.9.214 for path /user/nimbus at Fri Aug 11 09:54:22 UTC 2017
.................Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	3
 Total files:	17
 Total symlinks:		0
 Total blocks (validated):	112 (avg. block size 58514285 B)
 Minimally replicated blocks:	112 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Aug 11 09:54:22 UTC 2017 in 5 milliseconds


The filesystem under path '/user/nimbus' is HEALTHY
```
