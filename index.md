---
layout: default
title: Home
---

# Project Template

This is meant to be a documentation branch of a project.  I'll keep it in `~/Dropbox/ProjectDocs/projname`

## Steps to setup a the code etc

Make a [new repository](https://help.github.com/articles/create-a-repo) on [github](github.org)

Fetch to local

    cd ~/
    # or whereever we are putting the repository.  
    git clone https://github.com/jklymak/newrepo.git
    cd newrepo/

edit a file and add the file

    git add newfile

Commit:

    git commit -a -m "My new commit"

Upload:

    git push origin master

## Steps to setup the doc directory

For whatever reason github makes you create a special branch 'gh-pages' of your repository for your code to live in.  This has to be somewhere else than your code directory, which I think is a bit silly.  

    cd ~/Dropbox/ProjectDocs
    git clone https://github.com/jklymak/newrepo.git
    # clone the code directory
    cd newrepo/
    git checkout --orphan gh-pages
    git rm -rf .
    # remove everything.
    rm '.gitignore'
    # now get some content for the now empty docs directoyr
    cp -r ~/Dropbox/ProjectDocs/projecttemplate/* ~/Dropbox/ProjectDocs/newrepo
    cd ~/Dropbox/ProjectDocs/newrepo
    git add .
    git commit -a -m "First pages commit"
    git push origin gh-pages

