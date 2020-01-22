This repository contains a fork of [Cloudera's RPM .spec](https://github.com/cloudera/cdh-package/tree/cdh5-0.6.0_5.16.2/bigtop-packages/src/rpm/kudu) files to build binary packages for the latest version of Apache Kudu.

They were tested on CentOS 7.

- Install RPM building tools: ```yum install rpmdevtools```
- Setup your RPM building environment: ```rpmdev-setuptree```
- Download sources: ```spectool -g -R kudu.spec```
- Copy additional scripts to your SOURCES directory: ```cp SOURCES/* ~/build/SOURCES/```
- Build packages: ```rpmbuild -ba SPECS/kudu.spec```

You may potentially need to install other dependencies as described in [Kudu documentation](https://kudu.apache.org/docs/installation.html#rhel_from_source).

The build process takes quite a while (40 minutes on a 40-core server) and requires internet access as it will download and compile various dependencies.
