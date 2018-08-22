# Blync-Node

A simple Node.JS/Javascript example for controlling an [Embrava Blynclight](https://embrava.com/) as a HID (Human Interface Device) object. 

How to use
----------
Assuming you have a current NodeJS installation, you will need to make sure you have the [node-hid](https://github.com/node-hid/node-hid) module installed, and then download the contents of this repository (at a minumum test.js, blync.js, device.js, and package.json) and run the sample <code>node test.js</code>.

To define new Blynclight devices add the <code>dev.productId</code> to the list on line 10 in <code>blync.js</code>

To control the light, see sample code in <code>test.js</code> but essentially you use:

<code>
Blync = require('./blync');
var device = Blync.getDevice(0);
device.sendCommand(r, g, b,dim,blink);
</code>

where:
* <code>r,g,b</code> are the red, green, and blue colours (0-255)
* <code>dim</code> is a true/false value to set the light to full brightness, or dimmed
* <code>blink</code> is set to 0 for steady, 1 for 'slow', 2 for 'medium', and 3 for 'fast' blinking

By default the Blynclight will remain active and in a steady state provided power is maintained, but the <code>test.js</code> sample includes a <code>device.sendCommand</code> to deactivate the light in the exit handler

To Do
----------
* add additional Blynclight devices (maybe Embrava would like to send me some to test!)
* add the musicControl logic
* only supports first Blynclight device it finds, what if there is >1?
* make it all a bit more robust

----------
If you make use of this and like it and want to give something back... [I wrote a book!](http://amzn.to/1SHjbLI) :)

----------

Contribute
----------
This project can be forked from
[Github](https://github.com/Offbeatmammal/blync-node). Please issue pull
requests from feature branches.

License
-------
See Licence file in repo, or refer to http://unlicense.org
