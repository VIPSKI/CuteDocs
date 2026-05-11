# DrawText

2D and 3D text drawing utilities. **Client only.** Must be called every frame inside a `CreateThread` loop or tick.

---

## Cute.DrawText.draw2D

Draw text at a 2D screen position.

```lua
Cute.DrawText.draw2D(text, x, y, scale, r, g, b, a, font)
```

| Name    | Type    | Default | Description                          |
| ------- | ------- | ------- | ------------------------------------ |
| `text`  | string  | —       | Text to display                      |
| `x`     | number  | —       | Screen X position (`0.0` – `1.0`)    |
| `y`     | number  | —       | Screen Y position (`0.0` – `1.0`)    |
| `scale` | number  | `0.35`  | Text scale                           |
| `r`     | integer | `255`   | Red channel (0–255)                  |
| `g`     | integer | `255`   | Green channel (0–255)                |
| `b`     | integer | `255`   | Blue channel (0–255)                 |
| `a`     | integer | `255`   | Alpha channel (0–255)                |
| `font`  | integer | `4`     | GTA font index                       |

```lua
CreateThread(function()
    while true do
        Wait(0)
        Cute.DrawText.draw2D('Hello World', 0.5, 0.5)
    end
end)
```

---

## Cute.DrawText.draw3D

Draw floating text at a 3D world coordinate. Automatically scales with camera distance.

```lua
Cute.DrawText.draw3D(text, coords, scale, r, g, b, a)
```

| Name     | Type               | Default | Description                       |
| -------- | ------------------ | ------- | --------------------------------- |
| `text`   | string             | —       | Text to display                   |
| `coords` | `{x,y,z}`/vector3 | —       | World position                    |
| `scale`  | number             | `0.35`  | Base text scale                   |
| `r`      | integer            | `255`   | Red (0–255)                       |
| `g`      | integer            | `255`   | Green (0–255)                     |
| `b`      | integer            | `255`   | Blue (0–255)                      |
| `a`      | integer            | `255`   | Alpha (0–255)                     |

```lua
CreateThread(function()
    local coords = GetEntityCoords(PlayerPedId())
    while true do
        Wait(0)
        Cute.DrawText.draw3D('Press E to interact', coords, 0.35, 255, 255, 255, 255)
    end
end)
```
