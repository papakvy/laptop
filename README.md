<p align="center">
  <img alt="Nimble logo" src="https://assets.nimblehq.co/logo/light/logo-light-text-320.png" />
</p>

---

Laptop is a script to set up a macOS environment for web development.

The script is idempotent: It can run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

## Requirements

- macOS Sonoma (14.4) or higher

> [!NOTE]
> Both Apple Silicon and Intel are supported

Older versions may work but aren't regularly tested. This script is tested on the most recent and its previous version.

## Install

Download, review, then execute the script:

```bash
curl --remote-name https://raw.githubusercontent.com/papakvy/laptop/master/mac
less mac
bash mac 2>&1 | tee ~/laptop.log
```

Choose the additional packages when the prompts appear:

```text
Do you want to install Web's dependencies? [y|N]
```

## What it sets up

### Default

Applications:

- [Google Chrome] as the default browser
- [Postman] a collaboration platform for API development
- [Slack] for general team communication
- [VS Code] code editor

[google chrome]: https://www.google.com/chrome/
[postman]: https://www.postman.com/
[slack]: https://www.slack.com/
[vs code]: https://code.visualstudio.com/

Source Code versioning:

- [git] distributed revision control system
- [Git Large File Storage] an open-source Git extension for versioning large files
- [Github CLI] GitHub’s official command line tool

[git]: https://git-scm.com
[github cli]: https://github.com/cli/cli

Terminal:

- [iTerm2] a replacement for Terminal
- [oh-my-zsh] to spice up your shell
- [Zsh] as your shell

[iterm2]: https://www.iterm2.com/
[oh-my-zsh]: https://ohmyz.sh/
[zsh]: https://www.zsh.org/

Utilities:

- [asdf] to manage all your runtime versions with one tool
- [Bundler] for managing Ruby libraries
- [coreutils] GNU File, Shell, and Text utilities
- [gpg2] GNU Pretty Good Privacy (PGP) package
- [Homebrew] for managing operating system libraries
- [mas CLI] A simple CLI for the Mac App Store.
- [libyaml] YAML Parser

[asdf]: https://asdf-vm.com/
[bundler]: https://bundler.io/
[coreutils]: https://www.gnu.org/software/coreutils
[gpg2]: https://gnupg.org/
[homebrew]: https://brew.sh/
[mas cli]: https://github.com/mas-cli/mas
[libyaml]: https://github.com/yaml/libyaml

### Web

Tools:

- [Docker] for managing project dependencies
- [ImageMagick] for cropping and resizing images
- [Yarn] JavaScript package manager

[docker]: https://www.docker.com/community-edition
[imagemagick]: https://www.imagemagick.org/
[yarn]: https://yarnpkg.com/

Command Line Interfaces:

- [AWS CLI] official Amazon AWS command-line interface

[heroku cli]: https://toolbelt.heroku.com/

Plugins for asdf:

- [Nodejs] JavaScript runtime environment
- [Ruby] dynamic, open-source programming language with a focus on simplicity and productivity

[nodejs]: https://nodejs.org/
[ruby]: https://www.ruby-lang.org/en/

It should take less than 15 minutes to install (depending on your machine and internet speed).

### M1 incompatible dependecies

- [Keybase] to have encrypted team communication

It will omit all these dependencies above while running the script in the M1 machines.

## Customize in `~/.laptop.local`

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
#!/bin/sh

cask "dropbox"
cask "firefox"

brew "tree"
```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`,`brew_install_or_upgrade`,
and `gem_install_or_update` can be used in your `~/.laptop.local`.

See the [wiki](https://github.com/thoughtbot/laptop/wiki)
for more customization examples.

## Debugging

Your last Laptop run will be saved to `~/laptop.log`.
Read through it to see if you can debug the issue yourself.
If not, copy the lines where the script failed into a
[new GitHub Issue](https://github.com/nimblehq/laptop/issues/new) for us.
Or, attach the whole log file as an attachment.

## Contributing

Edit the `mac` file.
Document in the `README.md` file.
Follow shell style guidelines by using [ShellCheck] and [Syntastic].

```sh
brew install shellcheck
```

[shellcheck]: https://www.shellcheck.net/about.html
[syntastic]: https://github.com/scrooloose/syntastic

## License

It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[license]: LICENSE

## About

![Nimble](https://assets.nimblehq.co/logo/dark/logo-dark-text-160.png)

This project is maintained and funded by Nimble.

Inspired by the [project] of Thoughtbot.

We love open source and do our part in sharing our work with the community!
See [our other projects][community] or [hire our team][hire] to help build your product.

[project]: https://github.com/thoughtbot/laptop
[community]: https://github.com/nimblehq
[hire]: https://nimblehq.co/
