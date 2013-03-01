Action.IO provides a range of ports [1024 - 9999] for you to run services on your development box. 

Previewing your application simply involves taking an automatically generated <span class="tag">preview url</span>, pasting it into your browser, and appending the appropriate port where your service is running.  

You can find the <span class="tag">preview url</span> from the following two locations:

* [Getting the Preview URL from the Web IDE](#preview-webide)
* [Getting the Preview URL from the Boxes Dashboard](#preview-boxindex")

<a name="preview-webide"></a>
### From the Web IDE

The "Preview" menu in the [Action Web IDE](http://help.action.io/customer/portal/topics/364285-action-web-ide/articles) displays links to some common default ports, which you can click to open a new window in your browser.  

![Preview Menu](https://raw.github.com/action-io/action-assets/master/support/screenshots/preview-menu.png)

You can easily edit the urls from any of those links to preview other services you're running by substituting your desired port.  

<a name="preview-boxindex"></a>
### From the Boxes Dashboard

You'll also find your <span class="tag">preview url</span> in your boxes dashboard in the box-details.  

![Box Dashboard Preview URL](https://raw.github.com/action-io/action-assets/master/support/screenshots/box-preview-url.png)

If you're really smart, you'll notice we use some sensible naming conventions for your box preview url.  The box regions are probably tough to memorize, but regular users will remember it. 

https://*[box-name]*.*[box-region]*.action.io:*[port]*

### Ruby On Rails Example

If you're developing a Ruby on Rails project and using the default WEBrick web server, simply move into the Rails project directory in your console and run:

    rails server

This will fire up an instance of the WEBrick web server by default (Rails can also use several other web servers). To see your application in action, click the "Preview" menu and select "Port 3000". You should see your Rails development project in the new window that is opened.  

### Other Frameworks

For help on previewing applications written in other languages and frameworks, check the following [support article](http://help.action.io/customer/portal/articles/1000558-problems-running-server-on-localhost).

