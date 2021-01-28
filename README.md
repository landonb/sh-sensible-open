# `sh-sensible-open`

A Debian-like `sensible-browser` that's macOS-friendly (and still works on
Linux) that defaults ``--new-window`` and offers a generic incognito option.

*Open files and URLs gracefully from the command line or Vim!*

Jump ahead for [installation](#installation) help,
or keeping reading for a little introduction.

## Overview

Call the `bin/sensible-open` command to open a file or URL
in a new browser window.

Supposing you have the executable on path, you could call, e.g.,

  ```shell
  $ sensible-open index.html
  ```

to open an `index.html` file from the current directory.

Or you could call, e.g.,

  ```shell
  $ sensible-open https://github.com/landonb/sh-sensible-open
  ```

to open this project's GitHub page.

The `sensible-open` command will use the default browser you
have picked for your user.

### Options

To open in a new tab of an existing window, add `-t` or `--tab`, e.g.,

  ```shell
  $ sensible-open -t my-file.html
  $ sensible-open https://domain --tab
  ```

To open in an incognito aka private window, add any one of the following
four options you see used in this example:

  ```shell
  $ sensible-open -p for-me-eyes-only.html
  $ sensible-open https://browser-will-not-remember --private
  $ sensible-open -i is-for-incognito.html
  $ sensible-open https://my-isp-or-vpn-still-knows --incognito
  ```

Note that you can order however you want, so use `--` if needed
to be explicit about the location, e.g.,

  ```shell
  # For a filed named '-t'.
  $ sensible-open -- -t
  ```

### Vim usage

See the Vim plugin
[dubs_web_hatch]( https://github.com/landonb/dubs_web_hatch)
which uses this project to enable a feature that lets you
open the file or URL under the cursor in a new browser window.

E.g., you might put your cursor over a file path or URL and
type `gW` to go to that address in a web browser.

## Installation

The author recommends cloning the repository and wiring its `bin/` to `PATH`.

You can also create a symlink to the executable (`sensible-open`)
from a location already on `PATH`, such as possibly `~/.local/bin`.

Or you could clone the project and run the program directly to evaluate
it first, before deciding how you want to wire it.

Alternatively, you might find that using a shell package manager, such as
[`bkpg`](https://github.com/bpkg/bpkg),
is more appropriate for your needs, e.g.,
`bpkg install -g landonb/sh-sensible-open`.

### Makefile install

The included `Makefile` can also be used to help install.

- E.g., you could clone this project somewhere and
  then run a `sudo make install` to install it globally:

  ```shell
  git clone https://github.com/landonb/sh-sensible-open.git
  cd sh-sensible-open
  # Install to /usr/local/bin
  sudo make install
  ```

- Or specify a `PREFIX` to install anywhere else, such as locally, e.g.,

  ```shell
  # Install to $USER/.local/bin
  PREFIX=~/.local/bin make install
  ```

  And then ensure that the target directory is on the user's `PATH` variable.

  You could, for example, add the following to `~/.bashrc`:

  ```shell
  export PATH=$PATH:$HOME/.local/bin
  ```

### Manual install

If you clone the project and want the command to be callable in
your shell, remember to ensure that it can be found on `PATH`, e.g.,

  ```shell
  git clone https://github.com/landonb/sh-sensible-open.git
  export PATH=$PATH:/path/to/sh-sensible-open/bin
  ```

### Usage

  ```shell
  sensible-open [-p|--private|--incognito] [-t|--tab] <path-or-URL>
  ```

Enjoy!

