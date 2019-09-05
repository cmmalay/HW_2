
## HW_2: Pipe Problems  
This homework can be completed by editing this file with your answers.

#### For problems 1-4, use `animals.txt` (in the `data-shell/data` folder)  

__Problem 1: For the pipeline below, describe the text that passes through each of the pipes and into the final redirect (`final.txt`).__

`cat animals.txt | head -n 5 | tail -n 3 | sort > final.txt`

Hint: build the pipeline up one command at a time to test your understanding.
 ```
 This code displays the contents of the text file, prints the first 5 items of the text file and then prints the last 3 items from that list, and sorts those 3 contents and redirects them to final.txt to display them. 
```
__Problem 2: For the file _animals.txt_ from the previous exercise, the command:
`cut -d , -f 2 animals.txt` . 
uses the `-d` flag to separate each line by comma, and the `-f` flag to print the second field in each line, to give the following output:__
```
deer
rabbit
raccoon
rabbit
deer
fox
rabbit
bear
```
What other command(s) could be added to this in a pipeline to find out what animals the file contains (without any duplicates in their names)? 
```
You could write | sort | uniq after cut-d , -f 2 animals.txt to sort the contents and remove the duplicates. 
```

__Problem 3: Assuming your current directory is `data-shell/data/`, write a command with pipes to produce a table that shows the total count of each type of animal in the file__

  
d.	`cut -d, -f 2 animals.txt | uniq -c`  


### For Remaining Problem, Use HW_2/tree_data  

__Problem 4: Morgan has a directory full of tree ring measurement files that he inherited from a previous student who was poorly organized. The files are organized by a 7-character ID:__

`SSPPTTC.txt`  
S - site number  
P - plot number  
T - tree number  
C - core id (could be A, B or C)  
Ex: 130101A.txt  

Morgan is only interested in the raw data (the tree ring measurement files [`.txt`] noted by the 7-character IDs above: SSPPTTC). In addition, some of the files are too short to use and some files have data that are repeated. 

Write a line of code that will create a text file containing a list of the unique tree IDs (no repeats, no extensions) that have at least 5 lines of data. Build it up, one pipe at a time.
```
wc -l *.txt | sort -n | tail -n 25 | head -n 24 | cut -c 6-13 > Tree_ID_List.txt
```

### To Submit
1) Fork the repo
2) Clone to your machine
3) Create a new branch
4) Edit this README.md file to add your answers.  Use code blocks for code.
5) Commit changes.
6) Submit a pull request on hessllab/HW_2
