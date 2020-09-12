Once we have our `devdojo.sh` file created and we've specified the bash shebang on the very first line, we are ready to create our first `Hello World` bash script.

If you have not done so already, open the `devdojo.sh` file again:

```
nano devdojo.sh
```{{execute}}

And add the following after the `#!/bin/bash` line:

```
#!/bin/bash

echo "Hello World!"
```

Save the file and exit. To save the file with `nano` press `CTRL+O` and then press `ENTER`, to exit press `CTRL+X`.

After that make the script executable by running:

```
chmod +x devdojo.sh
```nano devdojo.sh

After that execute the file:

```
./devdojo.sh
```nano devdojo.sh

You will see a "Hello Wolrd" message on the screen.

Another way to run the script would be:

```
bash devdojo.sh
```nano devdojo.sh

As bash can be used interactively, you could run the following command directly in your terminal and you would get the same result:

```
echo "Hello DevDojo!"
```nano devdojo.sh

Putting a script together is useful once you have to combine multiple commands together.