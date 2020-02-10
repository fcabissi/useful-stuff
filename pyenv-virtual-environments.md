## Getting started with Python virtual environments and `pyenv`
_These instructions assume you have `pyenv` installed on a Unix-like system. If you have a Windows machine, I highly recommend installing `pyenv` on WSL. I've written up some instructions for doing so [here](https://github.com/fcabissi/useful-stuff/blob/master/pyenv-for-wsl.md#setting-up-a-python-environment-with-windows-subsystem-for-linux-wsl-and-virtualenv)._
_NOTE: These instructions will reference the current version of Python as of 2020-02-09, which is Python 3.8.1. Feel free to supplement your prefered version in any of these commands._
1. Make sure that the current pyenv version is the one you want to be using by running `python -V`. To switch to your version, run `pyenv global 3.8.1`.
2. To start making virtual environments, we will want a place to keep all of them. Create a folder for virtual environments with `mkdir .virtualenvs`.
3. Install virtualenv, the package for creating virtual environments, with `pip install virtualenv`. This is the only package we will install to our base Python version.
4. Create a virtual environment in the `.virtualenvs` folder. Here, we will create an environment called `my-first-env`:
```
virtualenv ~/.virtualenvs/my-first-env
```
5. Activate your new virtual environment with `source ~/.virtualenvs/my-first-env/bin/activate`.
6. You are now in your virtual environment and can feel free to install Python packages with wild abandon!
#### Optional: A handy bash command for starting virtual environments
The command `source ~/.virtualenvs/<ENVIRONMENT NAME>/bin/activate` doesn't exactly roll off the tongue. To help with that, I created a bash command to start up virtual environments by name. Add the following code to the end of your `.bashrc`:
```
# Start virtual environments
startenv() {
    source ~/.virtualenvs/"$1"/bin/activate
}
```
Next, run `source .bashrc`. You should now be able to start up your virtual environments with the `startenv` command. For example, to start `my-first-env`, you would run `startenv my-first-env`. Note that this command only works if you have your virtual environments stored in `.virtualenvs`.
#### Even more optional: A bash command for creating virtual environments
If you don't want the hassle of having to remember to put your new virtual environments in `.virtualenvs`, add the following to the end of your `.bashrc`:
```
# Make virtual environments
mkenv() {
    virtualenv ~/.virtualenvs/"$1"
}
```
Run `source ~/.bashrc`. You can now use `mkenv` to create new virtual environments, and then start them up with the `startenv` command. For example, we would replace the command in the environment creation step above (step #4) with:
```
mkenv my-first-env
```
After creating `my-first-env`, we could then start it with `startenv my-first-env`.
