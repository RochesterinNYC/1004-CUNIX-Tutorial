[CUNIX/UNIX Tutorial](http://rochesterinnyc.github.io/1004-CUNIX-Tutorial/)
---
####1004 - Intro to Computer Science and Programming in Java 
-------

This is a tutorial on UNIX and how to use CUNIX, the Columbia system of UNIX hosts, for 1004: Intro to Computer Science and Programming in Java. You will be able to use CUNIX to compile and run your Java programs if you wish.

-------

###Table of Contents

- [Terms/Definitions](#terms)
- [Login](#login)
- [CUNIX](#cunix)
- [Commands](#commands)
- [Demo](#demo)
- [Other Notes](#other)
- [More Resources/Documentation](#docs)

-------

<a name="terms"></a>

###Term Definitions:

####Operating System

- The core program that handles management, execution, scheduling, etc. of other programs/applications.

####Host

- A computer system that is accessed by remote users (not physically at the machines that the system runs on).

####UNIX

- Family of Operating Systems that follows a certain set of specifications ('Unix Philosophy').

####CUNIX

- Columbia system of UNIX hosts.

####Java

- Object-oriented programming language that is portable due to how it runs on an environment called the JVM (Java Virtual Machine) that can be held relatively consistent across various systems.

####Compile/Compilation

- To take source code (ex. Java code) and translate it into functionally equivalent code of another language (ex. bytecode), often to prepare for execution.

####File

- Collection of data items on disk.

####Directory/Folder

- Group of files or other directories (subdirectories).

####Text Editor

- A program that allows user to create, delete, and manipulate various text-based files.
- Examples: Pico, Nano, Vim, Emacs, Sublime Text

####Shell

- Program with a user interface that allows a user to access an operating system and send it commands to execute and see the results or errors.

####Command

- A text instruction telling a shell or program to execute some specific functionality.

####Arguments/Flags

- A way to specify options or configurations for how a command should execute. These are typically extra text words, characters (sometimes prefaced with a dash -), etc. and vary across different programs and commands.
- Flags can be stacked. Ex. if -a is an argument flag and -l is an argument flag, -la or -al is a valid argument flag.

------

<a name="login"></a>

###Login to CUNIX:

####Windows:

- Install PuTTY at: <a href="http://cuit.columbia.edu/putty-software">CUIT PuTTY</a>

- Open PuTTY.

- Specify the following as the hostname for the connection:

    cunix.cc.columbia.edu

- Specify your uni as the login and your Columbia password as the password. Make sure that the SSH option is the connection option that is selected.

- Open the connection.

####Mac or Linux:

- Open your shell program (Terminal, iTerm2, Xfce, etc.).

- Type the following command:

        ssh youruni@cunix.cc.columbia.edu

Example:
 
    ssh sdk777@cunix.cc.columbia.edu

- Type and enter 'yes' to the following prompt (will only pop up on first login):

    Are you sure you want to continue connecting (yes/no)?

- You will see the following prompt. Type and enter your Columbia account password.

    KerberosV Password:

####On Success:

On successful login and connection to the CUNIX system, you will see something like the following:

    Last login: Thu Jan 29 00:45:01 2015 from dyn-160-39-228-
    Sun Microsystems Inc.   SunOS 5.9       Generic May 2002
    $

<a name="cunix"></a>

###CUNIX:

- You are now logged into a CUNIX host that is running on a machine that is owned by Columbia University.

- When you type commands into your shell program and press enter, these commands are sent through the network (through the ssh connection) to the respective shell program running on the CUNIX host. The remote shell program attempts to execute your command on that host. The result or errors are sent back from the UNIX OS to that remote shell program, then through the network to your computer, and your shell program displays that result or the errors.

- You are at your base directory (jrw2175). If you enter in the following command:

        pwd

You should see the following result:

    /u/#/first_initial/uni

Example:

    /u/4/j/jrw2175

<a name="commands"></a>

###Commands:

####Directory Navigation:

- Print your current directory path/location:

        pwd

- Go into a directory (ex. directory named 'target'):

        cd target

- Go up a directory (to the directory that contains the current directory you're in):

        cd ..

- Go back to the previous directory you were in:

        cd -

- Go to your home directory (the directory you start in when you first login):

        cd ~

- Go to the root directory (the base directory of the host system you're accessing):

        cd /

- Exit your session and logout:

        exit

Please note that the following directory symbols denote special things:

- '.' is the current directory you're in.
- '..' is the directory that contains the directory you're currently in.
- '~' is your home directory.
- '/' is the base directory.

####File Management:

- List all files and directories:

        ls

- List all files and directories with details:

        ls -l

- List all files and directories (including hidden ones):

        ls -a

- Print the contents of a file (ex. code.txt):

        cat code.txt

- Create a new, blank file (ex. filename.txt) and update the access time:

        touch filename.txt

- Open a new or existing file (ex. filename.txt) in the pico text editor program:

        pico filename.txt

- Create a new directory (ex. newdirectory) in the current directory:

        mkdir newdirectory

- Move a file (ex. filename.txt) or directory (ex. orgdirectory):

        mv filename.txt destination
        mv orgdirectory destination

- Copy a file (ex. originalfile.txt and its copy newfile.txt) (if there already exists a file called 'newfile.txt' in the destination being copied to, that file will be overwritten):

        cp originalfile.txt newfile.txt

- Copy a directory (ex. originaldirectory and its copy newdirectory) (if there already exists a directory called 'newdirectory' in the destination being copied to, that directory and its contents will be overwritten):

        cp -r originaldirectory newdirectory

- Delete a file (ex. filename.txt):

        rm filename.txt

- Delete a directory (ex. deldirectory) (this will also delete all the contents of the directory). 

        rm -r deldirectory

####Java:

- Compile a java program. (ex. Hello.java):

        javac Hello.java

- Run a java program. (ex. Hello.class) (Note that specifying the .class extension is not necessary.):

        java Hello

####System Commands (Extra Stuff):

- Check manual page for a program (ex. javac) (press 'enter' to move down the manual page and 'q' to quit the manual):

        man javac

- See memory usage and process information of the system (press 'q' to quit the view):

        top

- See processes running for on the system:

        ps -A

Some more advanced, interesting, and potentially useful commands/programs to look up or get familiar with:

- Searching: grep and find
- Comparison: diff
- File/Directory Permissions: chmod
- Process Killing/Shutdown: kill
- Compression/Decompression: gzip and tar
- Text (chars, words, lines) Counting: wc
- More Advanced Text Editors: vi/vim, emacs
- Executing with Admin/Root Privileges: sudo

------

<a name="demo"></a>

###Hello CUNIX/Java Demo:

- Check the current directory path.
- Create a directory called 'hello'.
- Go into that directory.
- Check the current directory path. It should be your previous directory path along with '/hello' at the end.
- Open a new file called 'Hello.java' in the pico text editor (or vim if you're comfortable with that).
- Copy and paste the following code in that file:
    
        public class Hello {
          public static void main(String[] args) {
            System.out.println("1004 is the best class and I love CS loads already!");
          }
        }

Columbia's pico guide page is here: <a href="http://www.columbia.edu/acis/publications/pico.html">Pico Guide Page</a>

- List the files in the directory. You should see the following:

        Hello.java
    
- Enter the following command that will compile the Java code/program you just created. (You shouldn't see any output after this command, just the $ prompt again).

        javac Hello.java

- List the files in the directory. You should see the following: (The Hello.class was created through the compilation command you just ran)

        Hello.class Hello.java 

- Run the 'Hello' Java program with the following command:

        java Hello

- You should see the following prompt:

        1004 is the best class and I love CS loads already!

Full Example Output:

        $ pwd
        /u/4/j/jrw2175
        $ mkdir hello
        $ cd hello
        $ pwd
        /u/4/j/jrw2175/hello
        $ pico Hello.java
        $ ls
        Hello.java
        $ javac Hello.java
        $ ls
        Hello.class  Hello.java
        $ java Hello
        1004 is the best class and I love CS loads already!
        $

------

<a name="other"></a>

###Other Notes:

- If you do certain system-breaking operations, it will probably be in the server logs and it can be traced back to your uni so refrain from doing such things.
- However, do feel free to explore the system by navigating wherever you are allowed. Places where you should not be able to access will result in "Permission denied" messages (ex. trying to access other students' home directories).

------

<a name="docs"></a>

###More Resources /Documentation:

I highly recommend this tutorial (It's been used in 1004 for several years.):

<a href="http://www.cs.columbia.edu/~bert/courses/1003/cunix.html">CUNIX Tutorial</a>

<a href="http://cuit.columbia.edu/putty-configuration-tutorial">PuTTY Configuration</a>

<a href="http://www.columbia.edu/acis/publications/pico.html">Pico Guide Page</a>

<a href="http://bit.ly/1HhhPTm">Google: Lots of Intro UNIX Tutorials</a>