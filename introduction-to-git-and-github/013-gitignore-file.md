# Gitignore

In some cases, you might not want to commit some of your files to Git due to security reasons.

For example, if you have a config file where you have all of your database credentials and other sensitive secrets, you should never add it to Git and push it to GitHub as other people will be able to get hold of that sensitive information.

To do so, you need to have a `gitignore` file which includes a list of all of the files and directories that should be excluded from your Git repository. In this chapter, you will learn how to do that!

### Ignoring a specific file

Let's have a look at the following example if you had a `PHP` project and a file called `config.php`, which stores your database connection string details like username, password, host, etc.

In order to exclude that file from your git project, you could create a file called `.gitignore` inside your project's directory:

```
touch .gitignore
```{{execute}}

Then inside that file, all that you need to add is the name of the file that you want to ignore, so the content of the `.gitignore` file would look like this:

```
config.php
```

That way, the next time you run `git add .` and then run `git commit` and `git push`, the `config.php` file will be ignored and will not be added nor pushed to your Github repository.

That way, you would keep your database credentials safe!

### Ignoring a whole directory

In some cases, you might want to ignore a whole folder. For example, if you have a huge `node_modules` folder, there is no need to add it and commit it to your Git project, as that directory is generated automatically whenever you run `npm install`.

The same would go for the `vendor` folder in Laravel. You should not really add the `vendor` folder to your Git project, as all of the content of that folder is generated automatically whenever you run `composer install`.

So in order to ignore the `vendors` and `node_modules` folders, you could just add them to your `.gitignore` file:

```
# Ignored folders
/vendor/
node_modules/
```

### Getting a gitignore file for Laravel

In order to get a `gitignore` file for Laravel, you could get the file from [the official Laravel Github repository] here(https://github.com/laravel/laravel/).

The file would look something like this:

```
/node_modules
/public/hot
/public/storage
/storage/*.key
/vendor
.env
.env.backup
.phpunit.result.cache
Homestead.json
Homestead.yaml
npm-debug.log
yarn-error.log
```

It essentially includes all of the files and folders that are not needed to get the application up and running.

### Using gitignore.io

As the number of frameworks and application grows day by day, it might be hard to keep your `.gitignore` files up to date or it could be intimidating if you had to search for the correct `.gitignore` file for every specific framework that you use.

I recently discovered an open-source project called [gitignore.io](http://gitignore.io). It is a site and a CLI tool with a huge list of predefined `gitignore` files for different frameworks. 

All that you need to do is visit the site and search for the specific framework that you are using.

For example, let's search for a `.gitignore` file for Node.js:

![Nodejs gitignore file](https://imgur.com/bjT2aHP)

Then just hit the **Create button** and you would instantly get a well documented `.gitignore` file for your Node.js project, which will look like this:

```
# Created by https://www.toptal.com/developers/gitignore/api/node
# Edit at https://www.toptal.com/developers/gitignore?templates=node

### Node ###
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
lerna-debug.log*
...
```

### Using gitignore.io CLI

If you are a fan of the command-line, the gitignore.io project offers a CLI version as well.

To get it installed on Linux, just run the following command:

```
git config --global alias.ignore \
'!g{{execute}}i() { curl -sL https://www.toptal.com/developers/gitignore/api/$@ ;}; gi'
```{{execute}}

If you are using a different OS, I would recommend checking out the documentation [here](https://docs.gitignore.io/install/command-line) on how to get it installed for your specific Shell or OS.

Once you have the `gi` command installed, you could list all of the available `.gitignore` files from gitignore.io by running the following command:

```
gi list
```{{execute}}

For example, if you quickly needed a `.gitignore` file for Laravel, you could just run:

```
gi laravel
```{{execute}}

And you would get a response back with a well-documented Laravel `.gitignore` file:

```
# Created by https://www.toptal.com/developers/gitignore/api/laravel
# Edit at https://www.toptal.com/developers/gitignore?templates=laravel

### Laravel ###
/vendor/
node_modules/
npm-debug.log
yarn-error.log

# Laravel 4 specific
bootstrap/compiled.php
app/storage/

# Laravel 5 & Lumen specific
public/storage
public/hot

# Laravel 5 & Lumen specific with changed public path
public_html/storage
public_html/hot

storage/*.key
.env
Homestead.yaml
Homestead.json
/.vagrant
.phpunit.result.cache

# Laravel IDE helper
*.meta.*
_ide_*

# End of https://www.toptal.com/developers/gitignore/api/laravel
```

### Conclusion

Having a `gitignore` file is essential, it is great that you could use a tool like the [gitignore.io](gitignore.io) to generate your `gitignore` file automatically, depending on your project!

If you like the gitignore.io project, make sure to check out and contribute to the project [here](https://github.com/toptal/gitignore.io).
