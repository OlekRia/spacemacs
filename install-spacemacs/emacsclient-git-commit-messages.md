# Configure emacsclient for Git commit messages
Configure the `core.editor` property with `emacsclient` to open Emacs for editing Git commit messages (assuming you do not specify the `-m "commit message"`option to the `git` command).

You can run `emacsclient` in one of several ways (try these approaches until you find which one worked best for your operating system).

1) in the same terminal as your `git` command, preferably with Emacs persistent server running.

```shell
git config --global core.editor "emacsclient --tty"
```

2) create a new Emacs frame, if you have Emacs persistent server running.

```shell
git config --global core.editor "emacsclient --no-wait --create-frame"
```

3) open in an existing Emacs application, if you are always running Emacs.

```shell
git config --global core.editor "emacsclient --no-wait"
```

4) Running Emacs as a daemon

```shell
git config --global core.editor "emacsclient --alternate-editor"
```

Or configure an operating system environment variable called `ALTERNATE_EDITOR` as an empty string, `""`, which will call `emacs --daemon` if emacs is not running.


> #### Hint::Beware of old Emacs installs shipped with MacOSX
> If `emacsclient` is not working correctly, check to see which Emacs version it run, `SPC SPC emacs-version`.  Some MacOSX versions shipped with a very old version of Emacs (version 22).
