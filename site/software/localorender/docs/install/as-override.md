---
meta_title: 'LocaloRender - Documentation - Install as override'
meta_image: './software/localorender/imgs/localorender-cover.jpg'
description: 'A Nuke tool to replace the native Render dialog for Write nodes.'
---
<link rel="stylesheet" href="../../../localorender.css">

# install as override

This method will fully override the default Write node render dialog.

1. :octicons-copy-16:
   Copy [localorender.py](https://github.com/MrLixm/nuke-tools-lxm/blob/main/src/localorender/localorender.py)
   to your local nuke path (`~/.nuke`)
2. At the same location, open the `menu.py` file (or create it) and add the
   following content inside:

```python
import nukescripts
import localorender

nukescripts.showRenderDialog = localorender.nukescript_showRenderDialog()
```

## optional configuration

You can also optionally add the following lines:
```python
localorender.configure_logging()
``` 
which should allow you to see logging message in the Script Editor.

It's possible to set the configuration in which the tool open using the
`uibuilder` argument:

```python
import nukescripts
import localorender

uibuilder = localorender.UiBuilder(
    # open the UI with all writes nodes loaded by default
    node_selection_mode=localorender.WriteNodeSelectorWidget.option_all,
    # prevent to use the Settings system (if bugged)
    lock_settings=True,
)

nukescripts.showRenderDialog = localorender.nukescript_showRenderDialog(uibuilder=uibuilder)
```