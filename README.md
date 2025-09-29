# GuiForge

This is a lightweight and customizable UI library for mods, designed to create modern, dynamic, and responsive interfaces in Roblox.
It provides ready-to-use components like tabs, buttons, sliders, checkboxes, toggles, labels, notifications, and more, all styled with a clean and flexible design system.

With built-in support for themes, colors, icons, draggable windows, auto-scrolling, minimization, and animated effects, this library allows developers to quickly build professional-looking mod menus without reinventing the wheel.

Perfect for creating game utilities, mod menus, or plugin interfaces, it’s easy to integrate, extend, and adapt to any project.


# 📘 GuiForge Documentation

### Installation
To load the library into your Roblox project, simply use:

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/AdrainRazini/GuiForge/refs/heads/main/Modules/Regui.lua"))()
```

This will give you access to the full **GuiForge API**.

---

## ✨ Features
- **Tabs System** – Create multiple pages within your mod menu.  
- **Sub Tabs** – Organize content into collapsible groups.  
- **Buttons** – Fully customizable with hover/click effects.  
- **Text Inputs** – Capture user text dynamically.  
- **Checkboxes & Toggles** – Boolean options with visual feedback.  
- **Sliders (Int/Float/Options)** – Adjustable values with smooth UI.  
- **Labels & Images** – Add custom text and icons.  
- **Notifications** – Built-in alerts and dialogs.  
- **Draggable & Minimizable Windows** – Move and collapse your menus.  
- **Themes & Colors** – Easy customization with predefined palettes.  

---

## 🚀 Quick Start Example

```lua
local GuiForge = loadstring(game:HttpGet("https://raw.githubusercontent.com/AdrainRazini/GuiForge/refs/heads/main/Modules/Regui.lua"))()

-- Create a main window
local window = GuiForge.TabsWindow({
	Title = "My Mod Menu",
	Size = UDim2.new(0, 400, 0, 300),
	Text = "GuiForge Example"
})

-- Create a tab
local mainTab = GuiForge.CreateTab(window, {Name = "Main"})

-- Add a label
GuiForge.CreateLabel(mainTab, {
	Text = "Welcome to GuiForge!",
	Color = "White",
	Alignment = "Center"
})


local OptionsStrings = GuiForge.CreateSelectorOpitions(mainTab, {
	Name = "Selector",
	Alignment = "Center",
	Size_Frame = UDim2.new(1,-10,0,50),
	Frame_Max = 50,
	Options = {

		"On",
		"Off"

	},

	Type = "String"
}, function(val)
	print("Você escolheu:", val)
end)

local OptionsInstance = GuiForge.CreateSelectorOpitions(mainTab, {
	Name = "Selector",
	Alignment = "Center",
	Size_Frame = UDim2.new(1,-10,0,50),
	Frame_Max = 50,
	Options = {

		{name = "Name", Obj = "Parent"},
		
	},

	Type = "Instance"
}, function(val)
	print("Você escolheu:", val)
end)

-- Add a button
GuiForge.CreateButton(mainTab, {
	Text = "Click Me",
	Color = "White",
	BGColor = "Blue"
}, function()
	print("Button clicked!")
	GuiForge.NotificationPerson(window.Frame.Parent, {
		Title = "Hello!",
		Text = "You clicked the button!",
		Tempo = 3,
		Icon = "fa_envelope"
	})
end)

-- Add a toggle
GuiForge.CreateToggleboxe(mainTab, {
	Text = "Enable Feature",
	Color = "Green"
}, function(state)
	print("Toggle state:", state)
end)

-- Add a checkbox
GuiForge.CreateCheckboxe(mainTab, {
	Text = "Extra Option",
	Color = "Yellow"
}, function(state)
	print("Checkbox state:", state)
end)

-- Add a slider
GuiForge.CreateSliderInt(mainTab, {
	Text = "Speed",
	Minimum = 1,
	Maximum = 10,
	Value = 5
}, function(value)
	print("Slider value:", value)
end)

```

---

## 📂 API Overview

### 🖼 Windows
- `GuiForge.TabsWindow(list)` → Creates the main window.  
- `GuiForge.SubTabsWindow(scroll, list)` → Adds a sub-window with multiple mini-tabs.  

### 📑 Tabs
- `GuiForge.CreateTab(window, list)` → Creates a new tab in the main window.  
- `GuiForge.CreateSubTab(scroll, list)` → Creates a collapsible section.  

### 🔘 UI Elements
- `GuiForge.CreateButton(scroll, list, callback)`  
- `GuiForge.CreateTextBox(scroll, list, callback)`  
- `GuiForge.CreateCheckboxe(scroll, list, callback)`  
- `GuiForge.CreateToggleboxe(scroll, list, callback)`  
- `GuiForge.CreateSliderInt(scroll, list, callback)`  
- `GuiForge.CreateSliderFloat(scroll, list, callback)`  
- `GuiForge.CreateSliderOption(scroll, list, callback)`  
- `GuiForge.CreateLabel(scroll, list)`  
- `GuiForge.CreateImage(scroll, list)`  

### 🔔 Notifications
- `GuiForge.NotificationPerson(Gui, list, callback)` → Custom pop-up notification.  
- `GuiForge.NotificationDialog(Gui, list, callback)` → Yes/No dialog box.  
- `GuiForge.Notifications(Gui, list, callback)` → Simple notification using Roblox `SetCore`.  

### 🎨 Utilities
- `GuiForge.applyCorner(instance, radius)`  
- `GuiForge.applyUIStroke(instance, colorName, thickness)`  
- `GuiForge.applyDraggable(frame, dragButton)`  
- `GuiForge.applyAutoScrolling(scroll, padding, alignment)`  

---

## 🎯 Example: Notification
```lua
GuiForge.NotificationPerson(game.Players.LocalPlayer.PlayerGui, {
    Title = "Success",
    Text = "Feature Activated!",
    Tempo = 5,
    Icon = "fa_bx_config"
})
```

---

## 🏷 Credits
- **Library Name:** GuiForge  
- **Author:** @Adrian75556435  
- **Version:** 1.0.0  
- **Description:** Lightweight customizable UI library for Roblox mods.  
