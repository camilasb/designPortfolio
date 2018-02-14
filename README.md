GitBook Starter
====================
This repository contains a minimal boilerplate for creating a statically hosted GitBook on GitHub Enterprise. To begin using this boilerplate, simply fork this repository.

Prerequisites
============
* Install git. On Windows, ensure that Git Bash is installed, which is normally included with the Windows Git installer. Use Git Bash when running any commands in this README.

Initial Setup
=================
1. Clone Repository
2. Install yarn package manager 
3. Install gitbook-cli globally `yarn global gitbook-cli`
4. Install dependencies `yarn install`
5. gitbook install at the root

Configuring your GHE repository to enable GitHub Pages
=======================================================
1. Go to settings. For example, the settings for this repository would be located here:
```
https://github.ibm.com/nguyenal/gitbook-starter/settings
```
2. Scroll to the GitHub Pages section
3. Set Source to master branch / docs folder

Usage
======

Serve GitBook locally and watch for changes
--------------------------------------------
This is the primary way to develop documentation with GitBook. The development server will update automatically when changes are made.
```
$ gitbook serve
```

The default URL for the development server is:
```
http://localhost:4000
```

Build static files
--------------------
This is used for generating static HTML/CSS/JS files from markdown notation. We build into the docs folder, because this is where we serve the page from in GHE.
```
$ gitbook build . docs
```

Publish changes to GitHub Pages
-------------------------------
After building, we can just commit the entire directory to commit all of our changes, including the statically generated page from the build command.
```
$ gitbook install (only necessary the first time)
$ gitbook build . docs
$ git add .
$ git commit -m 'my message'
$ git push origin master
```

Known Issues
==================
If you are receiving the following error:
```
Error: Error watching file for changes: EPERM
```
This means gitbook is having trouble updating files. It is possible that your editor has a lock on the directory, so try closing the editor, running `gitbook serve` and then loading the editor again.

Further References
=====================
* Gitbook examples and documentation: https://toolchain.gitbook.com/
* Basic gitbook-cli commands: https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md
