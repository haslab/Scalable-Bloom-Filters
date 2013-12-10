-module(bitarray).
-export([new/1, set/2, get/2]).

-define(W, 24).

new(N) -> array:new((N-1) div ?W + 1, {default, 0}).

set(I, A) ->
  AI = I div ?W,
  V = array:get(AI, A),
  V1 = V bor (1 bsl (I rem ?W)),
  array:set(AI, V1, A).

get(I, A) ->
  AI = I div ?W,
  V = array:get(AI, A),
  V band (1 bsl (I rem ?W)) =/= 0.

