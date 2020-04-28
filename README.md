# Cho Tools --- File and Directory Management System for UNIX User

This software is released under the MIT License; see LICENSE.txt.

## Quick Start Guide
To use this tool, paste or include the content of **for-bashrc.txt** in your .bashrc.


Register a new entry creating a new directory.
```sh
$ cd ~
$ chomkdir myProject
Title: My project
Keywords (space separated): foo bar buzz

$ chols
(a) My project (myProject)

$ chocd a
$ pwd
/path/to/home/myProject
```

You can register existing directories as well.
```sh
$ cd ~/anotherProject
$ chomkdir .
Title: Another project
Keywords (space separated): buzz fizz

$ chols
(a) My project (myProject)
(b) Another project (anotherProject)

$ chocd b
$ pwd
/path/to/home/anotherProject
```

The entries can be filtered either by dirname or keyword.
```
$ chols myProject
(a) My project (myProject)

$ chols -k foo
(a) My project (myProject)

# alias of `chols -k`
$ chogrep foo
(a) My project (myProject)

$ chogrep buzz
(a) My project (myProject)
(b) Another project (anotherProject)
```

To bring the specific directory to top of the result of `chols`, use `chotouch`.
```
$ cd anotherProject
$ chotouch .

$ chols
(a) Another project (anotherProject)
(b) My project (myProject)
```

Or, you can reorder the entries editing .cho_cache. The entries in the file will be shown as the output of `chols`.
```
$ cat .cho_cache
myProject
anotherProject
```
