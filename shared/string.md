# String

String utility functions. Available on both **client** and **server**.

---

## Cute.String.trim

Remove whitespace from both ends of a string.

```lua
Cute.String.trim(str)
```

**Returns:** `string`

```lua
print(Cute.String.trim('  hello world  ')) -- 'hello world'
```

---

## Cute.String.split

Split a string into an array table by a separator character.

```lua
Cute.String.split(str, sep)
```

| Name  | Type   | Description        |
| ----- | ------ | ------------------ |
| `str` | string | Source string      |
| `sep` | string | Separator character |

**Returns:** `table`

```lua
local parts = Cute.String.split('a,b,c', ',')
-- parts = { 'a', 'b', 'c' }
```

---

## Cute.String.startsWith

Check if a string starts with a given prefix.

```lua
Cute.String.startsWith(str, prefix)
```

**Returns:** `boolean`

```lua
print(Cute.String.startsWith('Hello world', 'Hello')) -- true
```

---

## Cute.String.endsWith

Check if a string ends with a given suffix.

```lua
Cute.String.endsWith(str, suffix)
```

**Returns:** `boolean`

```lua
print(Cute.String.endsWith('image.png', '.png')) -- true
```

---

## Cute.String.contains

Check if a string contains a substring.

```lua
Cute.String.contains(str, sub)
```

**Returns:** `boolean`

```lua
print(Cute.String.contains('FiveM server', 'Five')) -- true
```

---

## Cute.String.titleCase

Convert a string to title case (first letter of each word capitalised).

```lua
Cute.String.titleCase(str)
```

**Returns:** `string`

```lua
print(Cute.String.titleCase('hello world')) -- 'Hello World'
```

---

## Cute.String.padLeft

Pad a string on the left side to reach a target length.

```lua
Cute.String.padLeft(str, len, char)
```

| Name   | Type    | Default | Description               |
| ------ | ------- | ------- | ------------------------- |
| `str`  | string  | —       | Source string             |
| `len`  | integer | —       | Target length             |
| `char` | string  | `' '`   | Character to pad with     |

**Returns:** `string`

```lua
print(Cute.String.padLeft('5', 3, '0')) -- '005'
```

---

## Cute.String.padRight

Pad a string on the right side to reach a target length.

```lua
Cute.String.padRight(str, len, char)
```

**Returns:** `string`

```lua
print(Cute.String.padRight('hi', 5, '.')) -- 'hi...'
```

---

## Cute.String.count

Count how many times a pattern appears in a string.

```lua
Cute.String.count(str, pattern)
```

**Returns:** `integer`

```lua
print(Cute.String.count('banana', 'a')) -- 3
```

---

## Cute.String.replace

Replace all occurrences of a substring (plain text, no patterns).

```lua
Cute.String.replace(str, from, to)
```

**Returns:** `string`

```lua
print(Cute.String.replace('hello world', 'world', 'FiveM')) -- 'hello FiveM'
```
