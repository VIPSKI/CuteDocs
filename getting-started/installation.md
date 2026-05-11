# Installation

## 1. Download

Clone or download **cute\_libs** and place the folder inside your server's `resources` directory:

```
resources/
└── cute_libs/
```

## 2. Start the resource

Add the resource to your `server.cfg`:

```
ensure cute_libs
```

{% hint style="warning" %}
`cute_libs` must be started **before** any resource that depends on it.
{% endhint %}

## 3. Add to your script

In your script's `fxmanifest.lua`, add `@cute_libs/init.lua` as a shared script:

```lua
shared_scripts {
    '@cute_libs/init.lua',
    'client.lua',
    'server.lua',
}
```

All `Cute.*` functions are now available globally on both client and server.

---

## Building the UI

The NUI overlay is pre-built and included in `web/dist/`. If you modify the React source files, rebuild with:

```bash
cd web
npm install
npm run build
```

The output will be placed in `web/dist/` automatically.
