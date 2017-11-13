# gvim_diff

## About
View diff of each files (in vertial split) in gvim/vim diff mode. 
And, to store the diff of each files in .diff.html extension
Note: Color scheme of the html file is based on your colorscheme in .vimrc file.

## Vim Keyboard Commands

To navigate in diff mode in vim:

 - do - Get changes from other window into the current window.
 - dp - Put the changes from current window into the other window. 
 - ]c - Jump to the next change.
 - [c - Jump to the previous change.

Without using diff command from terminal:

  - In vim, load files via either vertical (:vs) or horizontal (:sp) split
  - :diffthis to diff files from this window of files in the split.
  - :diffoff to turn off diff mode.

## 1 liner to use vim to store diff files in html.
In terminal:

     /usr/local/bin/vim -d $1 $2 -c ":TOhtml" -c ":saveas! $(basename $2).diff.html" -c ":qall!"

- $1 (or ${6} in SVN) is WAS file.
- SVN WAS FILE FORMAT [folder]/.svn/text-base/[file].svn-base
- $2 is IS file. 

To put in your alias file: 
    
    hdiff() {
         /usr/local/bin/vim -d $1 $2 \
          -c ":TOhtml" \
          -c ":saveas! $(basename $2).diff.html" \
          -c ":qall!"; 
    }


Note: "\\" is the end of line

or put it in one line: 

       hdiff() {  /usr/local/bin/vim -d $1 $2 -c ":TOhtml" -c ":saveas! $(basename $2).diff.html" -c ":qall!"; }

## To use gvim/vim diff instead of SVN diff

File: svn_gvimdiff

Retrieve files

    git clone https://github.com/alvinctk/gvim_diff.git

Updated path in svn_gvimdiff script:

      vim_path="/path/to/vim"
      default: vim_path="/usr/bin/vim"

Make script executable:,

     chmod 755 /path/to/svn_gvimdiff 


Next, either 

    Change your $HOME/.subversion/config file to point at gvim diff script 
          diff-cmd = /path/to/svn_gvimdiff
    In terminal: 
         cd /path/to/svn/working/directory
         svn diff
Or 
   In the terminal:

          svn diff --diff-cmd /path/to/svn_gvimdiff

## To use gvim/vim diff in git
TTo add soon.




