# cute\_libs

**cute\_libs** is a FiveM Lua & React library — inspired by ox\_lib but built from scratch with a cleaner API and a modern NUI layer.

---

## Features

* Shared utilities for Lua scripts (print, table, string, math, callbacks)
* Client-side NUI notifications with a modern NP4/ProdigyRP-inspired design
* Client-side 2D/3D text drawing
* Server-side player helpers
* Zero external Lua dependencies — just drop it in and go

---

## Quick Start

Add the following to your script's `fxmanifest.lua`:

```lua
shared_scripts {
    '@cute_libs/init.lua',
}
```

That's it. All `Cute.*` functions are now available in your script on both client and server.
