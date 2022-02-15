# quicknote

USAGE: qn [OPTION] ... [FILE] ... [TEXTINPUT or SECOND FILE]
  <br/>Small bashscript for notetaking with vim.
 <br/> Stores files in ~/.quicknote, and archives to ~/Documents/QNarchive
 <br/> When executed without an option it will list all notes.
  <br/>If the first parameter is a string that is not an option, it will create a new note with that the as name.
  <br/>
   <br/>
 Options:
  <br/>
 -p Prints the note (cat).
 <br/>
 -r Reads the note (less).
  <br/>
 -d Deletes the note.
  <br/>
 -g Searches through the file for string.
  <br/>
 -a Appends text to note. Requires two parameters - name of note (first), and a string of text in quotes (second). If note does not exist, it will be created with the quoted text.
  <br/>
 -n Renames note. Requires two parameters - current name of note (first), new name of note (second).
  <br/>
 -l Prints path of note. 
  <br/>
 -b Moves note to archive folder. 
 <br/>
 -j Starts a new note with current date as name (Journal). 
  <br/>
 -k Appends line with preceeding timestamp to journal. Creates file if it does not already exist. Requires a string of text in quotes.
 <br/>
 -h Displays help.
