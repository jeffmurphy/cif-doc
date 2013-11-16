# Introduction
This doc is for installing CIF v2 (small) on one of the following (minimum version given):

* CentOS 6.4
* RedHat 6.4
* Amazon Linux AMI 2013.09

**SELINUX**

1. Disable SELINUX by setting `SELINUX=disabled` in `/etc/sysconfig/selinux`
2. Reboot


## Hadoop/HDFS/Hbase


[Install HBase/HDFS from Cloudera](Hadoop-HBase-RH6-Small). For ultra-small, you can locate this on the same server as CIF. For small, locate it on a single separate server. 

## CIF


[DEBUG][2013-11-16T04:06:26Z]: done...
./bin/cif_smrt -C /home/jcmurphy/.cif -r ./rules/etc/misc.cfg -f sshbl.org -d -T medium -P at bin/cif_crontool line 205.
Argument "-T" isn't numeric in numeric gt (>) at /home/jcmurphy/src/cif-smrt/bin/../../libcif/lib/CIF.pm line 99.



