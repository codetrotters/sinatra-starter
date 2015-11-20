#Codetrotters Sinatra Starter

This is a starter project for sinatra. It instructions on how to set a virtual machine with all the basic
dependencies you will need.

##Includes
1. Vagrant VirtualMachine
	1. Ruby 2.3
	1. Postgresql 9.3 Database
	1. TeamPostgreSql Client (http://www.teampostgresql.com/)
1. Sample Starter Code

##Dependencies

In order to run the virtual machine you will
need **virtualbox** and **vagrant** you can
get those at

[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
[https://www.vagrantup.com/downloads.html](https://www.vagrantup.com/downloads.html)

##Starting Virtual Machine
To start the virtual machine you have to run
the following command from the root directory of
this repository

```bash
$ vagrant up
```

The virtual machine may ask where to get its internet from ( **Available bridged network interfaces** )
when this happens choose one of your available internet
interfaces that is connected to the internet


Once that has finished, you can connect to your new
virtual machine with

```bash
$ vagrant ssh
```

To return to your machine, just type `exit` from inside the virtual machine.

To stop the machine you can run

```bash
$ vagrant halt
```

##Running the Sinatra Application

From inside the virtual machine, on the
src/ run

```bash
$ cd ~/src/
$ bundle exec shotgun -o 0.0.0.0
```

Alternatively you can use the provided script

```bash
$ ~/src/bin/start.sh
```

You should be able to access the application at

[http://localhost:9393](http://localhost:9393)

##Connecting to PostgreSQL

The virtual machine comes with postgresql preinstalled,
with an empty database called **myapplication**

You can use your favorite PostgreSQL client with following connection details

| Property |  Value          |
|----------|-----------------|
| Host     |  localhost:5432 |
| Username |     postgres    |
| Password |     postgres    |
| Database |  myapplication  |

##Connecting to PostgreSQL with TeamPostgreSql 

You can also use the built in postgresql client
TeamPostgreSql by going to the following url on your
computer

[http://localhost:8082/teampostgresql](http://localhost:8082/teampostgresql)






