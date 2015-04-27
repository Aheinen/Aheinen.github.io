---
layout: post
title:  Cheat Sheet!
date:   2015-04-09
categories: jekyll update
---
  git init-

    initialize git repository

  git status-

      how tracked changes have changed

  git add "filename"-

      adds xyz.txt  to git staging area

  git add -A.

      where dot stands for current dir. and everything after -A ensures every file name is deleted

  git reset "filename"-

      remove a file or file from staging area

  git commit -m  -

      commits/save staged changes where -m includes message

  git log-

      shows log of commitments

  git remote add "stream" "link"-

      add remote repository where "stream" is remote name and "link" is url

  git push "stream" "branch"-

      finalize committed changes by adding to online repo.

  git pull "stream" "branch"-

      Will automatically download and add modified repo "stream" to "branch"

  git diff HEAD-

     find differences from last commit

  git diff --staged-

     see staged changes

  git branch "new_branch_name"-

       creates new branch

  git checkout-

      find out which branch currently on

  git rm -r "target folder"-

      recursively  removes all files and folder from dir

  git rm *"xyz"-

      removes everything following "*"

  git clone "link"-

      create clone where "link" is url

  git merge "branch"-

      pushes fetched changes onto specified "branch"