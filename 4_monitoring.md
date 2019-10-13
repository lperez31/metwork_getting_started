[< Previous step: Put some code in your API](./3_second_api.md)

## Monitor your application

The MetWork Framework monitoring module is called mfadmin. It also contains the mfsysmon submodule which provides a system monitoring out of the box.

Let's install it. Login as root user, and install mfadmin and mfsysmon:

``` bash
# As root user
yum -y install metwork-mfadmin metwork-mfsysmon
```

Start the services:

``` bash
service metwork start
```

### System monitoring

Open `http://localhost:15602`in your browser, you will see the monitoring website, built upon Grafana open source project. Login with the following credentials:
* user: admin
* password: admin

For your first login, it will ask you to change your password. Just clic on 'skip' for now.

This monitoring website will give you access to several dashboards. You can already clic on 'System Dashboard', which will give you something like this:

![alt text](./images/mfsysmon.png "mfadmin System Dashboard")

### Application monitoring

TODO

