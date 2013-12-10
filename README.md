# Scalable Bloom Filters

This repository is based on the following
[paper](http://gsd.di.uminho.pt/members/cbm/ps/dbloom.pdf):

    Scalable Bloom Filters
    Paulo Sérgio Almeida, Carlos Baquero, Nuno Preguiça, David Hutchison
    Information Processing Letters
    Volume 101, Issue 6, 31 March 2007, Pages 255-261 

It provides scalable bloom filters that can grow indefinitely while ensuring a
desired maximum false positive probability. Also provides standard partitioned
bloom filters with a maximum capacity. Bit arrays are dimensioned as a power of
2 to enable reusing hash values across filters through bit operations. Double
hashing is used (no need for enhanced double hashing for partitioned bloom
filters).

This module assumes the existence of a module called *bitarray* so that
different alternatives may be provided. To get an extremely efficient but non-
functional variant, hipe_bifs can be used, defining bitarray as [bitarray.erl-hipe_bifs](https://github.com/haslab/Scalable-Bloom-Filters/blob/master/bitarray.erl-hipe_bifs)

A functional alternative with good lookup performance can be obtained resorting
to the array module. E.g. [bitarray.erl-array](https://github.com/haslab/Scalable-Bloom-Filters/blob/master/bitarray.erl-array)
