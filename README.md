## Installfest
_Introduction_

Let's get our machines set up for the initial phase of SEI.  We will be iteratively building out a development environment throughout the course, but the basics are fairly minimal. We will use the `Terminal` app that's built into Mac OS to run some of the install commands. Most of the tools we need can be installed with `homebrew`, a package manager for OS X.

## Slack, Browser And Text Editor

Slack is a cloud-based team collaboration tool. You will use this to communicate with your instructional team, classmates, and the GA staff. For consistency, our class will be using `Google Chrome` as our default browser, and our text editor of choice will be `Sublime Text`.

- [Slack](https://slack.com/downloads/mac)
- [Google Chrome](https://www.google.com/chrome/)
- [Sublime Text](https://www.sublimetext.com/)

### Sublime Text

Copy and paste the following to the terminal so that you can open files in your text editor through the command line.

```shell
ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/
```

To test, go to a file/folder and enter

```shell 
subl . 
```

#### Sublime Resources

- [Sublime Tutor](https://sublimetutor.com/)
- [Sublime Shortcuts](https://devhints.io/sublime-text)

## Homebrew

[Homebrew](https://brew.sh/) is an extremely popular and easy to use package manager for macOS. This is the tool we will use to install all of the software we need for this course.

Install homebrew from the command line with the command:

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

This install script will tell you the files it will create and ask for your password. 
**YOUR PASSWORD WILL NOT DISPLAY AS YOU TYPE**, just type your password as you normally do.

After the install, brew will print an output describing where to find more information on how to use it.

#### Brew References

- [Brew Docs](https://docs.brew.sh/)
- [Brew Cask](https://caskroom.github.io/)
- [Bash Git Prompt Install](https://github.com/magicmonty/bash-git-prompt#via-homebrew-on-mac-os-x)
- [Bonus: Brew Fonts](https://github.com/Homebrew/homebrew-cask-fonts)

## Git
Let's install `git` and a nifty helper for viewing files in the command line, `tree`.

```
brew install git
brew install tree
```

## Bash Git Prompt

After running the Homebrew install, we want to configure our `bash prompt` to display helpful Git information.

From the command line, open your `~/.bash_profile` file with Sublime Text using the command:

```shell
subl ~/.bash_profile
```

Copy & paste the following into `~/.bash_profile`:

```shell
if [ -f "$(brew --prefix)/opt/bash-git-prompt/share/gitprompt.sh" ]; then
  __GIT_PROMPT_DIR=$(brew --prefix)/opt/bash-git-prompt/share
  source "$(brew --prefix)/opt/bash-git-prompt/share/gitprompt.sh"
fi
```

Save the file and quit Sublime Text.

## Configure Git

We want to set a default name an email address that Git will use to identify our commits. We want to be sure to use the same email as the one we created our GitHub (and GitHub Enterprise) account with.

```shell
git config --global user.name "YOUR NAME HERE"
git config --global user.email YOUR_EMAIL@DOMAIN.COM
```

We will also tell Git to use Sublime Text as our default editor:

```shell
git config --global core.editor "subl -n -w"
```

#### Git Config Reference

- [Git First Time Set Up](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
- [Git Config Tutorial](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config)
- [GitHub Setting username](https://help.github.com/articles/setting-your-username-in-git/#setting-your-git-username-for-every-repository-on-your-computer)
- [GitHub Setting email](https://help.github.com/articles/setting-your-commit-email-address-in-git/)
- [GitHub about commit email](https://help.github.com/articles/setting-your-commit-email-address-in-git/)

## Node.js

We will set up a runtime for using javascript from the terminal.  For SEI, we will use `nvm`, a version manager for the `Node` runtime.

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

#### NVM Reference
- [NVM Docs](https://github.com/creationix/nvm)

## PostgreSQL

`PostgreSQL` is an open source object-relational database system that uses and extends the Structured Query Language `(SQL)`. Postgres is the only database management system we will cover in this course.

Install postgreSQL using brew command:

```shell
brew install postgresql
```

Ensure that postgreSQL is automatically started everytime you reboot your OS, run this command:

```shell
brew services start postgresql
```

To access the PostgreSQL shell in the command line client, type this command in your terminal:

```shell
psql
```

***You may get an error `psql: FATAL:  database "YOUR-USER-NAME" does not exist`.

To fix this, run this command in your terminal:

```shell
createdb `whoami`
```

#### Postgres Reference

- [Postgres Troubleshooting](https://postgresapp.com/documentation/troubleshooting.html#errors-when-connecting-to-the-postgresql-server)
- [Postgres Tutorial](http://www.postgresqltutorial.com/)
- [Postgres Docs](https://www.postgresql.org/docs/11/index.html)

## Heroku

Heroku is an application cloud platform that we will use to deploy and run our applications.

```shell
brew tap heroku/brew && brew install heroku
```

Verify your Heroku version with this command:

```shell
heroku --version
```

#### Heroku Reference
- [Heroku Getting Started](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)


## (OPTIONAL INSTALLS)

### Spectacle

Spectacle is a simple utility that allows you to easily organize your windows without using a mouse.

You can install Spectacle with the following terminal command:
```
brew cask install spectacle
```

### Spectacle Resources
- [Spectacle GitHub](https://github.com/eczarny/spectacle#keyboard-shortcuts)
