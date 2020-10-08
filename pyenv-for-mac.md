## Setting up a Python environment on MacOS with `pyenv`
### Getting started: set up Homebrew
Homebrew is a package manager for MacOS roughly analogous to `apt-get` in Linux. You can use it to install many different useful packages outside of this set of instructions. If you already have Homebrew, skip this section.

To install Homebrew, run:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Alternatively, see installation instructions [here](brew.sh).
Once you have it installed, run `brew update`. This probably isn't necessary but do it for fun anyway.
### Install and set up `pyenv`
1. If you haven't yet, run `brew update`
2. Run `brew install pyenv`
3. Run the following command, which will add `pyenv init` to your shell:
```
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
```
