## Installfest
_Introduction_

Let's get our machines set up for the initial phase of wdi.  We will be iteratively building out a development environment throughout the course, but the basics are fairly minimal.  Most of the tools we need can be installed with `homebrew`, a package manager for OS X.

## Homebrew

[Homebrew](https://brew.sh/) is an extremely popular and easy to use package manager for macOS. This is the tool we will use to install all of the software we need for this course.

Install homebrew from the command line with the command:

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

This install script will tell you the files it will create and ask for your password. **YOUR PASSWORD WILL NOT DISPLAY**, just keep typing.

After the install, brew will print an output describing where to find more information on how to use it.

### Oh-My-Zsh!
First, we will change the default "shell" or terminal environment to use one that is more friendly for developers.

Open the `Terminal` app and type the following two commands (Hit `<Enter>` after each):
```
brew install zsh zsh-completions
```

Verify installation by running `zsh --version`. Expected result: zsh 5.1.1 or more recent.

Make it your default shell: 
```
chsh -s $(which zsh)
```

Log out and login back again to use your new default shell.
Test that it worked with 
```echo $SHELL```

Expected result: /bin/zsh or similar.

Install oh-my-zsh 
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


### Git
Let's install `git` and a nifty helper for viewing files in the command line, `tree`.


```
brew install git
brew install tree
```

### Atom

Next, let's install the `Atom` text editor.  From the terminal type the following command:

```
brew cask install atom
```

### Node

Finally, we will set up a runtime for using javascript from the terminal.  For wdi, we will use `nvm`, a version manager for the `Node` runtime.

You can install nvm with the following terminal command:
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

Copying + pasting this is strongly recommended.

Ensure that node is installed with the following commands.

```
nvm install node
nvm use node
```

### Spectacle

Spectacle is a simple utility that allows you to easily organize your windows without using a mouse.

You can install Spectacle with the following terminal command:
```
brew cask install spectacle
```

