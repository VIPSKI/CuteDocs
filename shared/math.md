# Math

Math utility functions. Available on both **client** and **server**.

---

## Cute.Math.clamp

Clamp a number between a minimum and maximum value.

```lua
Cute.Math.clamp(val, min, max)
```

| Name  | Type   | Description   |
| ----- | ------ | ------------- |
| `val` | number | Input value   |
| `min` | number | Minimum bound |
| `max` | number | Maximum bound |

**Returns:** `number`

```lua
print(Cute.Math.clamp(150, 0, 100)) -- 100
print(Cute.Math.clamp(-5, 0, 100))  -- 0
print(Cute.Math.clamp(50, 0, 100))  -- 50
```

---

## Cute.Math.round

Round a number to a given number of decimal places.

```lua
Cute.Math.round(val, decimals)
```

| Name       | Type    | Default | Description              |
| ---------- | ------- | ------- | ------------------------ |
| `val`      | number  | —       | Value to round           |
| `decimals` | integer | `0`     | Number of decimal places |

**Returns:** `number`

```lua
print(Cute.Math.round(3.7))    -- 4
print(Cute.Math.round(3.145, 2)) -- 3.15
```

---

## Cute.Math.lerp

Linearly interpolate between two values.

```lua
Cute.Math.lerp(a, b, t)
```

| Name | Type   | Description                       |
| ---- | ------ | --------------------------------- |
| `a`  | number | Start value                       |
| `b`  | number | End value                         |
| `t`  | number | Interpolation factor (`0.0`–`1.0`) |

**Returns:** `number`

```lua
print(Cute.Math.lerp(0, 100, 0.5))  -- 50.0
print(Cute.Math.lerp(0, 100, 0.25)) -- 25.0
```

---

## Cute.Math.between

Check if a number is between two values (inclusive).

```lua
Cute.Math.between(val, min, max)
```

**Returns:** `boolean`

```lua
print(Cute.Math.between(50, 0, 100))  -- true
print(Cute.Math.between(101, 0, 100)) -- false
```

---

## Cute.Math.distance

Get the 3D distance between two coordinate tables.

```lua
Cute.Math.distance(a, b)
```

| Name | Type                         | Description  |
| ---- | ---------------------------- | ------------ |
| `a`  | `{ x, y, z }` or `vector3`  | First point  |
| `b`  | `{ x, y, z }` or `vector3`  | Second point |

**Returns:** `number`

```lua
local dist = Cute.Math.distance(
    { x = 0.0, y = 0.0, z = 0.0 },
    { x = 3.0, y = 4.0, z = 0.0 }
)
print(dist) -- 5.0
```

---

## Cute.Math.randomInt

Return a random integer between `min` and `max` (inclusive).

```lua
Cute.Math.randomInt(min, max)
```

**Returns:** `integer`

```lua
local roll = Cute.Math.randomInt(1, 6)
print(roll) -- e.g. 4
```

---

## Cute.Math.formatNumber

Format a number with thousand separators for display.

```lua
Cute.Math.formatNumber(n, sep)
```

| Name  | Type   | Default | Description              |
| ----- | ------ | ------- | ------------------------ |
| `n`   | number | —       | The number to format     |
| `sep` | string | `'.'`   | Thousands separator char |

**Returns:** `string`

```lua
print(Cute.Math.formatNumber(1234567))       -- '1.234.567'
print(Cute.Math.formatNumber(1234567, ','))  -- '1,234,567'
```
