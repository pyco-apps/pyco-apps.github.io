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