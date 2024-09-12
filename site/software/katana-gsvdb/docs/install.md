---
meta_title: 'GSVDashboard - Documentation'
meta_image: './software/katana-gsvdb/imgs/katana-gsvdb-cover.jpg'
description: 'A Katana Supertool for previewing and editing GSV in the node graph.'
---

<link rel="stylesheet" href="../../katana-gsvdb.css">

# installation

## pre-requisites

Tested on Katana 3.6v5, 4.0v2 and 4.5v1, no guarantee it works on lower
versions (but it should).

## steps

Download the GSVDashboard GitHub repository at any temporary location

=== "Windows"

    ```
    D:\downloads\
        GSVDashboard\
            README.md
            package.json
            ...
    ```

=== "Linux"

    ```
    /d/downloads/
        GSVDashboard/
            README.md
            package.json
            ...
    ```

Move the internal `GSVDashboard` directory (which have a .py file inside) to
the `SuperTools` directory of a location registered by the `KATANA_RESOURCES`
env variable.

=== "Windows"

    ```
    D:\pipeline\katana\
        GSVDashboard\
            SuperTools\
                GSVDashboard\
                    __init__.py
                    ...
    ```

=== "Linux"

    ```
    /d/pipeline/katana/
        GSVDashboard/
            SuperTools/
                GSVDashboard/
                    __init__.py
                    ...
    ```

Your launcher script for Katana could then look like:

=== "Windows"

    ```batch
    "GSVDB_ROOT=D:\pipeline\katana\GSVDashboard"
    set "KATANA_RESOURCES=%KATANA_RESOURCES%;%GSVDB_ROOT%"
    ```

=== "Linux"

    ```shell
    GSVDB_ROOT="/d/pipeline/katana/GSVDashboard"
    export KATANA_RESOURCES="$KATANA_RESOURCES:$GSVDB_ROOT"
    ```


