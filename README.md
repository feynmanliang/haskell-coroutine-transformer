Haskell Coroutine Monad Transformer
===

An implementation of a coroutine monad transformer (`ContT`) using continuations.

`ContT` is built by stacking a Continuation monad transfomer with a State monad transformer.
The State consists of a list of suspended `CoroutineT`s, and every continuation of `ContT`
(invoked through calling `yield`) pops one of the suspended `CoroutineT`s and advances
it by one continuation.
