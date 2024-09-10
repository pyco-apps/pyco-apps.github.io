---
meta_title: 'LocaloRender - Documentation - Install'
meta_image: './software/localorender/imgs/localorender-cover.jpg'
description: 'A Nuke tool to replace the native Render dialog for Write nodes.'
---
<link rel="stylesheet" href="../../localorender.css">

# installation

## pre-requisites

The tool is self-contained and doesn't have external dependency. It
requires PySide2 to work, but this program is bundled with Nuke.

The tool is compatible with:

- [x] Python-2 and Python-3
- [x] any operating system
- [x] at least _Nuke_, _Nuke X_ and _Nuke Non-Commercial_ (probably others)

It was tested on Nuke 15 Non-commercial on Windows.

!!! note

    The tool is writing files in your system default temporary directory,
    which are deleted on Nuke exit (needed for the icons in the GUI).

## methods

You can install the tool in multiple ways dependending on your preferences.

!!! tip

    You can **combine** multiple installation methods if desired.

| installation methods                                          |                                              |
|---------------------------------------------------------------|----------------------------------------------|
| :material-menu: [as-menu](as-menu.md)                         | add a new entry in the "Render" top menu bar |
| :material-window-restore: [as-pane](as-pane.md)               | add a new :nuke-panel-icon: pane option.     |
| :material-file-replace-outline: [as-override](as-override.md) | replace the native render dialog.            |
| :material-script-text: [as-script](as-script.md)              | Script Editor and Python Knob buttons.       |
