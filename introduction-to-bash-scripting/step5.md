As with any other programming language you can add comments to your script. Comments are used to leave yourself notes through your code. 

To do that in bash you need to add the `#` symbol at the beginning of the line. Comments will never be rendered on the screen.

Here is an example of a comment:

```
# This is a comment and will not be rendered on the screen
```{{execute}}

Let's go ahead and add some comments to our script:

```
#!/bin/bash


# Ask the user for their name

read -p "What is your name? " name

# Greet the user
echo "Hi there $name"
echo "Welcome to DevDojo!"
```{{copy}}
