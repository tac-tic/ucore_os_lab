Notice 1:

For the reason that different processes share the same virtual memory address range, pages swapped by different processes may be set on the same disk sections. To avoid this, a bitmap for swapfs should be stored on the first few sections of disk. The swapfs_write should scan the bitmap for the vacant sections to hold the swapping page.

Notice 2:

Add a component of terminal to kernel.

Notice 3:

In function vfs_open, if the result of calling vfs_lookup is not 0, then the sentences below should call vfs_lookup, whose first parameter should be the first part of path split by the last '/', to find the inode according to the first part of path. At last, vop_create should be called to create a inode according to the file which hasn't existed.

In function vfs_lookup, it should loop calling vop_lookup to parse path split by '/'.