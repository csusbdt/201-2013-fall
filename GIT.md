# How to Use Git in This Course

To you Git in this course, you need to send to me
a file from your system that contains the public key
that your git client program uses when connecting to 
remote hosts.
After you send this to me, I will create an empty
remote repository for you to push commits into.
I will send you instructions on how to connect to
this repository.

If you want to interact with git from more than one machine,
you need to send me the public key for each machine.
When you send the public key, make sure you mention that it
is a second machine.

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

Copy this text and email to me. 

## From OS X

Use the same process as Linux.

## From a Windows Computer

If you are working under Windows, you should install the git client,
which you can get from [the Git website](http://git-scm.com/).
(The default option settings are OK.)

- Open the Git Bash program and make sure to cd into your home directory.
- Type the command ssh-keygen -t rsa -C "your_email@example.com" to create your SSH pub key
- Optionally enter a passphrase and write it down for later use.
- In your home directory enter the command __ls –a__ and see if _.ssh_ appears in your listings.
- Enter the command  clip < ~/.ssh/id_rsa.pub to copy the contents of your pub key file into the clipboard.
- Paste the contents into an email and send that email to Dr. Turner.

