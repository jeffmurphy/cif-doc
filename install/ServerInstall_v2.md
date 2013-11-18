# Preamble
---
If you have not joined the [CIF Community](https://groups.google.com/forum/?fromgroups#!forum/ci-framework) yet, please do. It's a great place to ask questions..

[v2 ChangeLog](https://github.com/collectiveintel/cif-v2/blob/master/ChangeLog)

A list of known v2 [issues](https://github.com/collectiveintel/cif-v2/issues)

The v2 FAQ can be found [here](https://code.google.com/p/collective-intelligence-framework/wiki/FAQ_v2)

Issues being discussed on the mailing list can be found [here](https://groups.google.com/forum/?hl=en&fromgroups=#!tags/ci-framework/v2)

### v0/v1 Compatibility

The clients stay essentially the same in terms of usage, however you must use the v2 client to connect to the v2 server.

### Upgrading

TBD

### System Requirements

These requirements will handle everything on the same box pretty well with the default open source data-sets. The more (bigger) data-sets you add, the more ram / disk space you'll need. The more cores you add, the more threads that can "batch out" the feed parsers (thus, resulting in faster data consumption).

These specs will handle around 10k feeds at once with minimal impact on memory usage. Past that you'll need to start doubling your specs. Virtual machine technology is great for prototyping your implementation and will give you a good baseline of what you'll need for production.

Keep in mind that not all virtual machine software are created equal. Some more production grade (vmware, etc) might work better than others (vbox, kvm, etc). If you experience exceptional degraded performance with the resources cited below, please provide that [feedback](https://groups.google.com/forum/?fromgroups=#!tags/ci-framework/performance) (with specs, tests run, etc).

Some initial benchmarking [stats](https://docs.google.com/spreadsheet/ccc?key=0An_zAK-1p1hzdDJJYUotOTZBNzBpUkV1amJFU3pmSXc&usp=sharing) to test a setup against.

#### Small Install
---
* x86-64bit unix platform
* at-least 4GB ram
* at-least 2 cores
* at-leats 100GB of free (after OS install) disk space
*

#### Large Install
---
* an x86-64bit platform
* at-least 16GB ram
* at-least 16 cores
* at-least 500GB of free (after OS install) disk space

# Setup
### Choose an operating system
---
CentOS6/RedHat6/Amazon Linux AMI 2013 is the operating system in which CIF v2 is developed against.

In theory any current Unix/Linux operating system should be able to run CIF. The challenge may be installing the required applications and dependencies.

* [RH6/CentOS6/Amazon AMI](ServerInstall_v2_RH6_Small.md)

### Disk Layout
---
CIF v2 is based on Hadoop/HBase. There is no specific disk layout. Ideally, place your HDFS directory on its own disk. 

### Required Applications and Dependencies
---
Choose the distribution you used as your base operating system and install the required applications and dependencies.

