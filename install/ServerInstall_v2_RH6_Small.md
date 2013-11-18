# Introduction
This doc is for installing CIF v2 (small) on one of the following (minimum version given):

* CentOS 6.4
* RedHat 6.4
* Amazon Linux AMI 2013.09

**SELINUX**

1. Disable SELINUX by setting `SELINUX=disabled` in `/etc/sysconfig/selinux`
2. Reboot


## Hadoop/HDFS/Hbase


[Install HBase/HDFS from Cloudera](Hadoop-HBase-RH6-Small.md). For ultra-small, you can locate this on the same server as CIF. For small, locate it on a single separate server. 

## CIF





