# Linux-Filesystem-using-FUSE
The filesystem is implemented at user-level using FUSE.The filesystem can be used for creating new files,modifying files and deleting files only.The concept of directories is not implemented.The filesystem is log-structured meaning that all the modifications to the file are written onto a log and then carried out at a later stage.A log consists of a series of segments which contain data and inodes,the filesystem gathers a segement worth of data in memory and appends it to the end of th elog.This helps to achieve faster write performance while mainatining the same read performance.

To mount the filesystem onto userspace FUSE must be installed-
check with
>fusermount -V

Go to the downloaded directory Linux-Filesystem-using-FUSE  using-
>cd Linux-Filesystem-using-FUSE

Once in the directory execute the make command-
>make

Once done generate a temporary directory named 'point' in the current directory using-
>mkdir point

If make was succesfully executed then-
>./lfs point

This is done to mount the filesystem.Now the folder point will be listed as a seperate filesystem.
To test the overall filesystem one can use iozone.
To umount the Filesystem-
fusermount -u point

To Re-run/remount the filesystem,remove lfslog file-
>rm lfslog
Repeat the Steps.
