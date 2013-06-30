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

Each time you complete an assignment,
you should commit your work into a local repository
and then push changes to the remote repository.
Also, you can push changes to your source code that is incomplete.
This lets your remote repository serve as a backup
of your work.  It also allows you to easily work from
multiple computers by synchronizing your local repositories with
your remote repository.

## Security

The process we use to establish authentication
with the remote repository is more secure
than sending a password with email over the Internet.

To understand this, you need to first understand that
your email can be read by people who work for the 
email service providers of the sender and receiver.
They can also be read by people who work for the
Governments with electronic surveillance programs,
such the United States and China.
Finally, if a criminal has compromised the system
used by one of the email service providers,
then they can read your emails.

If we transmitted a password by email,
then one of these actors can
potentially authenticate as you
to the remote repository server.
However, if one of these actors gets your public key,
they can not authenticate as you because
the private key is needed for this.

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

Use the same process as Linux to get the public key and send to the instructor.

### From Windows

If you are working under Windows, you should install the git client,
which you can get from [the Git website](http://git-scm.com/).
(The default option settings are OK.)

Open the Git Bash program and cd into your home directory.

    cd ~

Create your SSH keys. In the following, replace _your-name_ with your name. Setting a passphrase is optional.

    ssh-keygen -t rsa -C "Your-name"

Copy the public key file into the clipboard.

    clip < ~/.ssh/id_rsa.pub

Paste the clipboard contents into an email
and send to dturner@csusb.edu with your name and student id.

### Multiple Computers

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

[TryGit](http://try.github.io/levels/1/challenges/1)
is an excellent interactive tutorial that you can use
to get started.  This tutorial has you create a Github
account and practice git commands that interact with this account.
However, in this course, you will not use GitHub;
instead, you will push commits into a private remote
repository that only you and the instructors have access to.

There are other free tutorials, books and documentation that
you should make use of to better learn Git.
These are easily located on the Web.

