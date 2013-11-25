# Premises:

* Every project has at least one "canonical" repository. The canonical repo
  tracks the project's official history. New clones are created by cloning
  the canonical repo; the aliases below assume that the `origin` remote
  points to the canonical repo.

* Most development happens on short-lived feature branches, which are merged
  into the canonical repo's `master` branch when accepted. This merge should
  be non-fastforward, but the alias suite doesn't care.

* Developers publish _proposed_ changes to their own repositories, not to
  the canonical repository directly. The aliases below expect the user's
  personal repo to be associated with a remote named with the user's login
  name. (It's fine if this is an alias for `origin`, provided you're
  extremely careful with the `publish` alias.)

* Branches in a developer's personal repository are "unstable" and may be
  rewritten by the author. (It's up to you to communicate with your team;
  if you're working with someone on a shared feature branch, using
  `publish` will lead to obnoxious cleanup work.)

* You have `push.default` set to `simple`. (If your version of `git` doesn't
  support this option, upgrade. The default behaviour of `git push` is
  unsupportably bad.)

* You sometimes want to use normal Git commands, too. (Otherwise, why aren't
  you using `git-flow`, `tig`, or some other workflow frontend?)

# Usage:

Read the inline comments in [aliases.gitconfig](aliases.gitconfig).

# Installation:

    $ git config --global --add include.path '/path/to/aliases.gitconfig'

##  Removal:

    $ git config --global --unset include.aliases \
          '/path/to/aliases.gitconfig'
