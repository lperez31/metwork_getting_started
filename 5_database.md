[< Monitor your application](./4_monitoring.md)

## Create a database

### Installation of mfbase

You may need a database for your applications. If you don't have a friend who is expert in database administration, you have two choices:

1. Use sqlite. But has many limitations.
2. Spend hours understanding how to install and configure a database.

With MetWork Framework, you now have a third option: use the mfbase module.

Let's install it. Login as root user, and install mfbase:

``` bash
# As root user
yum -y install metwork-mfbase
```

Start the services:

``` bash
service metwork start
```

### Create and run the database

The mfbase module supports different types of databases, such as postresql and webdav.

Let's create a postgresql database.

As for other MetWork Framework modules, in mfbase you begin by creating a plugin:

``` bash
# As mfbase user
su - mfbase
bootstap_plugin.py create foo
```

Press enter several times to accept default values.

Edit `~/foo/sql/foo.sql` and put:
``` sql
-- SQL queries to run during plugin installation
CREATE TABLE records(
    name VARCHAR (355)
)
```

The SQL queries in this file will be executed at the creation of the database. It is not mandatory to use this file, you can also create your tables later.

Then release the plugin:

``` bash
# As mfbase user
cd foo
make release
```

The `make release` command should output something like 'plugin is ready at /home/mfbase/foo/foo-0.0.1-1.metwork.mfbase.plugin'. Copy the filename (without the path) and use the following command to run your mfbase plugin:

``` bash
plugins.install [YOUR_PLUGIN_FILENAME_HERE]
# For instance plugins.install foo-0.0.1-1.metwork.mfbase.plugin
```

That's all. Your database should be running.

### Check your database

Connect to your database:

``` bash
psql -U plugin_foo -h localhost -p 7432 plugin_foo
```

When prompted, use the password `plugin_foo`.

In the psql prompt, check that your table 'records' has been created:

``` shell
plugin_foo=> \d records
```

You should see an output confirming that your table exists.

Note that if you use the command `\d` to list all tables, you will see several other tables. These tables have been created by the postgis extension. With postgis, you can easily store geographic objects in your database, if you need to do so.

### Put data in our database

Let's add some code in the API we have built previously, to populate the database.

Login as mfserv:

``` bash
su - mfserv
```

Edit the code of our tutorial api, in the file `~/tutorial/tutorial/server.js`

TODO

### Monitor your database

TODO

[Next step: TODO >](./6_todo.md)