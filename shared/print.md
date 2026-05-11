# Print

Pretty-print utilities for the server/client console. Available on both **client** and **server**.

---

## Cute.Print

Print a message to the console with an optional color.

```lua
Cute.Print(msg, color)
```

**Parameters**

| Name    | Type   | Default | Description                                                              |
| ------- | ------ | ------- | ------------------------------------------------------------------------ |
| `msg`   | string | —       | The message to print                                                     |
| `color` | string | `white` | Color name: `white`, `red`, `green`, `yellow`, `blue`, `cyan`, `purple`, `orange` |

**Example**

```lua
Cute.Print('Hello world!', 'cyan')
```

---

## Cute.PrintSuccess

Print a **green** success message.

```lua
Cute.PrintSuccess(msg)
```

```lua
Cute.PrintSuccess('Resource started successfully.')
```

---

## Cute.PrintWarn

Print a **yellow** warning message. Automatically prefixes `[WARN]`.

```lua
Cute.PrintWarn(msg)
```

```lua
Cute.PrintWarn('Config value missing, using default.')
```

---

## Cute.PrintError

Print a **red** error message. Automatically prefixes `[ERROR]`.

```lua
Cute.PrintError(msg)
```

```lua
Cute.PrintError('Database connection failed.')
```

---

## Cute.PrintInfo

Print a **cyan** info message. Automatically prefixes `[INFO]`.

```lua
Cute.PrintInfo(msg)
```

```lua
Cute.PrintInfo('Player connected: John')
```

---

## Cute.Dump

Recursively print every key/value in a table to the console. Useful for debugging.

```lua
Cute.Dump(tbl, label)
```

**Parameters**

| Name    | Type   | Default  | Description               |
| ------- | ------ | -------- | ------------------------- |
| `tbl`   | table  | —        | The table to dump         |
| `label` | string | `"Dump"` | Optional label in header  |

**Example**

```lua
local data = { name = 'John', age = 25, job = { name = 'police' } }
Cute.Dump(data, 'Player Data')
```
