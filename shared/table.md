# Table

Table utility functions. Available on both **client** and **server**.

---

## Cute.Table.contains

Check if a table contains a specific value.

```lua
Cute.Table.contains(tbl, value)
```

| Name    | Type  | Description        |
| ------- | ----- | ------------------ |
| `tbl`   | table | The table to check |
| `value` | any   | Value to look for  |

**Returns:** `boolean`

```lua
local fruits = { 'apple', 'banana', 'orange' }
print(Cute.Table.contains(fruits, 'banana')) -- true
```

---

## Cute.Table.indexOf

Get the index of a value in an array table. Returns `nil` if not found.

```lua
Cute.Table.indexOf(tbl, value)
```

**Returns:** `integer | nil`

```lua
local items = { 'sword', 'shield', 'potion' }
print(Cute.Table.indexOf(items, 'shield')) -- 2
```

---

## Cute.Table.deepcopy

Create a full recursive copy of a table.

```lua
Cute.Table.deepcopy(orig)
```

**Returns:** `table`

```lua
local original = { a = 1, b = { c = 2 } }
local copy = Cute.Table.deepcopy(original)
```

---

## Cute.Table.merge

Merge two tables (shallow). Values from `tbl2` overwrite `tbl1`.

```lua
Cute.Table.merge(tbl1, tbl2)
```

**Returns:** `table`

```lua
local base = { a = 1, b = 2 }
local extra = { b = 99, c = 3 }
local result = Cute.Table.merge(base, extra)
-- result = { a = 1, b = 99, c = 3 }
```

---

## Cute.Table.size

Get the number of entries in a table (works for hash tables too).

```lua
Cute.Table.size(tbl)
```

**Returns:** `integer`

```lua
local t = { a = 1, b = 2, c = 3 }
print(Cute.Table.size(t)) -- 3
```

---

## Cute.Table.filter

Filter a table using a predicate function. Returns a new array table with matching values.

```lua
Cute.Table.filter(tbl, fn)
```

| Name  | Type     | Description                                          |
| ----- | -------- | ---------------------------------------------------- |
| `tbl` | table    | Source table                                         |
| `fn`  | function | `function(value, key): boolean` — return true to keep |

**Returns:** `table`

```lua
local numbers = { 1, 2, 3, 4, 5, 6 }
local evens = Cute.Table.filter(numbers, function(v)
    return v % 2 == 0
end)
-- evens = { 2, 4, 6 }
```

---

## Cute.Table.map

Map over a table and transform each value. Returns a new table.

```lua
Cute.Table.map(tbl, fn)
```

**Returns:** `table`

```lua
local prices = { 10, 20, 30 }
local doubled = Cute.Table.map(prices, function(v)
    return v * 2
end)
-- doubled = { 20, 40, 60 }
```

---

## Cute.Table.flatten

Flatten a nested array table one level deep.

```lua
Cute.Table.flatten(tbl)
```

**Returns:** `table`

```lua
local nested = { { 1, 2 }, { 3, 4 }, { 5 } }
local flat = Cute.Table.flatten(nested)
-- flat = { 1, 2, 3, 4, 5 }
```

---

## Cute.Table.isEmpty

Check if a table has no entries.

```lua
Cute.Table.isEmpty(tbl)
```

**Returns:** `boolean`

```lua
print(Cute.Table.isEmpty({}))      -- true
print(Cute.Table.isEmpty({ 1 }))   -- false
```

---

## Cute.Table.keys

Get all keys of a table as an array.

```lua
Cute.Table.keys(tbl)
```

**Returns:** `table`

```lua
local t = { a = 1, b = 2 }
local k = Cute.Table.keys(t) -- { 'a', 'b' }
```

---

## Cute.Table.values

Get all values of a table as an array.

```lua
Cute.Table.values(tbl)
```

**Returns:** `table`

```lua
local t = { a = 10, b = 20 }
local v = Cute.Table.values(t) -- { 10, 20 }
```
