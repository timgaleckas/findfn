# findfn

This thing can help you find other things!

Basically, what it does is take input arguments and an expected output, and it tries out every function and macro in a set of namespaces, collecting the names of the ones that produce the output for the input arguments passed. Here are some examples:

```clojure
user=> (use 'findfn.core)
nil
user=> (use '[clojail.testers :only [secure-tester] :rename {secure-tester tester}])
nil
user=> (find-fn tester 6 3 3) ; 6 is the expected output and the 3s are the input
(clojure.core/+ clojure.core/unchecked-add clojure.core/+' clojure.core/unchecked-add-int)
user=> (find-arg tester [2 3 4] map '% [1 2 3]) ; Finds a function to pass to a higher order function
(clojure.core/unchecked-inc-int clojure.core/unchecked-inc clojure.core/inc clojure.core/inc')
```

## Usage

   [findfn "0.1.0"]

## License

Copyright (C) 2011 [Joshua Cole](https://github.com/jColeChanged), [Alan Malloy](https://github.com/amalloy), [Anthony Grimes](https://github.com/Raynes)

Distributed under the Eclipse Public License, the same as Clojure.
