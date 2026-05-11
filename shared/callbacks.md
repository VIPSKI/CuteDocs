# Callbacks

A simple callback registry for registering and triggering named functions. Available on both **client** and **server**.

---

## Cute.Callbacks.register

Register a named callback handler.

```lua
Cute.Callbacks.register(name, fn)
```

| Name   | Type     | Description              |
| ------ | -------- | ------------------------ |
| `name` | string   | Unique callback name     |
| `fn`   | function | The function to register |

{% hint style="warning" %}
Registering a callback that already exists will overwrite it and print a warning.
{% endhint %}

```lua
Cute.Callbacks.register('myScript:onDeath', function(source)
    print('Player died:', source)
end)
```

---

## Cute.Callbacks.trigger

Trigger a registered callback by name, passing any arguments along.

```lua
Cute.Callbacks.trigger(name, ...)
```

| Name   | Type   | Description                          |
| ------ | ------ | ------------------------------------ |
| `name` | string | The registered callback name         |
| `...`  | any    | Arguments forwarded to the callback  |

**Returns:** The return value of the callback, if any.

```lua
Cute.Callbacks.trigger('myScript:onDeath', source)
```

---

## Cute.Callbacks.exists

Check if a callback is currently registered.

```lua
Cute.Callbacks.exists(name)
```

**Returns:** `boolean`

```lua
if Cute.Callbacks.exists('myScript:onDeath') then
    print('Callback is registered')
end
```

---

## Cute.Callbacks.remove

Remove a registered callback.

```lua
Cute.Callbacks.remove(name)
```

```lua
Cute.Callbacks.remove('myScript:onDeath')
```
