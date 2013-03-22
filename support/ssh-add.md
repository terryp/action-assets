SSH Keys enable you to manage your Action boxes directly from your computer.  The keypair is used to identify you when interacting with your box from outside of the website.

<ul class="inline choices">
  <li class="selected">Mac</li>
  <li><a href="http://help.action.io/customer/portal/articles/1034948-add-ssh-keys-to-action-io-windows-xp-">Windows</a></li>
</ul>

### 1: Generate a public key

On your **personal computer** enter the code below. We want the default settings so when asked to enter a file in which to save the key, just press enter.

    ssh-keygen -t rsa -C "your_email@youremail.com"
    # Creates a new ssh key using the provided email

    # Generating public/private rsa key pair.
    # Enter file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]

*Note* In the case you already have ssh keys on your machine, you should consider saving your key to a different file *not* `id_rsa`. For example:

    ssh-keygen -t rsa -C "your_email@youremail.com" -f ~/.ssh/action_io_rsa
    # Creates a new ssh key and saves in your local .ssh folder
    
    # Generating public/private rsa key pair.

Now you enter a passphrase (passphrases make things more secure).

    # Enter passphrase (empty for no passphrase): [Type a passphrase]
    # Enter same passphrase again: [Type passphrase again]
    Which should give you something like this:

    # Your identification has been saved in /Users/you/.ssh/id_rsa.
    # Your public key has been saved in /Users/you/.ssh/id_rsa.pub.
    # The key fingerprint is:
    # 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@youremail.com

### 2: Adding keys to Action.IO

Run the following code to copy the key to your clipboard.

    pbcopy < ~/.ssh/id_rsa.pub
    # Copies the contents of the id_rsa.pub file to your clipboard

** Make sure you copy the key _exactly_ without newlines or whitespace. The pbcopy command helps copy just the contents with no extraneous characters. **

If you don't have the pbcopy command, copy the output of the following command:

    cat ~/.ssh/id_rsa.pub

Next, Login to your Action.IO account and click "Public Keys" in the top right navigation.  You shouldn't have any keys listed if this is the first key you are adding. Click the "Add Public key" button:

![Public Key Button](https://raw.github.com/action-io/action-assets/master/support/screenshots/add-public-key-button.png)

Next, add a name for the SSH key e.g. "AJ's MBA".  This is helpful to identify which machines you've given access to your action boxes, so make it descriptive.

Then, paste your key into the "Key" field that you copied in section 2. of the article and click the "Add key".

![Public Key Form](https://raw.github.com/action-io/action-assets/master/support/screenshots/public-key-form.png)

### 3. Make sure it works

To make sure everything works we'll now SSH into your box. You'll be asked to authenticate this action using your password, which is the passphrase you created earlier.

Click the "boxes" link in the top navigation.  Then click any box you've created to expand its details:

![Box Details](https://raw.github.com/action-io/action-assets/master/support/screenshots/box-details.png)

Click the SSH URI link, it should look something like the link in the screenshot above.

Your browser will attempt to open a local terminal session. If there's a prompt like this, just click "Allow":

![SSH Prompt](https://raw.github.com/action-io/action-assets/master/support/screenshots/ssh-confirm-prompt.png)

In your terminal, you might see something like this:

    The authenticity of host '[apse1.actionbox.io]:10253    ([54.251.42.128]:10253)' can't be established.
    RSA key fingerprint is 57:b7:dd:50:04:09:e8:f8:e5:93:e1:2d:2f:46:a5:f5.
    Are you sure you want to continue connecting (yes/no)? yes

Don't worry, this is supposed to happen. Verify that the fingerprint matches the one here and type "yes". This will add your Action box to your known_hosts ssh file.

    Warning: Permanently added '[apse1.actionbox.io]:10253, [54.251.42.128]:10253' (RSA) to the list of known hosts.
    Welcome to Action.IO (GNU/Linux 3.2.0-31-virtual x86_64)

Now you've got your SSH keys setup so you can connect via Terminal / PuTTY and use Vim or Emacs to code!
