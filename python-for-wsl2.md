## Setting up a Python environment with Windows Subsystem for Linux (WSL) and virtualenv

_Note: In order to enable and run WSL 2, you must have Windows 10, version 2004, build 19041 or higher._

### Optional: Get Windows Terminal

While not strictly necessary, [Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/) provides a similar experience to something like iTerm on MacOS. I highly recommend downloading and installing it prior to completing the rest of these steps. You can find Windows Terminal in the Microsoft Store.

### Getting started: enable & install WSL

Follow the instructions [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10). I've reproduced an abbreviated version of those instructions below.

1.  Launch Windows Terminal as Administrator. It should open a PowerShell tab. Run the following command:

> `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`

2. Run the following command:

> `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
