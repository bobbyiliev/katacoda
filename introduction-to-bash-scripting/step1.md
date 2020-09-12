Let's start by creating a new file with a `.sh` extension, as an example we could create a file called `devdojo.sh`.

To create that file, you can use the `touch` command:

```
touch devdojo.sh
```{{execute}}

Next, make sure that you have the `nano` text editor installed:

```
apt install nano
```{{execute}}

Or you can use your text editor instead.

After that edit the newly created `devdojo.sh` file:

```
nano devdojo.sh
```{{execute}}

In order to execute/run a bash script file with the bash shell interpreter, the first line of a script file must indicate the absolute path to the bash executable:

```
#!/bin/bash
```{{execute}}

This is also called a [Shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)). All that the shebang does is to instruct the operating system to run the script with the `/bin/bash` executable.

To save the file with `nano` press `CTRL+O` and then press `ENTER`, to exit press `CTRL+X`.