-module(bitarray).
-export([new/1, set/2, get/2]).

new(Size) -> hipe_bifs:bitarray(Size, false).
set(I, A) -> hipe_bifs:bitarray_update(A, I, true).
get(I, A) -> hipe_bifs:bitarray_sub(A, I).

