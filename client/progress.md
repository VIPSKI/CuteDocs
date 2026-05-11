# Progress

Progress bar and circle UI components. Both block the thread until complete or cancelled. **Client only.**

---

## Cute.Progress.bar

Display a horizontal progress bar at the bottom center of the screen. Blocks until done.

```lua
local completed = Cute.Progress.bar(options)
```

| Field        | Type    | Default | Description                        |
| ------------ | ------- | ------- | ---------------------------------- |
| `duration`   | integer | —       | Duration in milliseconds           |
| `label`      | string  | `''`    | Text shown above the bar           |
| `canCancel`  | boolean | `false` | Allow player to cancel with ESC    |

**Returns:** `boolean` — `true` if completed, `false` if cancelled.

```lua
local done = Cute.Progress.bar({
    duration  = 5000,
    label     = 'Reparerer bil...',
    canCancel = true,
})

if done then
    Cute.Notify.success('Færdig', 'Bilen er repareret.')
else
    Cute.Notify.error('Annulleret', 'Reparation afbrudt.')
end
```

---

## Cute.Progress.circle

Display a circular progress indicator. Blocks until done.

```lua
local completed = Cute.Progress.circle(options)
```

| Field        | Type    | Default    | Description                              |
| ------------ | ------- | ---------- | ---------------------------------------- |
| `duration`   | integer | —          | Duration in milliseconds                 |
| `label`      | string  | `''`       | Text shown below the circle              |
| `position`   | string  | `'middle'` | `'middle'` (center screen) or `'bottom'` |
| `canCancel`  | boolean | `false`    | Allow player to cancel with ESC          |

**Returns:** `boolean` — `true` if completed, `false` if cancelled.

```lua
local done = Cute.Progress.circle({
    duration  = 3000,
    label     = 'Hacker system...',
    position  = 'middle',
    canCancel = true,
})

if done then
    print('Hack succesfuldt!')
end
```

---

## Cute.Progress.active

Returns `true` if a progress bar or circle is currently active.

```lua
Cute.Progress.active()
```

**Returns:** `boolean`

```lua
if Cute.Progress.active() then
    print('En progress kører allerede.')
end
```

---

## Cute.Progress.cancel

Cancel and hide any currently active progress UI immediately.

```lua
Cute.Progress.cancel()
```

```lua
-- Force-stop fra en anden tråd
Cute.Progress.cancel()
```

---

## Full example

```lua
CreateThread(function()
    -- Vis TextUI hint
    Cute.ShowTextUI({
        interact = "E",
        message  = "For at reparere bil",
    })

    -- Vent på E-tast
    while not IsControlJustReleased(0, 38) do
        Wait(0)
    end

    Cute.HideTextUI()

    -- Start progress
    local success = Cute.Progress.bar({
        duration  = 6000,
        label     = 'Reparerer bil...',
        canCancel = true,
    })

    if success then
        Cute.Notify.success('Succes', 'Bilen er repareret.')
    else
        Cute.Notify.warning('Annulleret', 'Reparation stoppet.')
    end
end)
```
