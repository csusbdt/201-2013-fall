## Overview

In this course, you have the option of submitting work
to a private remote Git repository.

In order for us to set up a private remote repository for you,
you need to send to us the public key that your Git client
program uses when connecting to remote hosts.
After you send this, we will create an empty
remote repository for you to push commits into.
We will also send you a username that you can use to
connect to this repository.
After you receive the username, you will be able
to clone the empty repository and use this to
submit your work and track changes to the
source code you develop.
The command you will use to clone your repository will
look like the following, with _username_
replaced by the username we email to you.

    git clone username@web1.ias.csusb.edu:201.git

Each time you complete an assignment,
you should commit your work into a local repository
and then push changes to the remote repository.
Also, you can push changes to your source code that is incomplete.
This lets your remote repository serve as a backup
of your work.  It also allows you to easily work from
multiple computers by synchronizing your local repositories with
your remote repository.

## Security

Email is not completely private.
There are a number of different actors who can read
emails, including employees of the companies that
provide email service to the sender and receiver,
workers who are part of government surveillance activities
(such as those who work for the US National Security Agency),
and any criminals who may have compromized systems of one of the
email service providers.

With this in mind,
it's safer to email public keys than passwords.
If someone gets your password, they can
authenticate as you;
if they get your public key, they can not.

However, one danger with sending public keys by email
is that an imposter
can send the recipient their own public key.
To mitigate this threat,
we will accept only a single public key for each repository.
Consequently, if you want to access your repository from
multiple computers,
you need to copy your public-private key pair
to all these computers.
See the section _Multiple computers_ below
to see how to do this.

## Setup instructions

### From JB 359

If you are using the computers in JB 359 (or 358),
then git is already installed for you.
However, you will need to send me the contents of the
file that contains your SSH public key.
You can get this file from the following location.

    ~/.ssh/id_rsa.pub

To see its contents, use the cat command as follows.

    cat ~/.ssh/id_rsa.pub

The file will look something like the following.

````
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDymdGr+QUAhvClI/7c8+ulzSxEH783b9tatMlB4ou53YgOTYrsJEN2rLilpgPeM6pxHt3EtD5aVO8boklZmzpwy/eDHSq8Dxzdhv+lxzv8KmRm8wX7vkBgezrQHoBcjWDyiztH/2MoE5uL42yT3goGPBXsbx/rq0QrwUxnzqNMjJ0R2HsWqF5VV/t0G0mJfgZVuCVBokSMmmuKof1KtUk+R0zTlxCMUhc7EMWf39gVXc6+JWJJqthV71VY8mX4y0CSsNa0/ILMIlyUV7kd4OLPi7qwjAlA292tsh+n3McaQAwWIuKJmO6gIq5rAvDsiIXbKQGaoVd4Sb6ABUuMgVo9 turner@turner-retina.home
````

Copy this text and email it to dturner@csusb.edu with your name and student id.

### From OS X

If you are working under OS X, you should install the git client,
which you can get from [the Git website](http://git-scm.com/).

Use the same process as for Linux to get the public key and send it with your name
and student id to the instructor.

### From Windows

If you are working under Windows, you should install the git client,
which you can get from [the Git website](http://git-scm.com/).
(The default option settings are OK.)

Open the Git Bash program and cd into your home directory.

    cd ~

Create your SSH keys. 
In the following, replace _your-name_ with your name. 
I recommend to not set a passphrase -- just press enter when prompted for one.

    ssh-keygen -t rsa -C "Your-name"

Copy the public key file into the clipboard.

    clip < ~/.ssh/id_rsa.pub

Paste the clipboard contents into an email
and send to dturner@csusb.edu with your name and student id.

### From Linux

You should try to follow the procedure described above for Linux computers in JB 359.

If you are receiving the message _Agent admitted failure to sign using the key_, then try running
ssh-add to load your keys into the SSH agent.

    ssh-add

### Multiple computers

If you want to interact with git from more than one machine,
you need to make sure that the private and public key files 
are the same across all the computers.
The private and public key files are contained in the following
files, respectively.
Both of these files contain character data,
so you can easily access and manipulate their contents.

- ~/.ssh/id_rsa
- ~/.ssh/id_rsa.pub

If you use multiple computers to complete work in this course,
remember to start a work session by pulling changes from the
remote repository, and to end a work session
by pushing changes to the remote repository.
To avoid synchronization problems, adhere to the following 2 rules.

- When you start a work sesion, pull from your remote repository.
- When you end a work session, push to your remote repository.

## Learn Git

In addition to setting up Git on your system,
you will also need to learn how to use it.
While you are waiting for me to create your repository,
you should complete the
[TryGit](http://try.github.io/levels/1/challenges/1) tutorial.
After this, familiarize yourself with
[the documentation for Git](http://git-scm.com/doc)
and [the Git book](http://git-scm.com/book).
I recommend that you read a few chapters of the
Git book and then carefully read 
[Chapter 9 on Git Internals](http://git-scm.com/book/en/Git-Internals).
The Git Internals chapter provides essential concepts
and details needed to understand Git.

