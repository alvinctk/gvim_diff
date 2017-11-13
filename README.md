# gvim_diff

## About
View diff of each files (in vertial split) in gvim/vim diff mode. 
And, to store the diff of each files in .diff.html extension
Note: Color scheme of the html file is based on your colorscheme in .vimrc file.

## 1 liner to use vim to store diff files in html.
In terminal:

     /usr/local/bin/vim -d $1 $2 -c ":TOhtml" -c ":saveas! $(basename $2).diff.html" -c ":qall!"

- $1 (or ${6} in SVN) is WAS file.
- SVN WAS FILE FORMAT [folder]/.svn/text-base/[file].svn-base
- $2 is IS file. 

To put in your alias file: 
After '\' is the end of line

hdiff(){

    /usr/local/bin/vim -d $1 $2 \
    -c ":TOhtml" \
    -c ":saveas! $(basename $2).diff.html" \
    -c ":qall!";
}

or put it in one line: 
hdiff(){  /usr/local/bin/vim -d $1 $2 -c ":TOhtml" -c ":saveas! $(basename $2).diff.html" -c ":qall!"; }

## To use gvim/vim diff instead of SVN diff
File: svn_gvimdiff
In terminal, 
     chmod 755 /path/to/svn_gvimdiff 
Next, either 

    Change your $HOME/.subversion/config file to point at gvim diff script 
          diff-cmd = /path/to/svn_gvimdiff
Or 
   In the terminal: 
          svn diff --diff-cmd /path/to/svn_gvimdiff

## To use gvim/vim diff in git
To add soon.




