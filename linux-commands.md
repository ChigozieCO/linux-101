# Everday Linux Commands
A great cloud engineer knows her tools and Linux is one of those tools therefore it is imperative to know how to use linux from the command line.

Below are common commands you would use in your everyday operation in Linux

## Make Directory
A directory is what we know as a folder in the Windows operating system.

A directory holds your files, files are always found in directories and so it is very necessary to know how to create one.

To make a directory in linux, use the command

```sh
mkdir <name of directory>
```

## Navigate into the Directory

Now that you have created a new directory, to be able to do work inside that directory such as create files inside the directory you need to navigate into the directory.

The command to do this is:

```sh
cd <name of directory>
```

## Create File

There are several ways to create a file in Linux, you can do it using the `touch` command as shown below:

```sh
touch <file name>
```

Or you can create the file by opening it with a text editor.

If you call a file that doesn't exist, Linux will open up the file and then ask you to save it when you are done editing that file.

You can make use of any file editor of your choice provided you have it installe.

However, two of the more popular ones are `vim` and `nano` (nano is more beginner friendly and vim takes some getting used to). 

Create the file using either of the commands below:

```sh
vim <file name>
```

or

```sh
nano <file name>
```

## List Files

To confirm that you have successfully created the file, we run the command below:

```sh
ls
```

This command will list all the files in the directory with the exception of the hidden files.

The above command will also not give us any details about the files in that directory.

To see the hidden files in that directory we use the `a` flag as shown below

```sh
ls -a
```

Even though now we are able to see all the files in the directory, we are still not able to see any details about the files.

To get details such as the file owner, the permissions the file has, and the date the file was created you need to use the `-l` flag.

```sh
ls -l
```

Combine it with the `a` flag to veiw the hidden file and get more details about the files

```sh
ls -la
```

## Delete Directory
Another useful command to know is the command used to delete files and directories. We always have a need to delete things.

To delete you use the `rm` command.

If you want to delete a directory:

```sh
rmdir <directory name>
```

:warning: The above command will only work for an empty directory, if there are files present in that directory you will get an error message like you can see in the image below:

<<<<<<<<<<<<<<< 1-1 >>>>>>>>>>>>>>>

There is a command that can be used to delete a directory along with the files it contains in just one step but as a beginner it's advisibkle to be very cautious in using that command.

Bad things have happened :fearful: :grimacing: when that command is used carelessly and so I'll be skipping that.

## Delete File
In order to then delete a directory with the above command you need to first delete the files contained in the directory one after the other.

To delete a file:

```sh
rm <file name>
```
Do this for all the files in the directory then you can sucessfully run the [delete directory command](#delete-directory)

## Clear terminal

After working on your terminal for a while it can become filled up with all your previous commands ran.

To clear that terminal and give you a fresh and empty view, use the `clear` command:

```sh
clear
```

You can also clear your terminal using `ctrl + l`.

Press your ctrl button and the letter `l` at the same time.

The difference between these two methods is that the `clear` command gives you a clean canvas, in the sense that your previous commands do not remain on that terminal again (you can retrieve your command history though).

Whereas `ctrl + l` pushes all your previously run commands upwards, out of view in the terminal and you can easily view them if you scroll up.

Try both methods to see the difference for yourself.

## View Command History

To reuse previously run commands you can simply tap your arrow up key on your keyboard.

To view the commands you have been running, perhaps after you ran the `clear` command use the `history` command as shown below:

```sh
history
```

The number of command saved in our history is determined by the value our HISTSIZE and echo HISTFILESIZE. 

Basically, **HISTSIZE** is the number of commands saved during your current session and **HISTFILESIZE** is the number of commands that will be remembered across sessions (even after a restart). 

The shell sets the default value to 500 after reading any startup files.

To view what the values of your HISTSIZE and HISTFILESIZE are, use the command below:

```sh
echo $HISTSIZE
echo $HISTFILESIZE
```

## Login to Root

Root is the superuser account in Linux. 

It is a user account for administrative purposes, and typically has the highest access rights on the system.

You should always perform tasks as a regular user and only make use of the root user when it is absolutely necessary.

The root user can do many things an ordinary user cannot, such as administrative tasks, changing the ownership of files, mounting disk, formatting & restating a new file system, starting/stopping services etc.

Only a very limited few should be able to have access to the root user account.

To switch to the root user, use the command below:

```sh
sudo su
```

You would then be prompted for the root user password which must be entered correctly for access to be granted.

To exit the root user you can use the `exit` command or switch to another user using the `su` command as seen below

```sh
su <username>
```

## View Contents of a File

You can view the contents of a file directly on the terminal without the use of a file editor using the `cat` command as shown below:

```sh
cat <file name>
```

## Show Working Directory Path

If for some reason you are unable to figure out what directory you are presently in or you just need to print it out on the terminal, use the below command:

```sh
pwd
```

This simply means print working directory. and it will print the file path on your terminal.

## Create User

To create a new user use the `useradd` command

Remember that you must have root privileges to do this, you can have root privilege by either adding `sudo` in front of the command or by logging in to root.

If you are logged in as root user, use the command below:

```sh
useradd <new username>
```

If you are logged in as a normal user you can gain root privilege by using the following command:

```sh
sudo useradd <new username>
```

Note that this command will require you to correctly enter the root user password before the command is run and a new user is added.

## Change Password

To change a user's password or configure the password of a new user you use the `passwd` command.

Just like the `useradd` command you need to be the root user or have root user privilege before you can perform this task.

And so either login as root or add `sudo` to the command:

If you are logged in as root user the command below:

```sh
passwd <username>
```

If you are logged in as a normal user you can gain root privilege by using the following command:

```sh
sudo passwd <username>
```

You will be prompted to enter a new password for the user and then to confirm the password entered.

These are basic commands for everyday operations which you will carry out on your Linux OS. They are enough to get you started.