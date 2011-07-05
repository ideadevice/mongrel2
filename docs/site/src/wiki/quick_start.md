Getting Started With Mongrel2
=============================

This is the fastest way to get started with Mongrel2.  Nothing is really
explained, just all the stuff you need is setup and you get to run a few
commands.  If you want very good explanations for all of this, go read [The
Mongrel2 Manual](http://mongrel2.org/static/mongrel2-manual.html) a complete
manual covering everything from getting started, to writing your first
handlers.

This getting started assumes you know what you're doing and can run commands in Unix.

Building The Dependencies
=========================

<p>Here's how I might do it on ArchLinux:</p>

<pre>
# install ZeroMQ 
wget http://www.zeromq.org/local--files/area:download/zeromq-2.1.4.tar.gz 
tar -xzvf zeromq-2.1.4.tar.gz 
cd zeromq-2.1.4/ 
./configure 
make 
sudo make install 
 
# install sqlite3 
sudo pacman -S sqlite3 
</pre>


<h1>Getting The Source</h1>

<p>Quickest way to do that is to grab the tar.bz2 file:</p>

<pre>
wget http://mongrel2.org/static/downloads/mongrel2-1.6.tar.bz2
</pre>


<h1>Building Mongrel2</h1>

<p>Now you need to build mongrel2:</p>

<pre>
tar -xjvf mongrel2-1.6.tar.bz2
cd mongrel2-1.6/
make clean all && sudo make install
</pre>

<p>The version number for your directory might be different since we 
update it frequently.</p>


<h1>Configuring The First Time</h1>

<p>Now you can try out the simplest config example and get it running:</p>

<pre>
cp examples/configs/sample.conf mysite.conf
m2sh load -config mysite.conf
ls config.sqlite
</pre>

<p><b>NOTE:</b>There's also other examples in examples/*.conf.</p>

<h1>Running Mongrel2</h1>

<p>Now you can run this and try it.  Make sure you're still in the mongrel2 source directory:</p>

<pre>
mkdir run logs tmp
m2sh start -host localhost
</pre>

<p>From another window do:</p>

<pre>
curl http://localhost:6767/tests/sample.html
hi there
</pre>


<h1>Shutting Down</h1>

<p>Just do CTRL-C and it'll exit.  <b>m2sh</b> has many other commands and some of them
shut things down or restart.  Run <b>m2sh help</b> to find out more.
</p>


<h1>Learn More From The Manual</h1>

<p>That is the fastest crash course you can get in running Mongrel2.  You
should now go read <a href="http://mongrel2.org/static/mongrel2-manual.html">The Mongrel2 Manual
 (HTML)</a> which we took much more time writing and making very nice for
you.</p>
