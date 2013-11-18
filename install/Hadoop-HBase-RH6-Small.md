# Hadoop/HBase

# Preamble

The CIFv2 uses the Cloudera distribution of Hadoop/HBase. For very-small (single server) installations this can be done on the CIF server itself. For small (two server) installations, this can be done on a separate machine, allowing the CIF server to connect to the HBase port. 

These instructions are for Hadoop/HBase sans authentication (just uses IPTables to control access to the HBase instance).

## Cloudera

Cloudera has [great documentation](http://www.cloudera.com/content/cloudera-content/cloudera-docs/CDH4/latest/CDH4-Quick-Start/CDH4-Quick-Start.html) for installing and configuring Hadoop/HBase/etc. This doc is just for the lazy.

## Installation (64-bit Single Server/Small)

As root:

1. (JDK6/JDK7 works) yum install java
3. rpm --import http://archive.cloudera.com/cdh4/redhat/6/x86_64/cdh/RPM-GPG-KEY-cloudera
4. curl -o /etc/yum.repos.d/cloudera-chd4.repo http://archive.cloudera.com/cdh4/redhat/6/x86_64/cdh/cloudera-cdh4.repo
5. yum install hbase-master hbase-regionserver hbase-thrift hadoop-hdfs hadoop-hdfs-namenode hadoop-hdfs-datanode
6. /etc/hadoop/conf/hdfs-site.xml  contains the filesystem location for HDFS, in /var by default. Change it if you want the database located elsewhere
7. su - hdfs -c 'hdfs namenode -format'
10. service hadoop-hdfs-namenode start
11. service hadoop-hdfs-datanode start
12. su - hdfs -c 'hdfs dfs -mkdir  /wes'
13. hdfs dfs -ls /   # should show /wes, else stop something is messed
14. su - hdfs -c 'hdfs dfs -rmdir /wes'
15. download our /etc/hbase/conf/hbase-site.xml
16. su -  hdfs  -c 'hdfs dfs -mkdir /hbase'
17. su -  hdfs  -c 'hdfs dfs -chown hbase /hbase'
18. service hbase-master start
19. service hbase-thift start
20. hbase shell
21. hbase> list  # should not throw any java exceptions, else something is messed
22. hbase> create 'table', 'cf'
23. hbase> put 'table', 'myrow', 'cf:boo', 'foo'
24. hbase> scan 'table' # should return 1 row
25. hbase> disable 'table'
26. hbase> drop 'table'
27. if nec'y open iptables inbound, tcp, port 2181 so cif-db can connect
28. scp cif-db/src/hbase-tables.txt to your HBase server
29. hbase shell < hbase-tables.txt   # ignore any errors about tables not existing

Note the IP address of your HBase server.
