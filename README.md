Unit tested Corona Hello World
==============================

An example of unit testing Corona using [Busted](https://github.com/Olivine-Labs/busted).  You do not need the Corona SDK to run this.  This was not written with TDD, and is not following any seperation of concerns.  I just wanted to provide an example showing that advanced testing methods can be used within Lua for Corona Projects.

I chose [Busted](https://github.com/Olivine-Labs/busted) because the syntax is what I'm used to with BDD style testing suites, and it included mocks and spys from luaunit.

Get it running
==============

On Mac using [Homebrew](http://mxcl.github.com/homebrew/):
```bash
> brew install luarocks
> luarocks install busted
> busted test.lua
```

There should be 2 successes and 0 failures.

Things you need to know
=======================

a function defined like this
```lua
function some.objectFunction (self, param1, param2)
  -- stuff here
end
```

is the same as 

```lua
function some:objectFunction (param1, param2)
 -- stuff here
end
```

Except in my experience you can write tests for the first one but not the second one, because of the way spies work with the busted testing framework.  When using the second method, Lua just takes care of the "self" portion at runtime (at least thats what I'm lead to believe by their documentation)


Links
=====
 * [Busted](https://github.com/Olivine-Labs/busted)
 * [HomeBrew](http://mxcl.github.com/homebrew/)

TODO:
 * Put display mock into its own folder.
