---
author: "YUEPENG"
title: "File Permission"
subtitle: "unix."
date: 2015-10-28T09:52:01+05:45
comments: false
tags: [tech]
---

### File Permission

The file permissions bits include an execute permission bit for file owner, group and other. When the execute bit for the owner is set to "s". This causes any persons or processes that run the file to have access to system resources as though they are the owner of the file.

When the execute bit for the group is set to "s", the set group ID bit is set and the user running the program is given access based on access permission for the group the file belongs to.

The following command:

```
chmod +s tfile
```
set the user ID bit on the file tfile

   
```
chmod g+s tfile
```
set the group ID bit on the file tfile

If the other users execute bit is not set with permission to execute, then the user ID bit set would be meaningless since only that same group could run the program anyhow.

### Directory Group Permission

If the setgid bit on a directory entry is set, files in that directory will have the group ownership as the directory.
   
---
For example, the administrator can create a group called web and add users bob and alice to the group web.
The directory /var/www/html can be created with the set GID bit set and bob and alice although in different primary groups can work in the directory and have full access to all files in that directory, but still not be able to access files in each other's primary group.
```
chmod g+s /var/www/html
```

### umask
Typically, users were primary members in a staff group, and then secondary members in auxillary groups, like 'web' in our case.
Their umask is 022, so new files would be created with 644 and 755 for directories.


{% highlight bash %}  
	chmod g+s /var/www/html
	chgrp -R web /var/www/html
{% endhighlight %}










