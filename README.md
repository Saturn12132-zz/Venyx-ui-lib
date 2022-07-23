```lua
--ui initiate
local Venyx = loadstring(game:HttpGet("https://raw.githubusercontent.com/Saturn12132/Venyx-ui-lib/main/module.lua"))()
```

```lua
--title and stuff
local UI = Venyx.new({
    title = "Venyx"
})
```

```lua
--set theme
UI:setTheme({
theme = "Background/Glow/Accent/LightContrast", 
color3 = Color3.fromRGB(101,26,138)
})
```

```lua
-- add a page
local Test = UI:addPage({
    title = "Test",
    icon = 5012544693
})
```

```lua
--add a section
local SectionA = Test:addSection({
    title = "Section A"
})
```

```lua
--button
SectionA:addButton({
    title = "Button",
    callback = function()
        print("Clicked")
    end
})
```

```lua
--toggle
SectionA:addToggle({
    title = "Toggle",
    callback = function(value)
        print("Toggled", value)
    end
})
```

```lua
SectionA:addTextbox({
    title = "Notification",
    default = "Default",
    callback = function(value, focusLost)
        print("Input", value)

        if (focusLost) then
            UI:Notify({
                title = "Title",
                text = value
            })
        end
    end
})
```

```lua
--textbox
SectionA:addTextbox({
    title = "Notification",
    default = "Default",
    callback = function(value)
        print("Input", value)
    end
})
```

```lua
--keybind
SectionA:addKeybind({
    title = "Toggle Keybind",
    key = Enum.KeyCode.One,
    callback = function()
        print("Activated Keybind")
        UI:toggle()
    end,
    changedCallback = function(key)
        print("Changed Keybind", key)
    end
})
```

```lua
--dropdown
SectionA:addSlider({
    title = "Slider",
    default = 0,
    min = -100,
    max = 100,
    callback = function(value)
        print("Dragged", value)
    end
})
```

```lua
--dropdown
local dropdownContent = {"Hello", "World", "Hello World", "Word", 1, 2, 3} -- // To save me from keep on doing this
SectionB:addDropdown({
    title = "Dropdown",
    list = dropdownContent,
    callback = function(text)
        print("Selected", text)
    end
})
```
