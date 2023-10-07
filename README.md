<p align="center">
<img src="https://github.com/Amourspirit/ooodev-gui-win/assets/4193389/8528a2bb-2658-4c76-a40e-fd7317b530dc" alt="OooDev Logo" width="174" height="174">
</p>

# LibreOffice Extension - OooDev GUI Automation for Windows

This is a LibreOffice Extension project for the [ooo-dev-tools-gui-win] python package.

## Introduction

Although the LibreOffice API gives access to many parts of the LibreOffice application, it does not give access to everything. This project is an extension that allows access to the GUI. This project a set of python modules to automate the LibreOffice GUI. At its simplest it allows you to send mouse and keyboard actions to windows dialogs and controls.

[ooo-dev-tools-gui-win] python package can be pip installed; However, this can be cumbersome that is the reason for this project. See [Pip & Virtual Environments](https://python-ooo-dev-tools.readthedocs.io/en/latest/guide/virtual_env/index.html).

This project uses [ooo-dev-tools-gui-win], [ooo-dev-tools](https://pypi.org/project/ooo-dev-tools/) (OooDev) and  [pywinauto](https://pypi.org/project/pywinauto/) python packages. This by installing this extension you will also install these packages and get access to their functionality.

For an example see [Impress append Slides to existing slide show](https://github.com/Amourspirit/python-ooouno-ex/tree/main/ex/auto/impress/odev_append_slides) on [Live LibreOffice Python UNO Examples](https://github.com/Amourspirit/python-ooouno-ex#readme)

See Also:

- [OOO Development Tools - Part 3: Draw & Impress](https://python-ooo-dev-tools.readthedocs.io/en/latest/odev/part3/index.html)
- [OooDev GUI Automation for Windows](https://ooo-dev-tools-gui-win.readthedocs.io/en/latest/index.html).

## Install Notes

Because this extension installs python packages that require some compiling, it may, depending on what packages are not yet installed, take a few minutes to install on first startup. After initial install there is no delay to LibreOffice startup.

The extension will install the packages in the user's python environment. If the user does not have a python environment, one will be created. If the LibreOffice python environment does not exist, one will be created.

A log file can be found in the LibreOffice user directory. The log file is named `ooodevguiwin_install.log`. The log file will contain information about the installation and any errors that may have occurred.

The LibreOffice user folder is usually located at `C:\Users\<user>\AppData\Roaming\Python\Python38\site-packages` where `<user>` is the user name. Also there is an environment variable `ORG_OPENOFFICE_EXTENSIONS_OOODEVGUIWIN_LOG_FILE` that can be used to find the path of the log file.

## Example Macro

This example is a macro that will toggle the status bar in Writer by sending a key combination to the GUI.

```python
# coding: utf-8
from __future__ import unicode_literals, annotations

from odevgui_win.robot_keys import RobotKeys
from odevgui_win.class_args.send_key_info import SendKeyInfo
from odevgui_win.keys.writer_key_codes import WriterKeyCodes
from ooodev.macro.macro_loader import MacroLoader

def toggle_status(*args, **kwargs):
    with MacroLoader():
        RobotKeys.send_current(SendKeyInfo(WriterKeyCodes.TOGGLE_STATUS_BAR))

g_exportedScripts = (toggle_status,)
```

See Also:
- [OooDev - Loading for Macro Execution](https://python-ooo-dev-tools.readthedocs.io/en/latest/odev/part1/chapter02.html#loading-for-macro-execution)
- [OooDev - MacroLoader](https://python-ooo-dev-tools.readthedocs.io/en/latest/src/macro/index.html#ooodev.macro.MacroLoader)

[ooo-dev-tools-gui-win]:https://pypi.org/project/ooo-dev-tools-gui-win/
