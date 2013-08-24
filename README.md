bm
==

bm is a shell bookmark script adapted from a page on [jeroen janssens' website](http://jeroenjanssens.com/2013/08/16/quickly-navigate-your-filesystem-from-the-command-line.html).

I thought it might work well to add a different pattern to the commands and worked them around a little.

make a bm
---------
<pre>
$ cd /some/very/deep/often-used/directory
# uses basename of ${PWD} as a default
$ bm
directory  ->  /some/very/deep/often-used/directory
# otherwise, uses whatever first word you provide
$ bm deep
deep ->  /some/very/deep/often-used/directory
</pre>

list bms
--------
<pre>
$ bml
deep       ->  /some/very/deep/often-used/directory
directory  ->  /some/very/deep/often-used/directory
</pre>

remove a bm
---------------
<pre>
$ bmr directory
removed '${BMPATH}/.bm/directory'
</pre>

cd to a bm
----------
<pre>
bmc deep
</pre>
