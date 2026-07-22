# Project description

As part of managing authorization for a research team, I reviewed the file permissions in the /projects directory to ensure they aligned with the organization's least-privilege policy. Using ls -la, I identified files and a directory with excessive access granted to 'Other' or 'Group' users, then used chmod to correct these permissions — including restricting write access on shared files and limiting access to a sensitive archived file and a private drafts directory.

# file and directory details

Used ls -la to inspect files and directories. Verified file types, ownership, permissions, file sizes, and modification dates. Hidden files and directories were also displayed.

# permissions string

Interpreted the Linux permission string. The first character indicates the file type (- for a file and d for a directory). The remaining characters represent read (r), write (w), and execute (x) permissions for the owner, group, and others.

# file permissions

Used the chmod command to modify file permissions. Added and removed read, write, and execute permissions for different user categories, then verified the changes with ls -l.

# permissions on a hidden file

Modified the permissions of the hidden file .project_x.txt using chmod. Confirmed that the updated permissions were successfully applied by listing hidden files with ls -la.

# directory permissions

Changed the permissions of the drafts directory using chmod. Verified that the directory permissions were updated correctly and understood how directory permissions affect access and navigation.

# Summary

In this lab, I learned how to inspect file and directory information, interpret Linux permission strings, and modify permissions using the chmod command. I also practiced changing permissions for both regular and hidden files, as well as directories, and verified all changes using ls -l and ls -la.
