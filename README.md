# Zsh uat branch merge notifier for git

`git-branch-uat-notifier` is a Z shell function that will list recent merges into your uat git branch.
You can specify this branch by exporting the `UAT_BRANCH_NAME` variable in your `.zshrc`; otherwise it defaults to `uat`.

## How It Works

Whenever you check out a branch in git, your terminal will display any recent merges of that branch into the uat branch.

You may also call the `list_uat_merges` function directly. By default it will list the merges for the current branch; otherwise you can specify a branch name as the first argument:

```
$> list_uat_merges my_branch

my_branch merged into uat on Fri Jun 19 (abcd123)
my_branch merged into uat on Fri Jun 5 (efgh456)
```

`git-branch-uat-notifier` outputs information using pretty colors for your heightened aesthetic enjoyment.

## Requirements

* You use `zsh`
* Your have a properly configured `$fpath`

## Installation

Clone the respository somewhere.

    $ git clone git://github.com/lordzork/git-branch-uat-notifier.git ~/.zsh/plugins/git-branch-uat-notifier

Alternatively, you can create a submodule.

    $ git submodule add git://github.com/lordzork/git-branch-uat-notifier.git ~/.zsh/plugins/git-branch-uat-notifier

Add the `functions` subdirectory to your `$fpath`. This should be done in your `.zshrc`.

    $ fpath+=$HOME/.zsh/plugins/*/functions/*(N)

Make sure the function is called from your `zshrc`

    $ echo "git_branch_uat_notifier" >> ~/.zsh/.zshrc

