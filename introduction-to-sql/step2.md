Now that you know what a database, table, and column are, the next thing that you would need to do is install a database service where you would be running your SQL queries on.

We would be using MySQL as it is free, open-source, and very widely used.

## Installing MySQL

As we are going to use **Ubuntu**, in order to install MySQL run the following commands:

* First update your `apt` repository:

```
sudo apt update -y
```{{execute}}

* Then install MySQL:

```
sudo apt install mysql-server mysql-client
```

We are installing 2 packages, one is the actual MySQL server, and the other is the MySQL client, which would allow us to connect to the MySQL server and run our queries.

In order to check if MySQL is running, run the following command:

```
sudo systemctl status mysql.service
```{{execute}}
In order to secure your MySQL server, you could run the following command:

```
sudo mysql_secure_installation
```{{execute}}

Then follow the prompt and finally choose a secure password and save it in a secure place like a password manager.

With that, you would have MySQL installed on your Ubuntu server. The above should also work just fine on Debian.

## Accessing MySQL via CLI

To access MySQL run the `mysql` command followed by your user:

```
mysql -u root -p
```{{execute}}

## Creating a database

After that, switch to the `demo` database that we created in the previous chapter:

```
USE demo;
```{{execute}}

To exit the just type the following:

```
exit;
```{{execute}}

## Configuring `.my.cnf`

By configuring the `~/.my.cnf` file in your user's home directory, MySQL would allow you to login without prompting you for a password.

In order to make that change, what you need to do is first create a `.my.cnf` file in your user's home directory:

```
touch ~/.my.cnf
```{{execute}}

After that, set secure permissions so that other regular users could not read the file:

```
chmod 600 ~/.my.cnf
```{{execute}}

Then using your favorite text editor, open the file:

```
nano ~/.my.cnf
```{{execute}}

And add the following configuration:

```
[client]
user=YOUR_MYSQL_USERNAME
password=YOUR_MYSQL_PASSWORD
```{{copy}}

Make sure to update your MySQL credentials accordingly, then save the file and exit.

After that, if you run just `mysql`, you will be authenticated directly with the credentials that you've specified in the `~/.my.cnf` file without being prompted for a password.

## The mysqladmin command

As a quick test, you could check all of your open SQL connections by running the following command:

```
mysqladmin proc
```{{execute}}

The `mysqladmin` tool would also use the client details from the `~/.my.cnf` file, and it would list your current MySQL process list.

Another cool thing that you could try doing is combining this with the `watch` command and kind of monitor your MySQL connections in almost real-time:

```
watch -n1 mysqladmin proc
```{{execute}}

To stop the `watch` command, just hit `CTRL+C`

## GUI clients

If you prefer using GUI clients, you could take a look a the following ones and install them locally on your laptop:

* [MySQL Workbench](https://www.mysql.com/products/workbench/)
* [Sequel Pro](https://www.sequelpro.com/)
* [TablePlus](https://tableplus.com/)

This will allow you to connect to your database via a graphical interface rather than the `mysql` command-line tool.