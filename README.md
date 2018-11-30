# Makefile Helper Generator

If you are working on a project which has a Makefile containing lots of commands, this might turn your life easier.

[![asciicast](https://asciinema.org/a/r9P8SvhNieCpRlERq6ssx11BR.png)](https://asciinema.org/a/r9P8SvhNieCpRlERq6ssx11BR)

This is an example in which we have a small Makefile, but imagine a greater one.

# How to make this happen?

- Your Makefile must have some comments in order to generate a properly help message. Like the Makefile model you can find in this project.
- You must have a command called `help`, that will execute the help generator for the Makefile.

### Example:

A Makefile command with a help comment.
```bash
say-hello:
    @# say-hello - Show a Hello world message.
    @echo "Hello world"
```

The `help` command in order to print the Makefile help.
```bash
help:
    @# help - Show this help.
    @./MakefileHelp.sh
```
Make sure that you have the `MakefileHelp.sh` file in the right path.

After that, you must only type `make help` and voilà! The magic happens!

The above example must print that help:
```bash
say-hello          - Show a Hello world message.
help               - Show this help.
```
Now you don't need to read all the Makefile in order to find how exaclty you must type that command you're looking for!