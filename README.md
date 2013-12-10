# Scalable Bloom Filters

Bloom Filters provide space-efficient storage of sets at the cost of a
probability of false positives on membership queries. The size of the filter
must be defined a priori based on the number of elements to store and the
desired false positive probability. Scalable Bloom Filters are a variant of
Bloom Filters that can adapt dynamically to the number of elements stored, while
assuring a maximum false positive probability. Scalable Bloom Filters are
described in the [paper](http://gsd.di.uminho.pt/members/cbm/ps/dbloom.pdf):

    Scalable Bloom Filters
    Paulo Sérgio Almeida, Carlos Baquero, Nuno Preguiça, David Hutchison
    Information Processing Letters
    Volume 101, Issue 6, 31 March 2007, Pages 255-261 

## Implementation in Erlang

An implementation in Erlang (module [bloom.erl](https://github.com/haslab/Scalable-Bloom-Filters/blob/master/bloom.erl)), which provides both Bloom
Filters (partitioned variant) and Scalable Bloom Filters.

This module assumes the existence of a module called bitarray so that different
alternatives may be provided. Two examples of module bitarray are shown, one
with update in-place using hipe_bifs (very efficient): [bitarray.erl-hipe_bifs](https://github.com/haslab/Scalable-Bloom-Filters/blob/master/bitarray.erl-hipe_bifs), and a purely functional
in the spirit of Erlang using the array module: [bitarray.erl-array](https://github.com/haslab/Scalable-Bloom-Filters/blob/master/bitarray.erl-array).

The implementation uses bit arrays dimensioned as a power of 2 to enable reusing
hash values across filters through bit operations. Double hashing is used (no
need for enhanced double hashing for partitioned bloom filters). Overall it
should be a quite efficient implementation, specially when using hipe_bifs
bitarrays.

