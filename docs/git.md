# Git notes
## Using git for version control. Lessons learned.

## How To
* **Git tag**
    1. Adding a tag
        * `git tag v1.0`
        * `git push origin --tags` - push to github
    1. Deleting tags
        * `git tag -d v1.0`
        * `git push origin :refs/tags/v1.0`
* Need tags for composer

### Git Resources
#### .gitignore
* Resources
  * [.gitignore templates](https://github.com/github/gitignore)
    * Collection of .gitignore templates
  * [gitignore.io](https://www.gitignore.io/)
* Global .gitignore [Stackoverflow 7335420](http://stackoverflow.com/questions/7335420/global-git-ignore)
  * `~/.config/git/ignore` - default location
  * `git config --global core.excludesfile '~/.gitignore'` - set the location
  
### Git error message. Can't merge unrelated histories.
* Allow unrelated histories [StackOverflow Issue](http://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories)
  * `git pull remote branch --allow-unrelated-histories`

### Git error trying to push when pull seems to work

```
hint: Updates were rejected because a pushed branch tip is behind its remote
hint: counterpart. Check out this branch and integrate the remote changes
hint: (e.g. 'git pull ...') before pushing again.
```
* *Hint:* **Read hints**
  * Checkout out rejected branch. ```git checkout master```
    * ```git pull {remote} master --allow-unrelated-histories```
  * Fix conflicts and commit
    * ```git push {remote} master```

### Removing sensitive data from git after having committed [Removing Sensitive Data - Github]( https://help.github.com/articles/removing-sensitive-data-from-a-repository/)

* ```git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch {path/filename}' --prune-empty --tag-name-filter cat -- --all```
* ```git push github --force --all```
* Remove the references
  * ```git for-each-ref --format='delete %(refname)' refs/original | git update-ref --stdin```
  * ```git reflog expire --expire=now --all```
  * ```git gc --prune=now```

* No guarantee that the data hasn't been downloaded or forked but at least it's removed going forward.

### Github Markdown
* Languages for code blocks - [highlights.js](https://highlightjs.org/static/demo/)
* Emoji List - :bowtie [Emoji Cheat Sheet](http://www.webpagefx.com/tools/emoji-cheat-sheet/)