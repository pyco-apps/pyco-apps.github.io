<link rel="stylesheet" href="../../../localorender.css">

# install as a new menu entry

1. :octicons-copy-16:
   Copy [localorender.py](https://github.com/MrLixm/nuke-tools-lxm/blob/main/src/localorender/localorender.py)
   to your local nuke path (`~/.nuke`)

2. At the same location, open the `menu.py` file (or create it) and add the
   following content inside:

=== "Open as a detached nuke panel"

    A nuke panel floating above the UI. Can be docked.

    ```python
    import nuke
    import localorender
        
    menu = nuke.menu("Nuke").menu("Render")
    menu.addCommand("Open LocaloRender", lambda: localorender.open_as_panel(), "F8")
    ```

=== "Open as modal dialog"

    A modal dialog is an un dockable window that block all the UI 
    until the window is closed.

    ```python
    import nuke
    import localorender
        
    menu = nuke.menu("Nuke").menu("Render")
    menu.addCommand("Open LocaloRender", lambda: localorender.open_as_panel(modal=True), "F8")
    ```

You can open the tool in Nuke by going to the top menu
bar > `Render` > `Open LocaloRender`

!!! tip

    You can also change the shortcut in the above code from `F8` to what you
    prefer.

## optional configuration

It's possible to set the configuration in which the tool open using the
`uibuilder` argument:

```python
import nuke
import localorender

uibuilder = localorender.UiBuilder(
    # open the UI with all writes nodes loaded by default
    node_selection_mode=localorender.WriteNodeSelectorWidget.option_all,
    # prevent to use the Settings system (if bugged)
    lock_settings=True,
)

menu = nuke.menu("Nuke").menu("Render")
menu.addCommand(
    "Open LocaloRender",
    lambda: localorender.open_as_panel(modal=True, uibuilder=uibuilder),
    "F8"
)
```