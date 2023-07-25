# Welcome to TUX

![tux](tux.jpg)
## What is a Distro

![](distro_tree.png)

There are many distributions of Linux but for our case we only care about those that are derived from debian (which is still a lot of distros).

You can know that a distro is derived from debian by simply looking at its package manager (we will talk more about package management later), if the distro uses `apt` then it is derived from debian.

## File system tree

![](linux_tree.jpg)

## Linux Command Line

### Start the terminal

![Start_terminal](start_terminal.png
"Start the terminal")

### List Files

The photo shows the most used flags of the `ls` command but there are many other flags.

![List_files](List_files.png)

### Man

The `man` command is your best friend when you need a quick description of a certain command. `man` stands for "Manual" and it does exactly what you think it does.

Let's say you want to know what other flags can the `ls` command accept, to get that you can type `man ls` to get the full description of the `ls` command.

![](man.png)

Use your arrows to navigate the Manual page (optionally you can use the vim keys). And when you are ready to exit press `q` to quit.

Notice that `man` is just another regular command, so if you want more info on `man` you can always use `man man` to read the manual of the `man` command.

### Change Directory

![Change Directory](change_directory.png)

### creating Files

You can create a file by using the `touch` command. This will create an empty file.

![](touch.png)

### Editing Files

Now that you have created your files you want to edit them. You can do so using a text editor. `nano` is the simplest terminal text editor found on most linux systems.

If I want to edit `file1.txt` for example, I will use the command `nano file1.txt`. Note that if you use the command `nano file2.txt` and `file2.txt` does not exist, nano will create it for you and you can start editing it right away, so if you want to create a file and edit it you don't need to use the `touch` command at all.

### Making Directories

To make a new directory use the `mkdir` command, and it works just like the touch command. So for example if I want to create a directory called "myDir" I would just type `mkdir myDir`

