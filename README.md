Demo system of TheSteakProject
===

This is the demo (client and server configuration) for the _3D Audio_ voice conferencing system implemented in [the STEAK project](www.steakconferencing.de).

## Client
The client is implemented in HTML5, CSS3, and JavaScript and connects via WebRTC to the voice conferencing system.
It just provides basic functionality as it can register at the conferencing system and join a conference.

The client uses [SIP.js](http://sipjs.com/) for communication with the voice conferencing (based upon [Asterisk](www.asterisk.org)).
In general, it can be used with any [SIP.js](http://sipjs.com/)-compatible conferencing system.

__ATTENTION__: This software was only tested in Google Chrome/Chromium while using state-of-the-art (standardized but under development) web technologies.
As web browser differ in their implementation status as well as their interpretation and acceptance of standards, the client might not work correctly in other web browsers.

Nevertheless, this software does _only_ use standardized technologies.
Web browser-specific functionalities (including prefixes) are not used.

### Configuration

The client is preconfigured for the STEAk conferencing demo available at [demo.steakconferencing.de](http://demo.steakconferencing.de).
If you want to use your own server, you need to adjust the parameters according to your configuration:

`new Client("WEBSOCKET-URL", "DOMAIN", "USERNAME", "PASSWORD");`

If you want to use different DTMF-codes for interaction while in a conference (e.&thinsp;g., 3D audio: on/off), you need to modify all lines using the function `this.session.dtfm()` accordingly.


### Resources
headphones.{wav, opus, mp3} are based upon the [ALSA](http://www.alsa-project.org/) files `front_left.wav` and `front_right.wav`.

## Server configuration files
In addition, this repository contains all necessary configuration files required to start the demo system.
The server will provide allow clients that connect as user _101_ with password _101_ to join conference rooms.
In addition, it will try to connect to a SIP provider enabling incoming calls via PSTN.

This repository also includes required but outdated SSL certifications.

For how to install the server see into the [Wiki](https://github.com/SteakConferencing/asterisk/wiki).

__DISCLAIMER:__ The provided configuration cannot be regarded as secure.  
It was just implemented for a demo and not for productive use.  
Please be careful if using this _online_.
