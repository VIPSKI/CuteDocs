# Notify

Modern NUI notification system with a NP4/ProdigyRP-inspired design. **Client only.**

---

## Cute.Notify.send

Send a fully customised notification to the NUI overlay.

```lua
Cute.Notify.send(options)
```

| Field         | Type    | Default  | Description                                        |
| ------------- | ------- | -------- | -------------------------------------------------- |
| `type`        | string  | `'info'` | `'success'`, `'error'`, `'warning'`, or `'info'`   |
| `title`       | string  | —        | Header text (optional, defaults to type label)     |
| `description` | string  | `''`     | Body text                                          |
| `duration`    | integer | `4000`   | Auto-dismiss time in milliseconds                  |

```lua
Cute.Notify.send({
    type        = 'success',
    title       = 'Bil spawnet',
    description = 'Din bil er blevet spawnet ved dig.',
    duration    = 3000,
})
```

---

## Cute.Notify.success

Shorthand for a **green** success notification.

```lua
Cute.Notify.success(title, description, duration)
```

```lua
Cute.Notify.success('Succes!', 'Penge modtaget.')
```

---

## Cute.Notify.error

Shorthand for a **red** error notification.

```lua
Cute.Notify.error(title, description, duration)
```

```lua
Cute.Notify.error('Fejl!', 'Du har ikke nok penge.')
```

---

## Cute.Notify.warning

Shorthand for a **yellow** warning notification.

```lua
Cute.Notify.warning(title, description, duration)
```

```lua
Cute.Notify.warning('Advarsel', 'Din HP er lav!', 5000)
```

---

## Cute.Notify.info

Shorthand for a **blue** info notification.

```lua
Cute.Notify.info(title, description, duration)
```

```lua
Cute.Notify.info('Server', 'Genstart om 5 minutter.')
```

---

## Cute.Notify.basic

Send a native GTA V notification (fallback, no NUI).

```lua
Cute.Notify.basic(msg, flash, saveToBrief)
```

| Name          | Type    | Default | Description                  |
| ------------- | ------- | ------- | ---------------------------- |
| `msg`         | string  | —       | Notification text            |
| `flash`       | boolean | `false` | Flash the notification       |
| `saveToBrief` | boolean | `false` | Save to the pause menu brief |

```lua
Cute.Notify.basic('~g~You received $500!')
```

---

## Cute.Notify.helpText

Show a help text hint in the top-left corner of the screen.

```lua
Cute.Notify.helpText(msg)
```

```lua
Cute.Notify.helpText('Press ~INPUT_CONTEXT~ to interact.')
```

---

## Cute.Notify.subtitle

Show a subtitle at the bottom of the screen.

```lua
Cute.Notify.subtitle(msg, duration)
```

| Name       | Type    | Default | Description           |
| ---------- | ------- | ------- | --------------------- |
| `msg`      | string  | —       | Subtitle text         |
| `duration` | integer | `3500`  | Duration in ms        |

```lua
Cute.Notify.subtitle('~b~Welcome to the server!', 5000)
```
