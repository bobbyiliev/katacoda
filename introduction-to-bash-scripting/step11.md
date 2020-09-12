# Bash Functions

Functions are a great way to reuse code. The structure of a function in bash is quite similar to most languages:

```
function function_name() {
    your_commands
}
```

You can also omit the `function` keyword in the beginning which would also work:

```
function_name() {
    your_commands
}
```

I prefer putting it there for better readability.

Example of a "Hello World!" function:

```
#!/bin/bash

function hello(){
    echo "Hello World Function!"
}

hello
```

One thing to keep in mind is that when you call the function, you should not add the parenthesis.

Passing arguments to a function works in the same way as passing arguments to a script:

```
#!/bin/bash

function hello(){
    echo "Hello $1!"
}

hello DevDojo
```

As a test, try creating a new file yourself and use the above code to test it!