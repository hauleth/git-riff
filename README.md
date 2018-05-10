# Git riff

Super simple [Git hooks][git-hooks] launcher.  It doesn't manage hooks basing on
some file, it just launch them.  So this is more suitable for managing personal
set of hooks instead of managing hooks on organization level.

## Installation

Fetch [git-riff](git-riff) and run it in your repository with `install` option.
Just like this:

    ./git-riff install

And it is done.  If you have some hooks already then you can skip `git-riff` from
overwriting them by running it like that:

    yes n | ./git-riff install

If you want your hooks to be managed by `git-riff` then check out
[Usage](#usage) section.

If you do not give a damn and want to thrash all your existing hooks then this
is for you:

    yes | ./git-riff install

## Usage

`git-riff` allows you to group your hooks basing on their functionality like
that:

```
.git/
└── hooks
   ├── # unimportant stuff
   └── hooks.d
      ├── email
      │   └── pre-commit
      ├── style-check
      │   └── pre-commit
      ├── trailing-whitespaces
      │   └── pre-commit
      ├── unresolved-merge
      │   └── pre-commit
      └── wip-check
          └── pre-push
```

So you create directory named `foo` in `.git/hooks/hooks.d` and there you create
executable files that are exactly the same as any other hooks and when hook is
fired all hooks are traversed and ran.

## License

See [LICENSE](LICENSE).

[git-hooks]: https://git-scm.com/docs/githooks
