# Makefile Helper Generator :dog:

If you are working on a project which has a Makefile containing lots of commands, this might turn your life easier.

## How to use it?

You must to create a file called `MakefileHelp.sh` containing the same conntent as the MakefileHelp.sh in this project. After that, you must set this file execution permission (`chmod +x MakefileHelp.sh`).

The following command will do both:

```bash
wget https://raw.githubusercontent.com/diogocavilha/make-help-generator/master/MakefileHelp.sh \
-q -O MakefileHelp.sh \
&& chmod +x MakefileHelp.sh
```

## How does it work?

- Your Makefile must have some comments in order to generate a properly help message. Like the Makefile example you can find in this project.
- You must have a command called `help`, that will execute the help generator for the Makefile.

**Example:**

Add help comments to your Makefile commands like:

```bash
run:
	@# run - Run the project.
	# commands...

build:
	@# build - Build the project.
	# commands...

unit-tests:
	@# unit-tests - Run unit tests.
	# commands...

integration-tests:
	@# integration-tests - Run integration tests.
	# commands...

help:
	@# help - Show this help.
	@./MakefileHelp.sh
```

Take a look at the last command called `help`. 
The `help` command will print the Makefile help.

```bash
help:
    @# help - Show this help.
    @./MakefileHelp.sh
```
Make sure that you have the `MakefileHelp.sh` file in the right path.

After that, you must only type `make help` and voilà! The magic happens!

The above example must print that help:
```bash
$ make help

 run                - Run the project.
 build              - Build the project.
 unit-tests         - Run unit tests.
 integration-tests  - Run integration tests.
 help               - Show this help.
```
Now you don't need to read all the Makefile in order to find how exaclty you must type that command you're looking for!
