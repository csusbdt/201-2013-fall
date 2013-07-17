# How to work remotely using SSH

You can use SSH (a communications protocol) to connect to our lab machines from outside the lab.
To do this, you need to have an SSH client installed on your computer.
In Windows, you can install a free program called _Putty_;
in OS X and Linux, an ssh command line client is pre-installed.
In Windows, you launch Putty; in OSX and Linux, you need to open a console window
and run the program with the command _ssh_.

Because of the firewall around the lab machines,
you can not directly connect to a lab machine.
To get to a lab machine, you need to connect to an intermediate computer
that is outside the firewall but has access to the lab machines.
This computer is called _jbh3-1_ and is in the domain _cse.csusb.edu_.
The fully qualified host name is as follows:

    jbh3-1.cse.csusb.edu

As an example, suppose your CSE computer system account name is _alice_
and you are working from OS X (or Linux).
Then, open a terminal window and run the following command.

    ssh alice@jbh3-1.cse.csusb.edu

Under Windows, you should establish the SSH connection by running Putty.
This will give you access to a terminal window connected to jbh3-1.

You can not run the C++ compiler from jbh3-1.
The intent of this computer is to provide a single point of entry into
the network that computers in our labs are connect to.
For this reason, you need to run a second SSH session inside the first one
to connect to a computer in lab room jb359.

There are 30 computers in jb359 labeled jb359-1 to jb359-30.
You can try to connect to any one of these.
As an example, suppose we are alice already logged into jbh3-1.
To connect to jb359-8, run the following command.

    ssh jb359-8

Note that you can omit the username and domain name in the above command
because the ssh program will use the username and domain of the host you are running from,
which in our case is _alice_ and _cse.csusb.edu_.

After you are logged into a computer in JB 359,
you need to run a console-based text editor to write programs.
There is a simple text editor installed on the lab machines called _nano_ that you can use.
You can not use programs that rely on a graphical window, such as gedit.

To launch nano to edit or create a file called main.cpp, run the following from the command line.

    nano main.cpp

When you are inside nano, you can save your work by holding down the control key and pressing the 'O' key.
You can exit by holding down the control key and pressing the 'X' key.

When you are finished working on the remote machine,
you should issue the exit command to terminate the connection.
Enter the exit command twice to terminate both connections, one after another.

    exit
    exit

