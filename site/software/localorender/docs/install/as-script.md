---
meta_title: 'LocaloRender - Documentation - Install as script'
meta_image: './software/localorender/imgs/localorender-cover.jpg'
description: 'A Nuke tool to replace the native Render dialog for Write nodes.'
---
<link rel="stylesheet" href="../../../localorender.css">

# install as script

## in a python knob

You can create a Python knob on any node, then :octicons-copy-16: copy/paste 
[localorender.py](https://github.com/MrLixm/nuke-tools-lxm/blob/main/src/localorender/localorender.py)
inside.

You can optionally edit the last line `open_as_panel()` to replace it by
`open_as_panel(modal=True)` if you prefer a modal dialog, than a floating
panel.

The `open_as_panel` call can also take an optional `uibuilder` argument.

## in the script editor

You never install the tool and just :octicons-copy-16: copy/paste 
[localorender.py](https://github.com/MrLixm/nuke-tools-lxm/blob/main/src/localorender/localorender.py)
in the script editor every time.

You can optionally edit the last line `open_as_panel()` to replace it by
`open_as_panel(modal=True)` if you prefer a modal dialog, than a floating
panel.

The `open_as_panel` call can also take an optional `uibuilder` argument.
