# Installing and Running Node
You should only have to install Homebrew and Node once in your time at EDA. Follow the instructions below.

## Installing Homebrew (Mac OSX) and Node.js (one-time)

1. [Install Homebrew](http://brew.sh/). This will be done on the command line (Terminal)
2. Once Homebrew is installed, run the command: `brew install node`
3. When this is complete, run this at your Terminal: `node --version` If you see a number, you are good to go.

## Installing Node.js (Linux/Ubuntu Only)
You can install NodeJS via [binary distributions](https://github.com/nodesource/distributions/blob/master/README.md#debinstall) or through the [Snap store](https://snapcraft.io/node).

To install via binary distrubtions, you can run these commands from the command line (this is copied from the link above). Run the first line to add the Node repository to apt, then then the second line to actually install `nodejs`.

```
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## Running Code Using Node
In order for our app to run and serve the files we need, you'll need to run Node and point it to our server file. Otherwise we can run any old JS file with Node.

Default method to tell Node to run a JavaScript file: `node /path/to/javascriptFile.js`

For example, put the following into `hello.js`:

``` javascript
console.log('hello world');
```

Then from the command line (in the same folder), execute the script by running: `node hello.js`

### Start Your Server

Typically at EDA we use this to start a web server: `node server/app.js` or `node server/server.js`

### Stopping the Server

In the Terminal window that is running the server, hit the keys Control + C (to Cancel). You will see: '^C'

### HALP! I closed the Terminal window!

If you no longer have a window in which to type `Control + C`, you can stop all node instances on your computer by running this in your terminal: `killall node`
