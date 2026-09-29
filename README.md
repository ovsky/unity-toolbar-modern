# 🎨 Toolbar Extender

> A modern, maintained fork of the beloved Toolbar Extender for Unity. Extend the Unity Editor toolbar with your own custom UI elements effortlessly.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Unity 2021.1+](https://img.shields.io/badge/Unity-2021.1%2B-blue)
![C#](https://img.shields.io/badge/Language-C%23-239120)
![Actively Maintained](https://img.shields.io/badge/Status-Actively%20Maintained-brightgreen)

---

## ✨ Features

- **Simple & Elegant API** – Just hook your GUI methods to `LeftToolbarGUI` or `RightToolbarGUI`
- **Flexible Positioning** – Add UI elements to the left or right side of the toolbar, around the play button
- **Full Editor Integration** – Seamlessly integrates with the native Unity toolbar
- **Multi-Version Support** – Compatible with Unity 2021.1 and newer
- **Reflection-Based** – Works with Unity's internal toolbar system using safe reflection patterns
- **Well-Documented** – Includes example scenes and clear usage patterns

---

## 🚀 Quick Start

### Installation

1. **Via Package Manager** (Recommended)
   - Open the Unity Package Manager window
   - Click "+" → "Add package from git URL"
   - Enter: `https://github.com/ovsky/unity-toolbar-modern.git`

2. **Manual Installation**
   - [Download the repository](https://github.com/ovsky/unity-toolbar-modern/archive/refs/heads/main.zip)
   - Drag the folder into your `Assets` directory

### Basic Usage

Create a script with `[InitializeOnLoad]` and add your UI logic:

```csharp
using UnityEditor;
using UnityEngine;
using UnityToolbarExtender;

[InitializeOnLoad]
public class MyToolbarButtons
{
    static MyToolbarButtons()
    {
        ToolbarExtender.LeftToolbarGUI.Add(DrawLeftToolbar);
        ToolbarExtender.RightToolbarGUI.Add(DrawRightToolbar);
    }

    static void DrawLeftToolbar()
    {
        GUILayout.FlexibleSpace();
        
        if (GUILayout.Button("My Button", EditorStyles.toolbarButton))
        {
            Debug.Log("Toolbar button clicked!");
        }
    }

    static void DrawRightToolbar()
    {
        if (GUILayout.Button("Settings", EditorStyles.toolbarButton))
        {
            // Open settings window
        }
    }
}
```

---

## 📚 Examples Included

The package comes with ready-to-use examples:

### 🎬 Scene Switcher
Quick buttons to switch between scenes during development. Demonstrates play mode change handling.

### 👁️ Scene View Focuser  
A toggle button that demonstrates `EditorPrefs` usage for persistent settings.

---

## 🛠️ API Reference

### Static Properties

```csharp
// List of actions to execute when rendering left toolbar
public static readonly List<Action> LeftToolbarGUI

// List of actions to execute when rendering right toolbar
public static readonly List<Action> RightToolbarGUI
```

### Usage Pattern

```csharp
// Add your GUI rendering method
ToolbarExtender.LeftToolbarGUI.Add(MyGUIMethod);

// Remove when no longer needed
ToolbarExtender.LeftToolbarGUI.Remove(MyGUIMethod);
```

---

## 🎯 Common Patterns

### Add a Simple Button
```csharp
if (GUILayout.Button("Text", EditorStyles.toolbarButton))
{
    // Action here
}
```

### Add a Dropdown
```csharp
GUILayout.Dropdown(selected, options, EditorStyles.toolbarDropDown);
```

### Add a Toggle
```csharp
EditorGUI.Toggle(new Rect(...), myBool, EditorStyles.toolbarButton);
```

### Add Spacing
```csharp
GUILayout.FlexibleSpace();  // Flexible space
GUILayout.Space(10);        // Fixed space
```

---

## 📋 Requirements

- **Unity Version:** 2021.1 or newer
- **Platform:** Works with all Unity Editor platforms
- **Dependencies:** None

---

## ⚖️ License

MIT License – Feel free to use this in your projects!

---

## 🙏 Credits

Originally created by **Marijn Zwemmer** ([unity-toolbar-extender](https://github.com/marijnz/unity-toolbar-extender))

**Modern Fork & Maintenance:** [ovsky](https://github.com/ovsky)

---

## 💡 Tips

- Use `GUILayout.FlexibleSpace()` to center your elements
- Leverage `EditorGUIUtility.currentViewWidth` for responsive layouts
- Remember to use `EditorStyles.toolbarButton` and similar toolbar styles for visual consistency
- Test across different Unity versions – internal toolbar structure varies

---

## 🤝 Contributing

Found a bug or have a suggestion? Feel free to open an issue or submit a pull request!

---

<div align="center">

**Made with ❤️ for the Unity development community**

[⭐ Give it a star if you find it useful!](https://github.com/ovsky/unity-toolbar-modern)

</div>
