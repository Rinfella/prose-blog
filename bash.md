# Introduction to Linux Terminals and Bash.

### The Linux System:

   Linux is UNIX based free and open-source operating system which is customized and designed in order for better user experience.
  
   Most of the Linux distros have a very nice and easy to understand Graphical User Interface (GUI).
  
   By saying GUI, we mean the visual applications and software we can see, interact with the mouse and/or keyboard. All these graphical elements are what we call a Desktop Environment (DE).

   Some hardcore Linux distros like Arch Linux only have the kernel and terminal out of the box, which means you can interact with it only by typing commands in the terminal.
  
   The terminal (or shell) is similar to cmd or PowerShell in Windows, in which you can run commands to do various tasks.
  
   For example: You can run a command to install an application instead of navigating to the app store or browser, finding a website to download that application and manually downloading it; sometimes running a single command is much faster than doing the same thing by clicking stuffs on your browser.
  
   In the desktop environment with a GUI, we have many terminal emulators which emulates the underlying shell in which we can run the commands.
  
   These terminal applications are simply called terminals for short. Some examples are - PuTTY (Windows), GNOME Terminal, Alacritty, Tmux, Kitty, iTerm, Konsole, XTerm, etc. 


### Basics of Terminals:
 
   The terminal is also known as a command-line, console, or shell. Whatever name you may call it, they refers to the same thing. In a Linux system, the shell interprets the user's commands and script files, and tells the server's operating system what to do with them.
  
   It can be either to update the system, install a new software, remove an installed software, create, copy, move a file, folder, etc.
  
   Users can efficiently and quickly interact because the terminal is a text-based interface and is very lightweight and fast.
  
   There are several kinds of shells like Bash, Zsh, Fish, etc. but they all serve the same purpose: to interprete user input and execute a process according to the user's instructions.

### The Command Prompt:

   When you first open up the terminal, you may see something like `sammy@ubuntu-74DS:~$` written on the first line of the app.
   This is the Command prompt. We will dissect these:
  
   1) sammy: The current user's username.
   2) ubuntu-74DS: The hostname of your computer or server.
   3) ~: The tilde (~) represents the home directory of the user (in our case, it is sammy).
  
   Since we are in the home directory by default when we open the terminal, it shows the home directory, i.e. where we are.
  
   If we login to the shell as a root user, we will see something like: `root@ubuntu-74DS:/home/ubuntu#`.
  
   The current user name changes to root and the prompt also changes the current directory from `~` to `/home/ubuntu`.
  
   This is because the home `(~)` directory for the root user is `/root` and since the root user is not on his home folder, it displays the full path of the current directory.

   1) The (~) is equivalent to /home/sammy or /root, (depending on what user account you used for signing in) which is the home folder of the current user.
   If you navigate to somewhere other than home, the directory you are in will be shown by the command promt on the left hand side.
  
   2) $: The Dollar ($) symbol indicates that the command promt ends here and anything you type into the command prompt will appear after the ($) sign.
  
   3) This ($) sign also indicates that you enter the terminal as a normal user.
   If you enter the terminal as a root mode, the pound (#) sign will appear instead of the ($) sign (more about that later).

### Basic terminal commands:

   **ls**
        : The easiest, yet one of the most important command is `ls`.
   This command lists all the files and folders in the current directory.
   However, in order to be able to see hidden files and folders, we need to add `-a`.
   Now, if we type `ls -a` in the terminal and then hit `Enter` the output will be basically the same, but some files or folder which we have not seen before will be added.
   These files or folders are hidden by default because the file or folder name starts with a dot (.) (you can make any file hidden by default if you add a dot at the beginning of the name), and can be listed by `ls` only if we add the `-a` flag.
   
   **pwd**: This command prints out the full path name of the directory you are currently in.
   If you are unsure in which directory you have navigated yourself into, then type the `pwd` command to print out the current directory you are in.
   
   **cd**
        : The command `cd` is used to change directory, or to move to some other locations in the directory.
   Suppose we are in the home directory /home/sammy or (~).
   In order to know which and what folders are in the current directory we are in, we type `ls`.
   Now, let's say there is a 'Downloads' folder and we want to look inside it.
   Type `cd Downloads` hit `Enter` and then type `ls` then `Enter`.
   This command will navigate you to the Downloads folder and then the `ls` command will list the contents of the Downloads folder.
  
   **touch**
        : The touch command creates an empty file of any type you want.
   The syntax is: `touch filename.txt`.
   This will create an empty file in the current directory you are in.
   If you want to create a file to a specific destination, say under `Documents` in your home folder, we can do this: `touch ~/Documents/filename.txt`.

   **cat**: The cat command (short for `concatenate`) is used to view/print out the contents of a file.
   We do `cat filename.txt` and the contents of the file will be outputted into the terminal.
   Like the touch command, even if you're not in the specific directory you want the file to be displayed, you can still do `cat Downloads/folder1/file1.txt` something like this.

---

   **vim/nano**
        : These are the editor tools we will be using for editing/writing contents of a file in the terminal.
   Since vim is not very beginner friendly, we will stick to using nano, and leave vim for when we're comfortable enough with everything else.
   Now if we want to create a file that does not exist, we can either make the non-existent file with the `touch` command first or directly use `nano`.
   We can do `nano newfile.txt` and write some stuffs into that new file, but if we do not save the changes we made, and just quit without saving, the file will not be created at all.
   Also, if you do `nano newfile.txt` and write nothing into it and just quit, the file will not be created at all.
   That is the main difference between touch and nano.
   All the `touch` command ever did was creating an empty file, but using `nano`, you can create a new file, but it cannot be empty.
   After writing anything you want using nano into that file, press `Ctrl + o` to save the changes you made and then `Ctrl + x` to quit the editor.
   (I didn't even want to bother writing instructions on how to use vim because even just the process of exiting the vim editor is worth a whole youtube video... Just imagine how complex the key bindings are..)

---

   **rm**
        : The rm command removes a file or a folder, basically anything.
   
   Usage: `rm <target_file>`
   or in case of a folder/directory:
   `rm -r <target_folder_or_directory>` OR `rmdir <target_folder_or_directory>`.
   
   rmdir can be used only drectories/folders and if wen want to remove a folder using the rm command, we need to pass the recursive (-r) flag.
   Keep in mind that if you remove anything using this rm or rmdir command, it is gone forever, no recycle bin, no nothing.. JUST GONE.
   So be very careful when using this command.

---

   **cp**
        : The cp command is used to copy a file or a folder from one place to another.
   Like the rm command, if you want to use the cp command on a folder, you need the (-r) flag:
   
   `cp <file1_name> <destination>` OR `cp -r <folder1> <destination>`
   
   What the `-r` flag does is that it recursively replicates the command applied on the parent folder to all its content inside and its sub-directories.
   We can also assign a different name to the file/folder we copied:
   
   `cp filename1 same_file_with_another_name`.

---

   **mv**
        : The mv command is used to move files and folders from one place to another.
   We don't need the `-r` flag in case of mv.
   Usage: `mv <file1> <destination>`.
   Like cp, the mv command can also rename the file/folder on the go:
   
   `mv <file1> <destination/filename2>`
   
   You can move the file and rename at the same time, but if you only want to rename the file, just move it within the same folder and give it a different name.

   

### If you want to know more, check out this tutorial made by [DigitalOcean](https://www.digitalocean.com/community/tutorials/an-introduction-to-the-linux-terminal)
### Feel free to ask anything you doubt about Linux and its related resources in my [Email](mailto:rinfellapachuau93@gmail.com) or [Telegram](https://t.me/rinfella) 




