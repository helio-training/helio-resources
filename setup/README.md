<img src="http://i.imgur.com/UzC7XPe.png" alt="Helio Training" width="226" align="center"/> v.0.1

---------------

# System and Bootcamp Setup

These are the initial tasks to get your computer setup for 
Helio Training. We'll walk you through setting up your new
development environment step by step in class, but this is
a great reference for following along.

## Software Installation

### Terminal
#### iTerm (Mac)

1. Visit the [iTerm Downloads Page](https://iterm2.com/downloads.html)
    - Install the latest version
    
#### ConEmu (Windows)
1. Visit the [ConEmu Downloads Page](https://conemu.github.io/en/Downloads.html)
    - Install the latest version

### Git
        
#### Mac
1. The pre-installed version on MacOS is fine
    - Test that it is installed by opening Terminal and typing `git --version`
        
#### Windows
1. Windows needs to install the latest version from [here](https://git-for-windows.github.io/)
    - After installation open the program GitBash and type in `git --version`        
        
### Powerline Fonts

#### Installation
1. With iTerm2 or GitBash open type in the following:
```sh
    mkdir ~/Repos && cd ~/Repos
    git clone https://github.com/powerline/fonts powerline-fonts && cd powerline-fonts
    ./install.sh
```
2. This installs some of the most popular fonts for development patched for powerline. Which will make our terminal a little more useful later on.