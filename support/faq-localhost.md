
Due to the way we handle network configuration on boxes, you will not be able to bind http servers to localhost (127.0.0.1)

Your application will need to run on 0.0.0.0 or a specific IP address. Listening on port 3000 will allow you to use our preview menu for a shortcut.

### Node example

Setting up a hello world web server on port 3000 using node.js.

    var http = require('http');

    http.createServer(function (req, res) {
      res.writeHead(200, {'Content-Type': 'text/plain'});
      res.end('Hello World\n');
    }).listen(3000, '0.0.0.0');

    console.log('Server running at http://0.0.0.0:3000/');

### Previewing the app

We supply some sensible default ports to enable you to preview your work in the browser. You can get your preview link in 1 of 2 ways:

1. Launch the Web IDE for your box, click the "Preview" menu and select the port where your web server is running.

![Preview Menu](https://raw.github.com/action-io/action-assets/master/support/screenshots/preview-menu.png)

2. In your list of boxes, click the box name to toggle it's details, copy the Preview URL and paste it in your browser. Change the port to 3000 or the applicable port where your server is running.

![Box Preview URL](https://raw.github.com/action-io/action-assets/master/support/screenshots/box-preview-url.png)