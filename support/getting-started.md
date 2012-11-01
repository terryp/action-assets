Welcome to Action.IO. 

Our goal at Action.IO is to provide a streamlined, beautiful and, enjoyable programming experience. 

So, let's get started, shall we? If you have any problems setting things up, check out [help.action.io](http://help.action.io) or send us an email at support at action dot io.  

1. Sign Up for an Account

Our beta period is invite-only, so if you haven't received an invite, you can signup for our beta list on our [homepage](https://action.io).  

If you've received the beta invite email, just click the link in the email and fill out a username and password.  We'll use the username around the site and to identify your boxes so pick something you like. 

2. Create a box

Once you've signed in to the site, you'll see your dashboard. You won't have any boxes created yet, so go ahead and click "New Box". If you need help creating a box, you can follow [these instructions](http://help.action.io/customer/portal/articles/802603-create-a-box).  

3. Adding SSH Keys to your Action Box

Adding your local SSH keys to your remote Action box will allow you to SSH into your box from Terminal / PuTTY etc…. This is great for developers who use Vim or Emacs. 

If you're not already using SSH, this article can walk you through the steps required:

[Adding SSH Keys to your Action.IO Account](http://help.action.io/customer/portal/articles/802633-add-ssh-keys-to-your-action-io-account)

To test out whether you've added your keys directly, click your box in the dashboard to toggle its details and click the SSH URI link:

You should see something like this:

	The authenticity of host '[apse1.actionbox.io]:10253 	([54.251.42.128]:10253)' can't be established.
	RSA key fingerprint is 57:b7:dd:50:04:09:e8:f8:e5:93:e1:2d:2f:46:a5:f5.
	Are you sure you want to continue connecting (yes/no)? yes

Type "yes", which will add your Action box to your known_hosts ssh file.	

Warning: Permanently added '[apse1.actionbox.io]:10253,	[54.251.42.128]:10253' (RSA) to the list of known hosts.
	Welcome to Action.IO (GNU/Linux 3.2.0-31-virtual x86_64)

4. Add Action Box SSH Keys to Github

So we've got our development box built, but what if we want to get a project we've been working on into our box on Action?  

For this, you'll need to just add your Action box SSH keys to Github just like you would with your own development machine. You'll need to either:

a. SSH into your Action.IO box
b. Open the box IDE and use the in-browser console at the bottom of the IDE. 

If you need help generating your SSH keys on your action box you can refer again to [this article](http://help.action.io/customer/portal/articles/802633-add-ssh-keys-to-your-action-io-account). 

Now that we've got SSH keys on our Action box, we just need to add them to Github so we can interact with Github easily.  

* [Login to Github](https://github.com/login) or [create a free account](https://github.com/signup/free)
* Click **Account Settings** on the top right menu
* Click **SSH Keys** on the left menu
* Click **Add SSH Key** on the top right of the list of keys
* Then just paste your Action.IO SSH key and give the key a name "Action-Rails" or something appropriate. 

Now, you can go back to your Action.IO box in your local terminal or in the Action.IO Web IDE and can clone the Github repo of your choice:

[Now you rollin'](http://www.youtube.com/watch?v=CtwJvgPJ9xw&t=0m14s).  