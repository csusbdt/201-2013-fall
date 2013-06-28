# How to Use Git in This Course

To you Git in this course, you need to send to me
the public key that your Git client program uses
when connecting to remote hosts.
After you send this to me, I will create an empty
remote repository for you to push commits into.
I will also send you a username that you can use to
connect to this repository.
After you receive the username, you will be able
to clone the empty repository and use this to 
submit your work and track changes to the
source code you develop for labs and assignments.

Each time you complete an assignment,
you should commit your work into a local repository
and then push changes to the remote repository.
Also, you can push changes to work that is incomplete.
This lets your remote repository serve as a backup
of your work and allows you to easily work from
multiple computers.

## From JB 359

If you are using the lab machines, then git is already installed for you.
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

Copy this text and email it to dturner@csusb.edu
with your name and student id.

## From OS X

Use the same process as Linux.

## From a Windows Computer

If you are working under Windows, you should install the git client,
which you can get from [the Git website](http://git-scm.com/).
(The default option settings are OK.)

Open the Git Bash program and cd into your home directory.

    cd ~

Create your SSH keys. (Setting a passphrase is optional.)

    ssh-keygen -t rsa -C "your_email@example.com"

Copy the public key file into the clipboard.

    clip < ~/.ssh/id_rsa.pub

Paste the clipboard contents into an email
and send to dturner@csusb.edu with your name and student id.

## Multiple Computers

If you want to interact with git from more than one machine,
you need to make sure that the private and public key files 
are the same across all the computers and that you send 
to me the public key.  The private and public key files
are as follows.

- ~/.ssh/id_rsa
- ~/.ssh/id_rsa.pub

If you use multiple computers to complete work in this course,
remember to push changes to the repository
when you and a work session so that you can pull the changes
on the other computers.
To avoid synchronization problems, adhere to the following 2 rules.

- When you start a work sesion, pull from your remote repository.
- When you end a work session, push to your remote repository.

## Learning Git

In addition to setting up git on your system,
you will also need to learn how to use it.

[TryGit](http://try.github.io/levels/1/challenges/1)
is an excellent interactive tutorial that you can use
to get started.  This tutorial has you create a github
account and practie git commands that interact with your account.
In CSE 201, you will not use GitHub; instead, you will
push commits into a private remote repository that only
you and the instructors have access to.

There are other free tutorials, books and documentation that
you should make use of to better learn Git.
These are easily located on the Web.

