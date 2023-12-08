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

After everything done, push it with force flag: git push -f
