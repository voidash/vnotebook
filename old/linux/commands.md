# commands

## Disk utility 

* List the size of current directory `du -h --max-depth=1 .`
* List the size of files in current directory `find -type f . -exec du -mh {} + | sort -r -n | less`
* list the condensed size of directory `du -sh .`


