idas blue is a peer-to-peer messaging system with end-to-end encryption.
====

## peer-to-peer messaging
posts are synchronized over [bittorrent sync](http://labs.bittorrent.com/experiments/sync.html), but really any peer-to-peer protocol would work. some open-source thing, mesh network, whatever.

## end-to-end encryption
posts are encrypted from the moment the sender hits the "send" button to the moment the reciever enters some password in her browser. posts are decrypted in the web-browser using [javascript](http://crypto.stanford.edu/sjcl/), so it's unlikely that posts are ever stored permanently in plaintext.

## trust in a trustless network
idas-blue is a fork of [Vole](http://vole.cc), which is popular among some Chinese activists (bittorrent gets around the great firewall). however, vole stores posts as plaintext, so anyone with a follower's address can read all of their posts. so, if you only want three people reading your communications, you're going to have a tiny network with not a lot of resiliance.

with idas-blue, you can disseminate your posts to a public network, letting untrusted peers propagate and distribute your files in a p2p fashion. only peers with the right password will be able to read your posts.

## researchily  
this project is primarily concerned with implementing "permissions" in a largely-distributed public-key cryptosystem.

# how it works
You follow people at "addresses." So it's kind of like twitter. But there are no length limits.

Posts are written in Markdown.

When you follow someone, you may get posts that are unencrypted, but you will probably get posts that appear blacked out. These posts are encrypted. You can enter a password at the top of your feed to decrypt them. 

Note that each post can have its own password - if you can decrypt *some* of your friend's posts but not *all* of them, he is probably giving different passwords to different people. 

![FAQ](http://24.media.tumblr.com/18dbcae01145a71c36a34119928118d3/tumblr_mvph2tSZbf1rvbr3mo1_400.gif)

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
