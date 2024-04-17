# Lab Report 1 - Henry Pond

## `cd` command

### No arguments

```
$ cd

henry@DESKTOP-87ALL79 MINGW64 ~
$ pwd
/c/Users/henry
```

The absolute path to the working directory was `/c/Users/henry`.

The absolute path does not change after running `cd`. This is because running `cd` with no arguments changes the working directory to the home directory, which is also `/c/Users/henry`. 

This output is not an error, the working directory is now the home directory.

### Directory argument

```
$ cd lecture1

henry@DESKTOP-87ALL79 MINGW64 ~/lecture1 (main)
$ pwd
/c/Users/henry/lecture1
```

The absolute path to the working directory was `/c/Users/henry`.

When offered a directory as an argument, the working directory becomes the directory offered as 
an argument. Since we offered the `lecture1` directory as an argument, the new working directory
became `/c/Users/henry/lecture1` as seen above with the `pwd` command.

This output is not an error, as we gave the command a proper argument and it executed as expected.

### File argument

```
$ cd Hello.java
bash: cd: Hello.java: Not a directory

henry@DESKTOP-87ALL79 MINGW64 ~/lecture1 (main)
$ pwd
/c/Users/henry/lecture1
```

The absolute path to the working directory was `/c/Users/henry/lecture1`.

When offered a file as an argument, the terminal output an error stating that the given argument, 
in this case the file `Hello.java`, was not a directory. The working directory did not change as a result.

This output is an error, as we did not give the command a proper argument. As a result, the command did 
not execute and the directory did not change.

## `ls` command

### No arguments

```
$ ls
Hello.class  Hello.java  messages/  README
```

The absolute path to the working directory was `/c/Users/henry/lecture1`.

When no argument was offered, the command simply listed the contents of the `lecture1` directory, that being the three files and the folder seen in the output above. This is because when `ls` is ran without arguments, it lists the contents of the current working directory, which in this case is `/c/Users/henry/lecture1`.

This output is not an error, as the command executed as expected.

### Directory argument

```
$ ls messages
en-us.txt  es-mx.txt  zh-cn.txt
```

The absolute path to the working directory was `/c/Users/henry/lecture1`.

When the directory `messages` was offered as an argument, the command listed the contents of the
offered directory, that being the three text files seen above.

This output is not an error.

### File argument

```
$ ls Hello.java
Hello.java
```

The absolute path to the working directory was `/c/Users/henry/lecture1`.

When the file `Hello.java` was offered as an argument, the command output the name of the file itself.

This output is not an error, as we gave the command a file to list as an output and the command executed as expected.

## cat command

### No arguments

```
$ cat




test
test
```

The absolute path to the working directory was `/c/Users/henry`.

When no arguments were offered, the command seemed to output whatever characters were input, including the new line
character and the string `test` as seen above. The command could only be aborted with CTRL+C.

This output is technically not an error, as the terminal is concatenating the string or character offered as an argument.
However, this use case seems quite limited.

### Directory arguments

```
$ cat lecture1 Documents
cat: lecture1: Is a directory
cat: Documents: Is a directory
```

The absolute path to the working directory was `/c/Users/henry`.

When directories were offered as arguments, the command output errors stating that the given arguments were directories.
This is because the command is not designed to work with directories as arguments.

This is an error for the reason stated above.

### File arguments

```
$ cat en-us.txt es-mx.txt
Hello World!
¡Hola Mundo!
```

The absolute path to the working directory was `/c/Users/henry/lecture1/messages`.

When files were offered as arguments, the command printed the text contained within the files one after the other,
with `en-us.txt` being printed first followed by `es-mx.txt`.

This is not an error, as the command executed as expected when given proper arguments.
