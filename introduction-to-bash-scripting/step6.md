You can pass arguments to your shell script when you execute it. To pass an argument you just need to write it right after the name of your script. For example:

```
./devdojo.com your_argument
```

In the script, we can then use `$1` in order to reference the first argument that we specified. 

If we pass a second argument it would be available as `$2` and so on.

Let's create a short script called `arguments.sh`:

```
nano arguments.sh
```{{execute}}

And then add the following contentn an example:

```
#!/bin/bash

echo "Argument one is $1"
echo "Argument two is $2"
echo "Argument three is $3"
```{{copy}}

Save the file and make it executable:

```
chmod +x arguments.sh
```{{execute}}

Then run the file and pass 3 arguments:

```
./arguments.sh dog cat bird
```{{execute}}

The output that you would get would be:

```
Argument one is dog
Argument two is cat
Argument three is bird
```

To reference all arguments you can use `$@`. Edit the script:

```
nano arguments.sh
```{{execute}}

And update it as follows:

```
#!/bin/bash

echo "All arguments: $@"
```{{copy}}

If you run the script again:

```
./arguments.sh dog cat bird
```{{execute}}

You will get the following output:

```
All arguments: dog cat bird
```

Another thing that you need to keep in mind is that `$0` is used to reference the script itself.

This is a good way to create self destruct the file if you need to or just get the name of the script.

For example, let's create a script that prints out the name of the file and deletes the file after that:

```
#!/bin/bash

echo "The name of the file is: $0 and it is going to be self-deleted"

rm -f $0
```{{copy}}