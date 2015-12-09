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


##Publishing to Heroku

1. Create a Heroku Account

   [http://heroku.com](http://heroku.com)
   
1. Create a new heroku app

1. Install the heroku toolbelt on your machine

   [https://toolbelt.heroku.com/](https://toolbelt.heroku.com/)
   
1. Go to your repository from the command line and type

   ```
   $ heroku login
   ```
   
1. Make your repo heroku aware inside your repository

   ```
   $ heroku git:remote -a [YOUR APP NAME HERE]
   ```   
     
1. Commit your changes and push to heroku

   ```
   $ git add -A
   $ git commit -m "Your commit message"
   $ git push heroku master
   ```
   
1. View your app on

   ```
   http://YOURAPPNAME.herokuapp.com
   ```
   
##Moving your data to heroku


###Prerequisites

You need **postgresql** command line tools to be able to run this commands
on MacOS you can use Homebrew
	
1. Install XCode from the AppStore
	
	[https://itunes.apple.com/en/app/xcode/id497799835?mt=12](https://itunes.apple.com/en/app/xcode/id497799835?mt=12)
		
2. Install XCode command line tools
	
	```
	$ xcode-select --install
	```
	
3. Install HomeBrew
	
	You can follow the instructions here
	[https://itunes.apple.com/en/app/xcode/id497799835?mt=12](https://itunes.apple.com/en/app/xcode/id497799835?mt=12)
	
	or run this command
		
	```
	$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	```

4. Install postgresql
	
	```
	$ brew install postgresql
	```
		
5. Link postgresql to get access to the command line tools
	   
	```
	$ brew link postgresql
	```

###Migrating your data

To move your local database to heroku you need to run the following command

```
$ heroku pg:push "postgres://postgres:postgres@localhost/myapplication" DATABASE_URL --app [YOUR APP NAME]
```

You can only do this if your remote database is empty, to resend
your database you have to empty it with

```
$ heroku pg:reset DATABASE_URL --app [YOUR APP NAME]
```
   
##Adding a Domain to your app
   
 
1. Search for the domain you want on

   ```
   https://iwantmyname.com/  
   ```

1. Buy the domain

1. From your IWantMyName.com dashboard find your name and click on 
   install a new service, find heroku from the list of
   services
   
1. Setup the heroku service by giving it your apps name


  
   






