---
layout: post
title: "Installing node.js on the Raspberry Pi"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Most of the time you use a package manager to download and install software on your system. This saves time as you don't need to compile the source code: it has already been done for you.

The Raspberry Pi, however, is quite a new platform and therefore some software is not available yet via a package manager such as apt-get. However, you can still download the source code and compile it yourself.

I spend a lot of time looking for a precompiled node because there are some horror stories about how difficult it all is. In the end, I just tried it and it went flawlessly. Apparently some brave souls have already cleared the path for us. So here is a few instructions on how to compile it.

Note that this does take a while - about an hour on my Pi - as the cpu is not that powerful.

# Downloading the source code
At the time of being, this was the latest. But check the official site for the current version

wget http://nodejs.org/dist/v0.8.16/node-v0.8.16.tar.gz

# Unpack it
tar xvf node-v0.8.16.tar.gz 

# Build it
cd node-v0.8.16/
./configure
make

# Optionally: run the tests
make test

Some tests failed for me - a known issue on the RPi.

# Install it on your system
sudo make install

# Verify that it works
node -v

# Start developing an application :)
