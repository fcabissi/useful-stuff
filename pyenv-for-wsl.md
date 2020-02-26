## Setting up a Python environment with Windows Subsystem for Linux (WSL) and virtualenv
_Note: These instructions are valid for the first version fo WSL, and work as of 2020-02-09. I expect that things will change a bit when WSL2 is released [in the near future](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux#WSL_2)._

### Getting started: enable WSL
Follow instructions [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to enable and install WSL. If Microsoft ends up moving that, as I suspect they might, I've reproduced the instructions below.
1. Open PowerShell as Administrator and run:

`Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`

2. Restart your computer when prompted.
3. Download and install your Linux distribution of choice from the Microsoft Store. I recommend Ubuntu 18.04 LTS (or whatever the latest version is) as the default, as I've found that most of the questions I have about issues have already been answered a thousand times online.
4. Launch Ubuntu and set a username and password when prompted.
### Installing pyenv
_Note: During the following steps, answer yes to any prompts for permissions when you install these packages._
My preferred method of managing multiple versions of Python on the same system is [Pyenv](https://github.com/pyenv/pyenv). It can take some getting used to, but ultimately I have found that is produces the fewest unintended consequences on my systems.
#### Before installing pyenv
We need to do a few quick housekeeping things.
1. Run `sudo apt-get update`
2. Run `sudo apt-get install make`
3. Run `sudo apt-get install gcc`
#### Install Pyenv
Now finally, we install pyenv. If you prefer, you can find installation instructions and documentation [here](https://github.com/pyenv/pyenv).
1. Run `curl https://pyenv.run | bash`
2. Run `sudo apt-get install zlib1g-dev build-essential libsqlite3-dev sqlite3 bzip2 libbz2-dev libssl-dev openssl libgdbm-dev libgdbm-compat-dev liblzma-dev libreadline-dev libncursesw5-dev libffi-dev uuid-dev`
3. Add the following lines to the **end** of your `.bashrc`:
```
# pyenv commands
export PATH="/home/{your username}/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
4. Run `source ~/.bashrc`

pyenv is now installed in WSL.
### Installing and managing Python versions with pyenv
_For the purposes of these instructions, I will reference the current version of python, `3.8.1`_
1. Install your preferred version of Python by running `pyenv install 3.8.1`. To view a list of Python distributions available for installation, run `pyenv install -l`. The installation step can take a while depending on the age/speed of your system.
2. To set the WSL system Python version to be the version you just installed, run `pyenv global 3.8.1`.
3. Verify that the above steps executed correctly by running `python -V`. The output of that command should be the installed Python version.

That's it! You now have a clean version of Python installed on your Windows machine with WSL. To learn about more advanced commands for pyenv, [please take a look at their docs](https://github.com/pyenv/pyenv).

If you'd like to get set up with virtual environments in your new pyenv-enabled WSL, check out my instructions [here](https://github.com/fcabissi/useful-stuff/blob/master/pyenv-virtual-environments.md).
