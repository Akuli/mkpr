# mkpr

This repo contains a bash script to work with GitHub pull requests.
Once installed, you can make a GitHub pull request like this:

```
$ git checkout -b new-branch-name
$ git add foo/bar/file.py
$ git commit -m "fix foobar bugs"
$ mkpr
```

This pushes your commit to GitHub and opens a browser window for creating the pull request.

This script also makes working on other people's pull requests easier.
[There are commands to do that on stackoverflow](https://stackoverflow.com/a/59704540/5806943),
but this script is more convenient.
You don't need to add every contributor as a remote, for example.
Here's how you work on pull request 123, created by someone else to a repository that you maintain:

```
$ mkpr checkout 123

...

$ git add foo/bar/file.py
$ git commit -m "Fix foobar"
$ mkpr push 123
$ git checkout main
```


## Installation

Dependencies: (you are on your own if you don't have `apt`)

```
$ sudo apt install jq curl
```

Copy or symlink the `mkpr` script to some folder on your `PATH`.
For example, if you cloned this repo to your home folder, so that you have a file `~/mkpr/mkpr`,
you could add this to your `~/.bashrc`:

```
export PATH="$PATH:$HOME/mkpr"
```
