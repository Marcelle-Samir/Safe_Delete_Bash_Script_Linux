# Safe_Delete_Bash_Script_Linux

## Summary:

The goal of this script is Implementing as a script, a "safe" delete command, sdel.sh. 
Filenames passed as command-line arguments to this script are not deleted, but instead gzipped if not already compressed (use file to check), then moved to a ~/TRASH directory. Upon invocation, the script checks the ~/TRASH directory for files older than 48 hours and permanently deletes them.

- the script periodically invoked by the “cron” daemon
- it can handle files and directories recursively. This would give it the capability of "safely deleting" entire directory structures.

**Common bugs you need to take care of:**

- The script should create only 1 TRASH directory in the home directory for the user who is currently using it.
- The script shouldn’t compress a file if it is already compressed(Hint: don't rely on filenames for that check)
- Make sure that ur script is portable (e.g. don't use smth like /home/ahmed/....)
- If i passed multiple files or directories to the script it should handle each one alone and provide a zipped file for each entry

**Test Scenarios:**

- Call the script with single parameters and multiple parameter
- The input parameters can be files and/or directories
