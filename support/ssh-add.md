You can use SSH Keys to manage your boxes directly from your local machine.  The steps listed below will help you generate a new SSH key and add the key to your Action.IO account.  

If you have an existing SSH keypair you want to use you can skip down to step 4. 

### 1. Check to see if you have existing SSH Keys

Open up terminal:

    cd ~/.ssh
    # Checks to see if there is a directory named ".ssh" in your user directory

If the terminal prompt says "No such file or directory" you can move to 3.) Otherwise go to 2.)

### 2. Backup and remove existing SSH keys

You already have an SSH directory so you'll want to back the old one up and delete it:

    ls
    # Lists all the subdirectories in the current directory
    # config  id_rsa  id_rsa.pub  known_hosts

    mkdir key_backup
    # Makes a subdirectory called "key_backup" in the current directory

    cp id_rsa* key_backup
    # Copies the id_rsa keypair into key_backup

    rm id_rsa*
    # Deletes the id_rsa keypair

### 3: Generate your new SSH key

To generate a new SSH key, enter the code below. We want the default settings so when asked to enter a file in which to save the key, just press enter.

    ssh-keygen -t rsa -C "your_email@youremail.com"
    # Creates a new ssh key using the provided email

    # Generating public/private rsa key pair.
    # Enter file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]

Now you enter a passphrase (passphrases make things much more secure). 

    # Enter passphrase (empty for no passphrase): [Type a passphrase]
    # Enter same passphrase again: [Type passphrase again]
    Which should give you something like this:

    # Your identification has been saved in /Users/you/.ssh/id_rsa.
    # Your public key has been saved in /Users/you/.ssh/id_rsa.pub.
    # The key fingerprint is:
    # 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@youremail.com

### 4: Add your SSH key to Action.IO

Run the following code to copy the key to your clipboard.

    pbcopy < ~/.ssh/id_rsa.pub
    # Copies the contents of the id_rsa.pub file to your clipboard

*** Make sure you copy the key _exactly_ without newlines or whitespace. The pbcopy command helps copy just the contents with no extraneous characters. ***

* Login to your Action.IO account 
* Click "Public Keys" in the top right navigation
* Click the "Add Public key" button
* Add a name for the key e.g. "AJ's MBA"
* Paste your key into the "Key" field
* Click "Add key"

### 5. Make sure it works!

To make sure everything works we'll now SSH into your box. You'll be asked to authenticate this action using your password, which is the passphrase you created earlier. 

    ssh -T ssh@action.io
    # Attempting to ssh to action

You may see this warning:

    # The authenticity of host 'action.io ()' can't be established.
    # RSA key fingerprint is 12:24:ac:35:41:9k:36:49:ac:ee:e9:98.
    # Are you sure you want to continue connecting (yes/no)?
   
Don't worry, this is supposed to happen. Verify that the fingerprint matches the one here and type "yes".

    # Hi username! You've successfully authenticated, but Action.IO does not
    # provide shell access.

If that username is correct, you've successfully set up your SSH key. Don't worry about the shell access thing, you don't want that anyway.

If you see "access denied" please consider using HTTPS instead of SSH. If you need SSH start at these instructions for diagnosing the issue.