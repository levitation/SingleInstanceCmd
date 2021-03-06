## SingleInstanceCmd
Tool for ensuring that a process specified in the arguments is launched only one at a time. Similar to the flock tool in Linux.

By default, the SingleInstanceCmd.exe tool creates also a job object, which ensures that when the SingleInstanceCmd.exe tool is killed then the child process and all of its grandchildren descending from it are also killed.

The main use case for this has been launching processes from Task Scheduler. Without this tool there are two issues with Task Scheduler:
1. When the task is manually ended via Task Scheduler, the process or its descendants was not necessarily all killed. Using a job object solves this.
2. After the task is manually ended via Task Scheduler or killed via Task Manager, the Task Scheduler may try to start multiple instances of the process concurrently.

### State 
Ready to use. Maintained and in active use.

### Usage
SingleInstanceCmd.exe mutexname [-] cmd [args]
<br>"-" indicates that no job object must be created (descending child processes will live even when SingleInstanceCmd.exe is killed)

See also example.bat for a usage example.


[![Analytics](https://ga-beacon.appspot.com/UA-351728-28/SingleInstanceCmd/README.md?pixel)](https://github.com/igrigorik/ga-beacon)
