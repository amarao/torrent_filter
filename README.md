torrent_filter
==============

Allow to filter torrent files based on content of the files 'inside' torrent:
* Size
* Number
* availability of directories

Usage:

ls *.torrent|torrent_filter [-q] [-D] [-N X] [-S Y]|read_torrents_files_from_stdin_and_use_them

It read torrent files list from stdin, check evry file for criteria:
* It is valid torrent file (always)
* It is has no directories (-D option)
* It contains less then X files (-N option)
* Summary size of all files is less then Y (-S option)

For the -S option postfixes can be used: 
K, M, G, T (counted as power of 1024) or 
kb,mb,gb,tb (counted as power of 1000).

Passed checking files are printed to stdout, all not passed - to stderr (or skipped if -q is used)

Why?
====
Bad guys posing huge files (sometimes over 100GB) in their torrent-rss feeds. This eats my HDD space very fast and i'm annyed enough to write this utility to save <s>trees</s> hard drives.
