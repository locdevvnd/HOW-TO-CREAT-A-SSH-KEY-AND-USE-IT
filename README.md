# _Hello, this is Loc_ 😎

## _Here is my information, and you can contact me_

- Phone number: +84 898202569
- Address: Danang, Viet Nam
- Gender: Male
- Email: locong1224@gmail.com
- Github: https://github.com/locdevvnd

## CREATE ONE SSH KEY

>  ### HOW TO CREATE ONE SSH KEY AND USE IT

![](https://sebastien.saunier.me/images/posts/SSH%20Connection%20explained.png)

### Step 1: 
- Check if your machine has any ssh key
- Open a command line (terminal) and run the command:
```sh
$ ls -al ~/.ssh 
``` 

The above command will check in the .ssh directory (located in the root directory of the user you are logging in to the machine, eg on Mac: /Users/loc/.ssh) has any ssh key, by default, normal ssh keys will have the form:

```
id_rsa
id_rsa.pub
id_dsa.pub
id_ecdsa.pub
id_ed25519.pub
```
The public key will have the extension .pub (id_rsa.pub), the private key will have no extension (id_rsa)
If there is an ssh key pair in this directory (say id_rsa and id_rsa.pub), you can skip Step 2 and go straight to Step 3.


### Step 2:

- Run a following command on terminal

```
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```
- To avoid trouble later, I recommend you leave the settings at default, like this time, ssh-agent asks where you want to save your key, just press Enter:
```
Enter file in which to save the key (/Users/binhcq/.ssh/id_rsa): [Press enter]
```
- Next, enter the password for your key
```
Enter passphrase (empty for no passphrase): [Type a passphrase]
# Enter same passphrase again: [Type passphrase again]
```
- After entering the password, you will receive a notification that the password has been saved to the address you specified earlier:
```
Your identification has been saved in /Users/you/.ssh/id_rsa.
# Your public key has been saved in /Users/you/.ssh/id_rsa.pub.
# The key fingerprint is:
# 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db 
your-email@example.com
```
### Step 3: 

SSH - agent is your ssh key manager, its job I mentioned above.
- Make sure that ssh-agent is enabled with the command:
```
eval "$(ssh-agent -s)"
# Agent pid 59566
```
- Add your ssh key to the ssh-agent
```
ssh-add ~/.ssh/id_rsa
```
### Step 4: 
Copy the ssh key to the clipboard:
```
pbcopy < ~/.ssh/id_rsa.pub
```
 - Then go to your account, go to settings, go to Add ssh key and paste the content you copied earlier:

![](https://jdblischak.github.io/2014-09-18-chicago/novice/git/img/github-add-ssh-key.png)


>**OK, at this point you can already use the ssh link.**

## **GOODLUCK AND THANK YOU FOR READING**






