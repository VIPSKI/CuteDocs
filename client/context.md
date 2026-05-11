# Context Menu

The context menu UI allows you to display an interactive list of options to the player, with support for sub-menus, descriptions, icons, metadata panels, and progress bars per item.

---

## Cute.Context.register

Registers one or more context menus. Menus must be registered before they can be opened.

```lua
Cute.Context.register(menu)
```

**Parameters**

| Parameter | Type | Description |
|-----------|------|-------------|
| `menu` | `table` | A single menu table, or an array of menu tables |

**Menu fields**

| Field | Type | Default | Description |
|-------|------|---------|-------------|
| `id` | `string` | required | Unique identifier used to open the menu |
| `title` | `string` | required | Title displayed in the header |
| `menu` | `string` | `nil` | ID of parent menu — shows a back arrow in the header |
| `canClose` | `boolean` | `true` | If `false`, hides the X button so the player cannot close it manually |
| `options` | `table` | required | Array of option items (see below) |

**Option fields**

| Field | Type | Description |
|-------|------|-------------|
| `title` | `string` | Label for the option |
| `description` | `string` | Smaller text shown below the title |
| `icon` | `string` | Icon character or emoji displayed on the left |
| `iconColor` | `string` | CSS color string for the icon |
| `disabled` | `boolean` | Grays out the option and makes it unclickable |
| `readOnly` | `boolean` | Like disabled but without the grayed-out opacity |
| `menu` | `string` | ID of a sub-menu to navigate to when clicked |
| `arrow` | `boolean` | Shows a `›` arrow on the right side |
| `progress` | `number` | Fills a progress bar (0–100) below the title |
| `metadata` | `table` | Array of `{ label, value }` shown in a side panel on hover |
| `onSelect` | `function` | Called when the option is clicked |
| `args` | `any` | Passed as the first argument to `onSelect` |

---

## Cute.Context.open

Opens a registered context menu by its ID.

```lua
Cute.Context.open(id)
```

| Parameter | Type | Description |
|-----------|------|-------------|
| `id` | `string` | The ID of a previously registered menu |

---

## Cute.Context.close

Closes the currently open context menu.

```lua
Cute.Context.close()
```

---

## Cute.Context.getOpen

Returns the ID of the currently open menu, or `nil` if none is open.

```lua
local id = Cute.Context.getOpen()
```

---

## Usage Example

```lua
Cute.Context.register({
    id = 'garage_menu',
    title = 'Garage',
    canClose = true,
    options = {
        {
            title = 'Hent køretøj',
            description = 'Vælg et køretøj fra din garage',
            icon = '🚗',
            menu = 'vehicle_list',
        },
        {
            title = 'Sæt køretøj i opbevaring',
            description = 'Parkér dit nuværende køretøj',
            icon = '📦',
            onSelect = function()
                -- store vehicle logic
            end,
        },
        {
            title = 'Deaktiveret valg',
            description = 'Ikke tilgængeligt lige nu',
            disabled = true,
        },
        {
            title = 'Kondition',
            description = 'Dit køretøjs tilstand',
            progress = 72,
            metadata = {
                { label = 'Motor',   value = '72%' },
                { label = 'Dæk',     value = '85%' },
                { label = 'Krop',    value = '60%' },
            },
        },
    },
})

Cute.Context.register({
    id = 'vehicle_list',
    title = 'Vælg køretøj',
    menu = 'garage_menu',
    options = {
        { title = 'Sultan RS',  onSelect = function() end },
        { title = 'Zentorno',   onSelect = function() end },
    },
})

RegisterCommand('garage', function()
    Cute.Context.open('garage_menu')
end)
```

---

## Notes

- You can register multiple menus at once by passing an array of menu tables to `Cute.Context.register`.
- Sub-menus are navigated client-side with no extra Lua calls needed.
- The menu can be closed by the player with **ESC** unless `canClose` is set to `false`.
