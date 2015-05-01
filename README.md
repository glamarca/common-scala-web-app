# Scala-Play-Slick-Bootstrap application template

This package is a common [Scala](http://www.scala-lang.org/) application template using [Play Framework](https://www.playframework.com/) and [Slick](http://slick.typesafe.com/).

## [Play Framework](https://www.playframework.com/) Documentation
Once the application is deployed, you can always access [Play Framework](https://www.playframework.com/) Documentation at [http://localhost:9000/@documentation](http://localhost:9000/@documentation) .

Online documentation : https://www.playframework.com/documentation

## Installing

### Download and Install [Activator](https://www.typesafe.com/community/core-tools/activator-and-sbt)

[Activator](https://www.typesafe.com/community/core-tools/activator-and-sbt) is a tool created by [Typesafe](https://www.typesafe.com) to create and develop [Scala](http://www.scala-lang.org/) applications. You can download [Activator](https://www.typesafe.com/community/core-tools/activator-and-sbt) from the following address: https://www.typesafe.com/community/core-tools/activator-and-sbt.

[Activator](https://www.typesafe.com/community/core-tools/activator-and-sbt) use [SBT](http://www.scala-sbt.org/) as build tool and dependencies manager. All [SBT](http://www.scala-sbt.org/) dependencies configuration links can be found on the [MVN Repository](http://mvnrepository.com/) , in the [SBT](http://www.scala-sbt.org/)tab

To install activator, simply unzip the downloaded file and add the absolute path to the new directory in the environment variable `$PATH`. You will be able to run the command `activator` from anywhere in your file system.

### Clone the repository

Clone the repository locally using [Git](http://git-scm.com/downloads):

```
    $ mkdir projects
    $ cd projects
    $ git clone https://github.com/glamarca/$PROJECT_NAME
```

It will create the directory `$PROJECT_NAME` where all cloned files will be located.

### External Database Configuration

By default, the template use a [H2](http://www.h2database.com) embedded database, usefull for dev or demo.
The default db is located in the "h2" folder of the project.

If you want to use another database , you have to edit the **application.conf** file to provide the correct connexion informations.
You also have to change the dependencies in the **build.sbt** file.

#### [MySql](http://www.mysql.com) example

* Create DB :
```
   $ mysql -u root -p
   $ mysql> CREATE DATABASE $DB_NAME;
```
* Create User :
```
$ mysql> CREATE USER '$USER_NAME'@'localhost' IDENTIFIED BY '$USER_PASSWORD';
```
* Grant Privileges :
```
  $ mysql> GRANT ALL PRIVILEGES ON DB_NAME.* TO '$USER_NAME'@'localhost';
  $ mysql> FLUSH PRIVILEGES;
```
* Edit **application.conf** file :
```
  db.default.driver=com.mysql.jdbc.Driver
  db.default.url="jdbc:mysql://localhost/$DB_NAME"
  db.default.user="$USER_NAME"
  db.default.password="$USER_PASSWORD"
```
* Edit **application.conf** file :  
  Replace `"com.h2database" % "h2" % "1.4.187"` by `mysql" % "mysql-connector-java" % "5.1.30`

### Configure the Application Name

* Edit **application.conf** file :

  Replace `name := """Scala-Play-Slick-Bootstrap"""` by `name := """$PROJECT_NAME_PATH"""`

### Run the Application

  To run the application:
```
  $ cd $PROJECT_NAME_PATH
  $ activator

  [$PROJECT_NAME_PATH] $ run
```

Once the server is started, you can open the application in your browser accessing the address: [http://localhost:9000/](http://localhost:9000/)  
