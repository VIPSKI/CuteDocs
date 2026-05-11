# Player

Server-side player utility functions. **Server only.**

---

## Cute.Player.getName

Get a player's display name.

```lua
Cute.Player.getName(source)
```

| Name     | Type    | Description     |
| -------- | ------- | --------------- |
| `source` | integer | Player source   |

**Returns:** `string`

```lua
local name = Cute.Player.getName(source)
print(name) -- 'John'
```

---

## Cute.Player.getIdentifiers

Get all identifiers for a player as a key/value table.

```lua
Cute.Player.getIdentifiers(source)
```

**Returns:** `table`

```lua
local ids = Cute.Player.getIdentifiers(source)
print(ids.steam)   -- 'steam:110000112345678'
print(ids.license) -- 'license:abc123...'
print(ids.discord) -- 'discord:123456789'
```

---

## Cute.Player.getIdentifier

Get a single specific identifier type for a player.

```lua
Cute.Player.getIdentifier(source, identType)
```

| Name         | Type    | Description                                  |
| ------------ | ------- | -------------------------------------------- |
| `source`     | integer | Player source                                |
| `identType`  | string  | Type: `'steam'`, `'license'`, `'discord'`, etc. |

**Returns:** `string | nil`

```lua
local license = Cute.Player.getIdentifier(source, 'license')
print(license) -- 'license:abc123...'
```

---

## Cute.Player.getPing

Get a player's current ping in milliseconds.

```lua
Cute.Player.getPing(source)
```

**Returns:** `integer`

```lua
local ping = Cute.Player.getPing(source)
print(ping) -- 42
```

---

## Cute.Player.getEndpoint

Get a player's IP address (endpoint).

```lua
Cute.Player.getEndpoint(source)
```

**Returns:** `string`

```lua
local ip = Cute.Player.getEndpoint(source)
print(ip) -- '127.0.0.1:30120'
```

---

## Cute.Player.kick

Kick a player from the server with an optional reason.

```lua
Cute.Player.kick(source, reason)
```

| Name     | Type    | Default                 | Description    |
| -------- | ------- | ----------------------- | -------------- |
| `source` | integer | —                       | Player source  |
| `reason` | string  | `'Kicked by server.'`   | Kick reason    |

```lua
Cute.Player.kick(source, 'You have been banned.')
```

---

## Cute.Player.getAll

Get a list of all currently connected player sources.

```lua
Cute.Player.getAll()
```

**Returns:** `table` — array of integer source IDs

```lua
local players = Cute.Player.getAll()
for _, src in ipairs(players) do
    print(Cute.Player.getName(src))
end
```

---

## Cute.Player.isConnected

Check if a player source is currently connected.

```lua
Cute.Player.isConnected(source)
```

**Returns:** `boolean`

```lua
if Cute.Player.isConnected(source) then
    print('Player is still online')
end
```
