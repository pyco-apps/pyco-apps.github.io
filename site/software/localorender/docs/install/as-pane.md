---
meta_title: 'LocaloRender - Documentation - Install as pane'
meta_image: './software/localorender/imgs/localorender-cover.jpg'
description: 'A Nuke tool to replace the native Render dialog for Write nodes.'
---
<link rel="stylesheet" href="../../../localorender.css">

# install as a new pane option

1. :octicons-copy-16:
   Copy [localorender.py](https://github.com/MrLixm/nuke-tools-lxm/blob/main/src/localorender/localorender.py)
   to your local nuke path (`~/.nuke`)
2. At the same location, open the `menu.py` file (or create it) and add the
   following content inside:

```python
import localorender

localorender.register_as_panel()
```

You can open the panel in Nuke by clicking the :nuke-panel-icon: icon
then `Windows` > `Custom` > `Localorender`

# optional configuration

You can also optionally add the following lines:
```python
localorender.configure_logging()
``` 
which should allow you to see logging message in the Script Editor.
