# Git Cheat Sheet

Here is a list of the Git commands mentioned throughout the eBook

* Git Configuration

Before you initialize a new git repository or start making commits, you should set up your git identity. 

In order to change the name that is associated with your commits, you can use the `git config` command:

```
git config --global user.name "Your Name"
```{{execute}}

The same would go for changing your email address associated with your commits as well:

```
git config --global user.email "yourmail@example.com"
```{{execute}}

That way, once you have the above configured when you make a commit and then check the git log, you will be able to see that the commit is associated with the details that you've configured above.

```
git log
```{{execute}}

In my case the output looks like this:

```
commit 45f96b8c2ef143011f11b5f6cc7a3ae20db5349d (HEAD -> main, origin/master, origin/HEAD)
Author: Bobby Iliev <bobby@bobbyiliev.com>
Date:   Fri Jun 19 17:03:53 2020 +0300

    Nginx server name for www version (#26)

```

### Initializing a project

To initialize a new local git project, open your git or bash terminal, `cd` to the directory that you would like your project to be stored at, and then run:

```
git init .
```{{execute}}

If you already have an existing project in GitHub, for example, you can clone it by using the git clone command:

```
git clone your_project_url
```{{execute}}

### Current status

In order to check the current status of your local git repository, you need to use the following command:

```
git status
```{{execute}}

This is probably one of the most used commands as you would need to check the status of your local repository quite often in order to be able to tell what files have been changed, staged, or deleted.

### Add a file to the staging area

Let's say that you have a static HTML project, and you have already initialized your git repository.

After that, at a later stage, you decide to add a new HTML file called `about-me.html`, then you've added some HTML code in there already. In order to add your new file so that it is also tracked in git, you first need to use the `git add` command:

```
git add file_name
```{{execute}}

This will stage your new file, which essentially means that the next time you make a commit, the change will be part of the commit.

To check that, you can again run the `git status` command:

```
git status
```{{execute}}

You will see the following output:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   about-me.html
```

### Removing files

In order to remove a file from your git project, use the following command:

```
git rm some_file.txt
```{{execute}}

Then after that, if you run `git status` again, you will see that the `some_file.txt` file has been deleted:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        deleted:    some_file.txt
``` 

### Discard changes for a file

In case that you've made a mistake and you want to discard the changes for a specific file and reset the content of that file as it was in the latest commit, you need to use the command below:

```
git checkout -- file_name
```{{execute}}

This is a convenient command as you can really quickly revert a file back to its original content.

### Commit to local

Once you've made your changes and you've staged them with the `git add` command, you need to commit your changes. 

To do so, you have to use the `git commit` command:

```
git commit
```{{execute}}

This will open a text editor where you could type your commit message.

Instead, you could use the `-m` flag to specify the commit message directly in your command:

```
git commit -m "Nice commit message here"
```{{execute}}

### List branches

In order to list all of the available local branches, just run the following command:

```
git branch -a
```{{execute}}

You would get a list of both local and remote branches, the output would look like this:

```
  bugfix/nginx-www-server-name
  develop
* main
  remotes/origin/HEAD -> origin/master
  remotes/origin/bugfix/nginx-www-server-name
  remotes/origin/develop
  remotes/origin/main
```

The `remotes` keyword indicates that those branches are remote branches.

### Fetch changes from remote and merge the current branch with upstream

If you are working together with a team of developers working on the same project, more often than not, you would need to fetch the changes that your colleagues have made in order to have them locally on your PC.

To do that, all you need to do is to use the `git pull` command:

```
git pull origin branch_name
```{{execute}}

Note that this will also merge the new changes to the current branch that you are checked into.

### Create a new branch

To create a new branch, all you need to do is use the `git branch` command:

```
git branch branch_name
```{{execute}}

Instead of the above, I prefer using the following command as it creates a new branch and also switches you to the newly created branch:

```
git checkout -b branch_name
```{{execute}}

If the `branch_name` already exists, you would get a warning that the branch name exists and you would not be checked out to it,

### Push local changes to remote

Then finally, once you've made all of your changes, you've staged them with the `git add .` command, and then you committed the changes with the `git commit` command, you have to push those changes to the remote git repository.

To do so, just use the `git push` command:

```
git push origin branch_name
```{{execute}}

### Delete a branch

```
git branch -d branch_name
```{{execute}}

### Switch to a new branch

```
git checkout branch_name
```{{execute}}

As mentioned above, if you add the `-b` flag, it would create the branch if it does not exist.

### Conclusion

Knowing the above commands will let you manage your project like a pro!

If you are interested in improving your command line skills in general, I strongly recommend this [Linux Command-line basics course here](https://devdojo.com/course/linux-command-line-basics)!