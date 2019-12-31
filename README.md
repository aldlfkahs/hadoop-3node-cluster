# hadoop2.7.6-3node-cluster
UNIST 20141440 Seung Won Lee

### Environment
This system is set for three virtual machines. One for master node, and remaining two for slave nodes.
Uploaded files are only configuration parts of whole files, and it is default state.
On master node, three items are executed; namenode/resource manager/secondary namenode/.
On slave node, two items are executed; data node/node manager.

### hadoop configuration tuning
The goal of tuning is getting the highest performance of on each own's environment.
There are three major factors for performance.

##### 1.Replication
This factor determines the number of copy of hdfs files. If the replication is large, it will have more probability to utilize locality. However, the number of write operation will also increase, which causes overheads.
This property is in hdfs-site.xml. (dfs.replication)

##### 2.Blcok size
This factor determines the block size of hdfs file system. If it is large, it can reduces initialization and I/O overheads because the number of blocks are reduced.
This property is in hdfs-site.xml. (dfs.blocksize)

##### 3.CPU and Memory Configuration
This factor determines the memory or CPU allocation of nodemanager, app-master, mapper and reducer.
If physical memory or CPU is allowed, the more resources is allocated, the better performance is naturally.


### Conclusion
There are more factors such as buffer size but above three are usually major factors.
There is no absolute answer. The optimized configuration is case by case.
To see the detailed explanation, please click [here](https://aldlfkahs.github.io/Portfolio/hadoop%20report.pdf).
