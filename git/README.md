# 🌿 Git

Quick reference for everyday Git usage.

---

## Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global core.editor "vim"
git config --global init.defaultBranch main
```

---

## Everyday Commands

```bash
git status                   # show working tree status
git add .                    # stage all changes
git add -p                   # stage interactively (hunk by hunk)
git commit -m "message"      # commit with message
git commit --amend           # edit last commit (not yet pushed)
git push origin main         # push to remote
git pull --rebase            # pull and rebase instead of merge
```

---

## Branching

```bash
git branch                   # list local branches
git branch feature-x         # create branch
git switch feature-x         # switch to branch
git switch -c feature-x      # create + switch
git branch -d feature-x      # delete merged branch
git branch -D feature-x      # force delete
```

---

## Undoing Things

```bash
git restore file.txt         # discard working dir changes
git restore --staged file.txt  # unstage a file
git revert HEAD              # new commit that undoes last commit
git reset --soft HEAD~1      # undo last commit, keep changes staged
git reset --hard HEAD~1      # undo last commit, discard changes ⚠️
```

---

## Useful Aliases

Add to `~/.gitconfig`:

```ini
[alias]
  lg = log --oneline --graph --decorate --all
    st = status -s
      co = switch
        undo = reset --soft HEAD~1
          aliases = config --get-regexp alias
          ```

          ---

          ## See Also

          - [aliases.md](aliases.md) — full alias list
          - [workflows.md](workflows.md) — branching strategies
