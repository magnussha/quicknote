# quicknote

USAGE: qn [OPTION] ... [FILE] ... [TEXTINPUT or SECOND FILE]
  Small bashscript for notetaking with vim.
  Stores files in ~/.quicknote, and archives to ~/Documents/QNarchive
  When executed without an option it will list all notes.
  If the first parameter is a string that is not an option, it will create a new note with that the as name.
  
   
 Options:
  
 -p Prints the note (cat).
 
 -r Reads the note (less).
  
 -d Deletes the note.
  
 -g Searches through the file for string.
  
 -a Appends text to note. Requires two parameters - name of note (first), and a string of text in quotes (second). If note does not exist, it will be created with the quoted text.
  
 -n Renames note. Requires two parameters - current name of note (first), new name of note (second).
  
 -l Prints path of note. 
  
 -b Moves note to archive folder. 
 
 -j Starts a new note with current date as name (Journal). 
  
 -k Appends line with preceeding timestamp to journal. Creates file if it does not already exist. Requires a string of text in quotes.
 
 -h Displays help.
 
 
 
 
 Autocompletion
 
 
 ```
 _qn_complete() {
    local QN_DIR=$HOME/.quicknote
    local cmd=$1 cur=$2 pre=$3
    local arr i file

    arr=( $( cd "$QN_DIR" && compgen -f -- "$cur" ) )
    COMPREPLY=()
    for ((i = 0; i < ${#arr[@]}; ++i)); do
        file=${arr[i]}
        if [[ -d $QN_DIR/$file ]]; then
            file=$file/
        fi
        COMPREPLY[i]=$file
    done
}
complete -F _qn_complete nospace qn 
```
