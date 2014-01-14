Idas Blue
====

## Introduction
Posts are synchronized over [BitTorrent](http://labs.bittorrent.com/experiments/sync.html). Posts are encrypted from the moment the sender hits the "send" button to the moment the reciever enters some password in her browser. 

Everything's peer-to-peer, so there's **no need for servers** or any other centralized infrastructure. Because everything's encrypted, you can safely distribute your data to strangers to give it resilliance/redundancy. Posts are **decrypted in the web-browser** using [Javascript](http://crypto.stanford.edu/sjcl/), so it's unlikely that posts are ever stored permanently in plaintext.

Right now posts are simply text, but imagine a distributed Megaupload/Rapidshare in which you can browse (decrypted) content like youtube/flickr/soundcloud/tumblr/twitter/rss reader. In theory you could share any kind of media and Idas Blue would wrap it into a browsable webpage.

## Privacy and deniability
Idas Blue is a fork of [Vole](http://vole.cc), which is popular among some Chinese political activists (BitTorrent gets around the so-called great firewall of China). However, Vole stores posts as plaintext, so anyone with a user's address can read all of their posts. This is not ideal for adversarial conditions. If you only want three people reading your communications, you'll have a tiny network with not a lot of redundancy or resiliance.

With Idas Blue, **you can disseminate your posts widely to an untrusted network**, letting (theoretically) any stranger propagate and distribute your files in a p2p fashion. only peers with the right password will be able to read your communications.

## Future plans
- BitTorrent Sync is closed-source and has no API. This means people have to use its interface for following people - we want all that to be integrated. We could replace this with any peer-to-peer protocol would work. [telehash](http://telehash.org/), [some other mesh network](http://hyperboria.net/), whatever.
- Idas doesn't handle non-text very well. We could sync any kind of file, so Idas should display or link to those files in the browser. Like a tumblr of bittorrented content.
- Users need to download a client to view vole. Any way around this? Elegant implementation for android/iOS (really just a matter of generating static HTML and displaying it in a browser).

Getting started
---------------

Read "contrib.md." For now you need to install [Bittorrent Sync](http://labs.bittorrent.com/experiments/sync.html) separately.

Following others
----------------

* Grab the **read-only** ID of the person you want to follow. A directory is in progress at [vole.cc](http://vole.cc). Why not start with Vole Team updates? Our key is RA32XLBBHXMWMECGJAJSJMMPQ3Z2ZGR7K.
* Find the Idas Blue `users` folder. Unless you changed the defaults, it will be in a directory called `idas-blue/users` in your home folder.
* Create a new folder in `idas-blue/users`, you should name it after the user that you're about to follow. For example, `idas-blue/users/voleteam`.
* In BitTorrent Sync, add this new folder as a shared folder, using the read-only key you grabbed in step 1. [Instructions](http://labs.bittorrent.com/experiments/sync/get-started.html) are available on their site and vary a little by operating system.
![OSX Screenshot](https://f.cloud.github.com/assets/453297/692312/c113737a-dc18-11e2-84e4-dee7e0507c08.png)
* You should receive notification that the folder has sync'd.
* In your browser, see the new posts appear.

Sharing your posts
------------------

Find your own user folder, for example, if you created a profile named 'Chuck':

    /home/chuck/idas-blue/users/Chuck_9674e8e8-7c7a-41e6-52ed-51a3f7969812

* In Bittorrent Sync, add this folder as a shared folder.
* In the folder options, grab the **read-only key**. Make sure the key starts with the letter 'B' that signifies it's the read-only one. You can find it by going to the advanced folder preferences. This is the key that you can share with others so they can follow your posts.
* Posts are written in Markdown.

Configuration
-------------

To override the default configuration options, make a copy of `config.sample.json` and name it `config.json`.

Change the `server.listen` value to `0.0.0.0:6789` to listen for requests from any network device, instead of just the local machine.

Technology
----------

* [stanford javascript crypto library](http://crypto.stanford.edu/sjcl/) (but go bears)
* [bittorrent sync](http://labs.bittorrent.com/experiments/sync.html)
* [Vole](http://vole.cc)
* [Go](http://golang.org/)
* [Ember.js](http://emberjs.com/)

License
-------

all Vole code copyright (C) 2013 Vole development team  
all Idas Blue code copyright (c) 2014 http://cosmopol.is

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
