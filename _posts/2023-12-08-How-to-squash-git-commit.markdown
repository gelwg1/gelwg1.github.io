---
layout: post
title:  "How to squash Git commit"
date:   2023-12-08 12:14:12 +0700
categories: [Git]
---

To combine multiple commit into one, use Squash: 
git rebase -i <after-this-commit> 
A vim window will open with a list of your previous commits.
Replace "pick" on with "squash" or "s" of all the commits there except for the first one.

In this example, <after-this-commit> is either the SHA1 hash or the relative location from the HEAD of the current branch from which commits are analyzed for the rebase command. For example, if the user wishes to view 5 commits from the current HEAD in the past the command is git rebase -i HEAD~5. 
If <after-this-commit> is SHA1 hash, it will start listing all commits after this one (means that this one is not include)

After everything done, push it with force flag: git push -f

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
