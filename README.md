# gvim_diff
# About
View diff of each files (in vertial split) in gvim/vim diff mode. 
And, to store the diff of each files in .diff.html extension

## To use gvim/vim diff in SVN
File: svn_gvimdiff
To use gvim/vim diff instead of SVN diff

Either 

Change your $HOME/.subversion/config file to point at gvim diff script 
    diff-cmd = /path/to/svn_gvimdiff
Or 
In the terminal: 
   svn diff --diff-cmd /path/to/svn_gvimdiff

## To use gvim/vim diff in git
To add soon.
