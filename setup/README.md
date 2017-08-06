<img src="http://i.imgur.com/UzC7XPe.png" alt="Helio Training" width="226" align="center"/> v.0.1

---------------

# System and Bootcamp Setup

These are the initial tasks to get your computer setup for 
Helio Training. We'll walk you through setting up your new
development environment step by step in class, but this is
a great reference for following along or setting up a new 
machine.

Terminal
---

#### iTerm (Mac)

1. Visit the [iTerm Downloads Page](https://iterm2.com/downloads.html)
    - Install the latest version
    
#### ConEmu (Windows)
1. Visit the [ConEmu Downloads Page](https://conemu.github.io/en/Downloads.html)
    - Install the latest version

Git
---
        
#### Mac
1. The pre-installed version on MacOS is fine
    - Test that it is installed by opening iTerm and typing `git --version`
        
#### Windows
1. Windows needs to install the latest version from [here](https://git-for-windows.github.io/)
    - After installation open the program GitBash and type in `git --version`        

> The following setup is mainly for Mac/Linux systems. #SorryForWindows

Xcode Developer Tools _(Important)_
---
MacOS doesn't ship with _all_ of the software we need in order
to build and utilize certain tools and programs. In order to
get these tools the simplist way possible - we install Xcode
from the App Store. Installing it this way also gets us the
full development package for native development if you want
to go down that path.

[Download Xcode](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)

Homebrew _(MacOS Only)_
---

Homebrew is a package manager for MacOS that makes installing
common operating system programs simple and easy. 

1. With iTerm open type in the following:
```sh
# This install will prompt you for your password
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. After install you can run `brew doctor` to see if your installation was successful and if you're ready to brew.
        
ZSH Terminal Setup
---

ZSH is a standard bash shell replacement. It provides an easy 
base for creating powerful and customizable terminal shells. 
This setup is personal preference and you're free to tweak 
it how you like or skip it entirely. When we're done with the 
following steps you should have something like the picture 
below.

![ZSH-Config](http://i.imgur.com/i1Nq85t.gif)

#### Powerline Fonts
1. With iTerm open type in the following:
```sh
mkdir ~/Repos && cd ~/Repos
git clone https://github.com/powerline/fonts powerline-fonts && cd powerline-fonts
./install.sh
```
2. This installs some of the most popular fonts for development patched for powerline. Which will make our terminal a little more useful later on.

#### Terminal Color Schemes
1. With iTerm open type in the following:
```sh
# Skip this first line if you already created this folder for Powerline Fonts
mkdir ~/Repos && cd ~/Repos
git clone https://github.com/mbadolato/iTerm2-Color-Schemes
```
2. This installs some of the most popular fonts for development patched for powerline. Which will make our terminal a little more useful later on.

####
####oh-my-zsh

Oh my zsh is a great starter package for ZSH. It comes with some great plugins and makes getting started with ZSH a breeze.

1. Open up your terminal and install [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) by typing in the following in iTerm:
```sh
# This install will prompt you for your password
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
2. Your shell should change automatically to zsh when the install finishes. It won't look like the example quite yet.

####oh-my-zsh Plugins

Since ZSH is extensible we can install a couple plugins to enhance
our experience.

1. Open up iTerm and type the following (in order; one by one):
```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

####oh-my-zsh Spaceship Theme

1. Copy the contents [this file](https://raw.githubusercontent.com/denysdovhan/spaceship-zsh-theme/master/spaceship.zsh) with Cmd+C
2. Open up iTerm and type the following:
```sh
vim $ZSH/themes/spaceship.zsh-theme
```
3. This will open Vim - a terminal text editor. In order to paste
the contents of the file you copied from step one you need to 
press `i` on your keyboard to put Vim into `insert` mode. In
this case you'll press `i` and then `Cmd+v`.
4. In order to save this file we need to exit `insert` mode in
Vim and return to the `default` editor mode. In order to do that
simply press `escape`. Once we're in the `default` editor mode we
can type `:wq` which instructs vim to `write`(w) and then `quit`(q)
the `:` is simply how we pass instructions to Vim.

####oh-my-zsh Configuration
All of the configuration for ZSH lives in one file called `.zshrc`
by default when we installed `oh-my-zsh` it created this for us in
our home directory `~/.zshrc`. This file allows us to customize
our zsh shell and add functionality to it through plugins and
extensions.

1. Open up iTerm and type the following:
```sh
vim ~/.zshrc
```
2. Edit the file like the image below (theme and plugin settings):
![ZSH-Config](http://i.imgur.com/fHNFjDY.gif)

####iTerm Configuration
Now we're almost ready to take a gander at our new terminal, but
before we run the command needed to run our changes we need
to change some settings in iTerm for them to display right.

With iTerm open press `Cmd+,` - this is the Mac shortcut for 
opening preferences for the application you currently have
running.

We'll change the font first to a powerline supported font.

1. Click on the `Profiles` tab and then the `Text` tab inside of it.
2. Click the "Change Font" button and select one of the fonts that have `for Powerline` as a suffix.
    - The example on this page uses the font `Hack` which has powerline support by default
    
Next up we'll change the color scheme to give a little visual
boost to the thing we'll be staring at for some time.

1. Click on the `Profiles` tab and then the `Colors` tab inside of it.
2. Click on the dropdown at the bottom right with the `Color Presets...` placeholder and select `Import...`.
3. Navigate to your color schemes repository we downloaded earlier 
and open the `schemes` folder within it. Pick a theme you like.
    - The example on this page uses `One Dark` which isn't included in this repo. A great starting scheme I'd recommend though is `Tomorrow Night`
    
####Make It So
Alright that's it for configuring and installing, now how do we see 
our changes? Whenever you make changes to the `~/.zshrc` file
you won't see any difference until you run `source ~/.zshrc` which
tells your current shell to re-initialize with the settings file
as it stands now. After running that command you _should_ see
something close to the example image.