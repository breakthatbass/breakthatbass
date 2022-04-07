# Setting Up

A bunch of stuff to get yourself set up for basic programming and understanding how to use the tools.

First I'll explain a bit about the teriminal, the shell, and some of the commands you'll want to know. And how it all relates to writing and running code. Then I'll show you how to download tools you need.

## The Terminal and the Shell
When you open the Terminal app, you are presented with a command line. You see the 'prompt' which is the thing that says something like `jordangamache@jordans-macbook-pro ~ %` and the cursor. Those two things are part of the shell. The shell is different from the terminal. You can use a different terminal but use that same shell. And you can use the same terminal but use a different shell. A terminal is just something that provides you with a shell of your choice.

A [shell](https://en.wikipedia.org/wiki/Shell_%28computing%29) is the software that reads in commands and does things based on the command. You should think of the shell as “being” in a certain directory at any particular time. You can move throughout any of the directories in the operating system. Although you can only be in one directory at any given time, you can access anything in any other directory with the file path to what it is you want.

### Some Basic Commands
A command can run by itself, with subcommands, flags, or with arguments. It depends on the command. The `ls` command can be used by itself or with one argument. An argument is extra information for the command which can change how it behaves.

You probably have looked into this by now, but if you haven't, or haven't found anything helpful, here are some basics.

When you type the `ls` command:
```
ls
```
It will list all the files and directories in your current directory. 
Let's provide an argument.

```
ls Documents
```

The argument is `Documents` and with `ls`, providing an argument just tells it to list out the files and directories in the directory of the argument. If you have a directory called Documents in your current directory, it will list it all out. I'm not sure why the term "argument" is used but all it means is you're providing more info for the command to do something.

```
ls -a
```
The `-a` is a flag/option. `ls` has lots of options. Flags always will start with a `-` and then have a single letter. A common one I use though is `-a`. `-a` stands for "all" and it just means 'list all the files'. When you run `ls` by itelf, it ignores any files that begin with a '.' in their name. These are hidden files. Sometimes they're also called dotfiles. They tend to be files for configurations and settings. Usually, you don't want to bother with them when seeing what's in a directory. Sometimes you do though. Run the 'ls -a' command. You'll probably see some files with names like `.zshrc`, `.config`, maybe `.bash_profile` too.

**side note:** what's cool about the terminal and the software that runs in it, is that you have full control to change and customize things at a very granular level. At some point I'll show you how to do that but for now just know that all the customizaing of your shell and other things will happen in these dotfiles in your `~` directory.  

Back to the shell. Mainly, you want to start with navigating the file system, creating files, creating directories, printing files, etc.

Open your terminal and type the following commands, one per line:
```
cd
mkdir projects
cd projects
ls -la
```

This does four things that you'll end up doing a lot.  
1. `cd` means *change directory*. And running `cd` with no arguments just brings you to the `~` directory no matter where you are in the file system.

2. `mkdir projects` - `mkdir` means "make directory". The "projects" argument makes it create a directory called "projects" in your current directory.

3. `cd projects` - This makes you change directory into the new projects directory you just made.

4. `ls -la` - `ls` again, but with two flags. Flags are always a single letter, so `-la` isn't a single flag, but a `-l` flag and an `-a` flag. This is the same as doing `ls -l -a` which will do the same thing. flags can be done all at once and that's normal to do if you are using a lot of flags in a command. We already know what the `-a` will do, adding the `l` means printing out the data in the "long format"

In your projects directory, you should see something like this.
```
total 0
drwxr-xr-x  2 taylorgamache  staff   64 Apr  6 13:12 .
drwxr-xr-x  6 taylorgamache  staff  192 Apr  6 13:35 ..
```

This is showing you all the files you have in projects. Namely there are two of them: `.` and `..`. These mean “this directory” and “parent directory”, respectively. (You know how folders can be inside other folders? The outer folder is called the “parent” folder, which is what the parent directory is.

So if you type `cd ..`, you'll end up in the outer older, or parent directory.

That should be enough for you to understand how commands work. You can probably find what you need online from here. I'll add a small cheatsheet below of all the commands you need to worry about right now.

**You're using the ZSH shell**  


**Scripts and Shell Scripts**  
This isn't something you'll really be doing right now, but it's good to know what it is. 

### Command Cheat Sheet

Below are really al the most important commands that you'll use right now. 
- `touch` - Creates a file. Requires an argument: filename.
    ```
    touch my_python_program.py
    ```
- `cp` - Copies a file. Requires two arguments
    ```
    cp path/to/file path/to/file_copy

    # create a copy in the parent directory with a new name
    cp my_python_program.py ../pyprog.py

    # create a copy in the parent directory with the same name
    cp my_python_program.py ../
    ```
- `mv` - Moves/renames a file. Works exactly like `cp` except it doesn't copy, it moves the original file. You can rename the file in the same way as done in naming the copy in `cp`.
- `rm` - Delete a file or directory.
    ```
    rm my_python_program.py

    # delete a directory with -rf

    rm -rf directory_name

- `cat` - Prints the contents of a file in the terminal. Requires a file as an argument.
    ```
    cat myfile.txt
    ```

### Creating a Python Program
To start, you're going to want to create a directory where you keep your programs. I made a directory called `projects` (like the above example) and it's where I hold all my code. But you can create any file in any directory.

If you still have projects directory from before, `cd` into it. Remember, it's in your home directory, if you're not there you can run the `cd` command by itself and it will bring you there.

Also, a side note about file paths: you can use a full file path as an argument. So if you're in some far away directory, no matter where you are, you can get to the projects directory with `cd ~/projects`. The `~/projects` is the full file path.

When you're in it, your prompt should have `~/projects` in it. Now you can create a file with `touch`. Let's create a Python file. All that means is using the `.py` extension at the end of the file.

Run this command:
```
touch hello.py
```
A Python file has been created! Now to open it in VS Code, you can open Vs Code the normal way, and open a workspace and find the projects directory and it will be there on the side. Another thing you can do is run this command:
```
open ~/projects/ -a 'visual studio code'
```
And it will make the projects directory a workspace.

To open a workspace from in VS Code, click the file explorer icon at the top left and click the "Add Workspace" button.

Now that vs code is open, you can continue using `touch` to create files, or you can click the new file icon at the top left.

Open the hello.py file by clicking on the file name.

Now you can type code!

To start, just add this to `hello.py`:
```
print("hello")
```
That's all we want in the entire file for now. Now go back to your terminal and type this command:
```
python3 hello.py
```
And it will return this:
```
hello
```

It doesn't really do anything but that's how you create and run a python file. Hopefull you can use your Python cheat sheet to learn more about what to do. But as I have time, I'll add more to this document.

Before you move on, try using the `cat` command here. Run `cat hello.py`. It will print out the contents of the Python file you just made to the terminal.

### Homebrew
[Homebrew](https://brew.sh) is great and it will be the main way you install other command line tools.

To install it, run this command"
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

It looks like a bunch of nonsense but all it says is this: *regardless of what shell is the default shell, use the bash shell to download and run the install script from the homebrew website without saving it.* This is basically trying to get a command that would always work on a brand new computer without anything installed yet.

The command to use homebrew is `brew` and it has a lot of subcommands. The only one you need though is `install`.

To confirm it downloaded and installed correctly you can run:
```
brew --version
```
Installing something using Homebrew always works like this:
```
brew install program_name
```

Let's use Homebrew to download `git`. It's as simple as:
```
brew install git
```
Now you have `git` on your computer. You don't need to use it yet but you got to use homebrew. And that's all there is to Homebrew!

One more thing. If you want to uninstall a program you downloaded with Homebrew, you just use the `uninstall` subcommand.
```
brew uninstall program_name
```

### Pip

`pip` works the same exact way but `pip` is used for only python related things. Like homebrew, you use the `install` and `uninstall` subcommands. You won't need `pip` quite yet, but you will soon. It's an easy way to download functions to use in your code without having to write them.