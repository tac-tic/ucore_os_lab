Notice 1:

For the reason that different processes share the same virtual memory address range, pages swapped by different processes may be set on the same disk sections. To avoid this, a bitmap for swapfs should be stored on the first few sections of disk. The swapfs_write should scan the bitmap for the vacant sections to hold the swapping page.

Notice 2:

Add a component of terminal to kernel.