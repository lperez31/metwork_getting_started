[< Previous step: Welcome to the Metwork Framework](./index.md)

## Installation

For this tutorial, we are going to start with a fresh CentOS 7 VM. If it's not a fresh CentOS, it should also work of course.

First, register the MetWork Framework stable repository. Login as root, copy the following command and paste it in a terminal.

``` bash
cat >/etc/yum.repos.d/metwork.repo <<EOF
[metwork_stable]
name=MetWork Stable
baseurl=http://metwork-framework.org/pub/metwork/releases/rpms/stable/centos7/
gpgcheck=0
enabled=1
metadata_expire=0
EOF
```

MetWork Framework is organized in modules. We are going to install the webservice module: mfserv.

``` bash
yum -y install metwork-mfserv
```

That's all we need for now!

[Next step: Create your first API >](./2_first_api.md)