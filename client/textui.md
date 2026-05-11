# TextUI

A minimal, clean interaction prompt rendered in the NUI overlay. Inspired by NP4/ProdigyRP — shows an optional key badge next to a message. **Client only.**

---

## Cute.ShowTextUI

Show the TextUI overlay.

```lua
Cute.ShowTextUI(options)
```

| Field       | Type   | Required | Description                                                        |
| ----------- | ------ | -------- | ------------------------------------------------------------------ |
| `[1]`       | string | No       | Optional ID for your own reference — not rendered in the UI        |
| `interact`  | string | No       | Key label shown in the badge (e.g. `"E"`). Omit for text-only mode |
| `message`   | string | Yes      | The message text to display                                        |

**With key badge:**

```lua
Cute.ShowTextUI({
    interact = "E",
    message  = "For at tilgå garagen",
})
```

**Text only (no key badge):**

```lua
Cute.ShowTextUI({
    message = "Du er i en zone",
})
```

**With an ID (optional):**

```lua
Cute.ShowTextUI({ "armory",
    interact = "E",
    message  = "Åbn armeriet",
})
```

---

## Cute.HideTextUI

Hide the TextUI overlay.

```lua
Cute.HideTextUI()
```

```lua
Cute.HideTextUI()
```

---

## Full example

```lua
local insideZone = false

CreateThread(function()
    while true do
        Wait(0)

        local ped    = PlayerPedId()
        local coords = GetEntityCoords(ped)
        local dist   = #(coords - vector3(123.4, 456.7, 89.0))

        if dist < 2.0 then
            if not insideZone then
                insideZone = true
                Cute.ShowTextUI({
                    interact = "E",
                    message  = "For at tilgå garagen",
                })
            end

            if IsControlJustReleased(0, 38) then -- E key
                -- do something
            end
        else
            if insideZone then
                insideZone = false
                Cute.HideTextUI()
            end
        end
    end
end)
```
