# Linux Folder System

- [Filesystem, Hierarchy Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)

Regarding programs that you execute in your terminal, they are all found in the directories listed in your `PATH` environment variable and you can use the `which` command (or the `type` command) to check where your shell is finding a specific program.
In general, there are some conventions about where specific types of files live.   

- `/bin` - Essential command binaries
- `/sbin` - Essential system binaries, usually to be run by root
- `/dev` - Device files, special files that often are interfaces to hardware devices
- `/etc` - Host-specific system-wide configuration files
- `/home` - Home directories for users in the system
- `/lib` - Common libraries for system programs
- `/opt` - Optional application software
- `/sys` - Contains information and configuration for the system (covered in the [first lecture](/2020/course-shell/))
- `/tmp` - Temporary files (also `/var/tmp`). Usually deleted between reboots.
- `/usr/` - Read only user data
  + `/usr/bin` - Non-essential command binaries
  + `/usr/sbin` - Non-essential system binaries, usually to be run by root
  + `/usr/local/bin` - Binaries for user compiled programs
- `/var` - Variable files like logs or caches

