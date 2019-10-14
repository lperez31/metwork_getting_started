[< Create a database](./5_database.md)

## Tasks triggered by files

### What is mfdata?

We are going to showcase some possibilities of the mfdata MetWork module. But what is mfdata?

__Example of use case:__ Imagine that you have files that are provided to your app by ftp. For instance, images sent by another app. Imagine that you want to trigger a task each time an image arrives. This task would convert the image to jpeg and move it to another directory.

__Other example of use case:__ Another app exports data every night in csv format and put it in a directory. When this csv file arrives, you want to trigger a task to insert it in a database.

With mfdata, you can manage these kind of worklows. All you have to do is configuring the events that will trigger your app (most of the time it will be when a file arrives), and mfdata will launch your app when the events occur.

### Installation of mfdata

Login as root user, and install mfdata:

``` bash
# As root user
yum -y install metwork-mfdata
```

Start the services:

``` bash
service metwork start
```

### Create your plugin

Let's create a mfdata plugin and launch it.

``` bash
# Login as mfdata user
su - mfdata
# Create your plugin with default template
bootstrap_plugin.py create tutodata
# Launch your plugin in dev mode
cd tutodata
make develop
```

TODO

[Next step: TODO >](./7_todo.md)