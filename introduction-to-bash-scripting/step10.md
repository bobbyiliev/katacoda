# Bash Loops

As with any other language, loops are very useful. With bash you can use `for` loops, `while` loops and `until` loops.

## For loops

Here is the structure of a for loop:

```
for var in ${list}
do
    your_commands
done
```

For example, create a new file:

```
nano for-loop.sh
```{{execute}}

And add the following content:

```
#!/bin/bash

users="devdojo, bobby, tony"

for user in ${users}
do
    echo "${user}"
done
```

Then run the file:

```
bash for-loop.sh
```{{execute}}

You can also use `for` to process a series of numbers, for example here is one way to loop through from 1 to 10:

```
#!/bin/bash

for num in {1..10}
do
    echo ${num}
done
```

## While loops

The structure of a while loop is quite similar to the `for` loop:

```
while [ your_condition ]
do
    your_conditions
done
```

For example, create a new file:

```
nano while-loop.sh
```{{execute}}

And add the following content:

```
#!/bin/bash

counter=1
while [[ $counter -le 10 ]]
do
    echo $counter
    ((counter++))
done
```

Finally run the script:

```
bash while-loop.sh
```{{execute}}

Now let's create a script that asks the user for their name and not allow an empty input:

```
#!/bin/bash

read -p "What is your name? " name
ba
while [[ -z ${name} ]]
do
    echo "Your name can not be blank, please enter a valid name!"
    read -p "Enter your name again? " name
done

echo "Hi there ${name}"
```

If you run the above and just press enter without providing input, the loop would run again and ask you for your name again and again until you actually provide an input.

## Until Loops

The difference between `until` and `while` loops is that the `until` lool will run the commands within the loop until the condition becomes true.

Structure:

```
until [ your_condition ]
do
    your_commands
done
```

For example, create a new file:

```
nano until-loop.sh
```{{execute}}

And add the following content:

```
#!/bin/bash

count=1
until [ $count -gt 10 ]
do
    echo $count
    ((count++))
done
```

Finally run the script:

```
bash until-loop.sh
```{{execute}}

## Continue and Break
As with other languages you can use `continue` and `break` with your bash scripts as well:

* `continue` tells your bash script to stop the current iteration of the loop and start the next iteration
* `break` tells your bash script to end the loop straight away