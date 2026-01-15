10 Linux Commands 

1) To change permissions
    chmod [user] [permission] [file/directory]

2) Change ownership of a file
    sudo chown [new-owner] [file]

3) Switch user accounts
    sudo su [user]

4) Output data to the command line
    echo "[data]"

5) Redirect output to a file
    echo "[data]" > [file]      # overwrites the file
    echo "[data]" >> [file]     # appends to the file

6) To count the number of lines, words and bytes in a file
    wc [file]  #returns "[lines] [words] [bytes] [filename]"
    wc -l [filename] # number of lines
    wc -w [filename] # number of words
    wc -c [filename]            # number of bytes
    wc -m [filename]            # number of characters
    wc -L [filename]            # length of the longest line

7) Redirect input of a command from another command
    [command 1] | [command 2]   # the results of command 1 are used as input for command 2
            OR
    [command 2] < [command 1]   # same results as above

8) Sort a file
    sort [file]
    sort -n [file]              # numeric sort
    sort -r [file]              # reverse sort
    sort -f [file]              # sort regardless of capitalization
    sort -k[1...n] [file]       # sort based on column number 1...n (if data has multiple columns)
    sort [file] | uniq          # remove all duplicates
    sort [file] | uniq -c       # show the number of duplicates for each unique value

9) Extract columns from a file
    cut -d: -f[1...n] [file]    # extract column[1...n] using ':' as a delimiter
    cut -d: -f1,3 [file]        #extract columns 1 and 3

10) To build commands from input
    cat names.txt | xargs echo "Hello: "  # returns "Hello: Charlie Adam Bob Alice"
    cat names.txt | xargs -n 1 echo "Hello: " 
        #returns Hello: Charlie
                 Hello: Adam
                 Hello: Bob ...
  
