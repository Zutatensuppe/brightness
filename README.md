# brightness

Increases or decreases brightness of the display.

## Usage

1. Store your sudo password into secret-tool:

    ```
    secret-tool store --label='TestLabel' TestAttr TestVal
    ```

    You will then be asked to enter a password. This has to be the root password, because the brightness script requires sudo to put a value into
`/sys/class/backlight/intel_backlight/brightness`.

2. Put the following into the brightness script (depending on what you used in the first step):

    ```
    secret_tool_attribute = "TestAttr"
    secret_tool_value = "TestVal"
    ```

3. Then to increase/decrease brightness call:

    ```
    ./brightness up
    ./brightness down
    ```

### With i3wm

Put the following into your `~/.config/i3/config` to have the brightness up/down keys
increase/decrease brightness (adjust `PATH_TO_BRIGTHNESS` accordingly):

```
bindsym XF86MonBrightnessUp exec PATH_TO_BRIGTHNESS up    
bindsym XF86MonBrightnessDown exec PATH_TO_BRIGHTNESS down
```

## Requirements

- `secret-tool`
- `python3`
