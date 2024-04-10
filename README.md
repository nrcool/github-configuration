# Install and setup git

Install command:  `sudo apt install git -y`

## [](https://github.com/nrcool)Setup Git

1.  Set your username:  `git config --global user.name 'your username here'`
2.  Set your email address:  `git config --global user.email 'your email here'`

## [](https://github.com/nrcool)Setup SSH authentication

1.  Generate an ssh key:  `ssh-keygen -t ed25519 -C "your_email@example.com"`  This creates a new SSH key, using the provided email as a label. When you’re prompted to:  `"Enter a file in which to save the key,"`  press Enter. This accepts the default file location. At the prompt, to type a secure passphrase, press enter for no passphrase. If you want to use a passphrase, go ahead as it provides an extra layer of security. However, for this course you do not need to add a passphase.
    
2.  Use the following command to see your public ssh key:  `cat ~/.ssh/id_ed25519.pub`  copy the entire output of this command to the clipboard. See examle here:
    
3.  In your github page, go to  `settings`  >  `SSH and GPG Keys`  Here add your ssh key that you copied to the clipboad in the step prior. Type  `yes`  (the whole word) and press enter and you are done
    
4.  Test you ssh connection by using this command:  `ssh -T git@github.com`  You will see the following outcome:
    

> If you do not see an error message or a different message than the one shown prior, then your SSH connection is correct. Now you can push and clone using SSH.


```important``` 

!!! After setting up 2 Factor Authentication on GitHub, I couldn’t push my remote repositories from the command line anymore.

!!! When I tried to push a remote repo, the command line threw this error:

```bash
~ :> git push origin my-branch  
Username for '[https://github.com](https://github.com/)':
myusernamePassword for '[https://myusername@github.com':](https://ginnyfahs@github.com'/) 
mypasswordremote: Invalid username or password.fatal: Authentication failed for '[https://github.com/my-repository](https://github.com/repository-name)’

``` 

The error stumped me — and made me vow that, when I did ultimately get to the bottom of it, I’d do my best to pay the knowledge forward.

# How to Authenticate on GitHub with 2FA

Command line authentication requires a personal access token.

Go to Settings:

![](https://miro.medium.com/v2/resize:fit:700/1*msyCH1amQUU75QFbrhqvIA.png)

Then Developer Settings:

![](https://miro.medium.com/v2/resize:fit:700/1*m6EQSNjnkpYXZvoIf0TRrg.png)

Then Personal access tokens >> Tokens (classic):

![](https://miro.medium.com/v2/resize:fit:700/1*R8xrWzTb02ur3GJNIGT-zg.png)

Generate a new Personal Access Token (also classic). Make sure you copy the Personal Access Token as soon as it gets generated — you won’t be able to see it again!

![](https://miro.medium.com/v2/resize:fit:700/1*bi9qdbUZ9I2Q3uxGEND12Q.png)

Paste the Personal Access Token into the “Password” field when you authenticate via the command line.

![](https://miro.medium.com/v2/resize:fit:700/1*64UoBJrnazo8FZDJ4SGS8w.png)