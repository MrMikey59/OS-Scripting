# Operating Systems Command Line Options

Options for the command line will differ based on the operating system you use.  

**Convention**: DOS & other Scripting Command key words are listed in uppercase. Switches are case sensitive.

**NOTE: 💻 = comes preinstalled on the operating system.**  

# Operating Systems (OS)  
- [fswatch: file change monitor](https://github.com/emcrisostomo/fswatch)
- [Hacker](https://en.wikipedia.org/wiki/Hacker_culture)
- [Hacker Tools](https://en.wikipedia.org/wiki/Security_hacker)
- [Regular Expressions](https://regexone.com/)

Some good resources to learn about OSs:

- [MIT's 6.828 class](https://pdos.csail.mit.edu/6.828/) - Graduate level class on Operating System Engineering. Class materials are publicly available.
- Modern Operating Systems (4th ed) - by Andrew S. Tanenbaum is a good overview of many of the mentioned concepts.
- The Design and Implementation of the FreeBSD Operating System - A good resource about the FreeBSD OS (note that this is not Linux). 
- Other guides like [Writing an OS in Rust](https://os.phil-opp.com/) where people implement a kernel step by step in various languages, mostly for teaching purposes. 

#### Common command-line flags/patterns

Command-line tools vary a lot, and you will often want to check out
their `man` pages before using them. They often share some common
features though that can be good to be aware of:

 - Most tools support some kind of `--help` flag to display brief usage
   instructions for the tool.
 - Many tools that can cause irrevocable change support the notion of a
   "dry run" in which they only print what they _would have done_, but
   do not actually perform the change. Similarly, they often have an
   "interactive" flag that will prompt you for each destructive action.
 - You can usually use `--version` or `-V` to have the program print its
   own version (handy for reporting bugs!).
 - Almost all tools have a `--verbose` or `-v` flag to produce more
   verbose output. You can usually include the flag multiple times
   (`-vvv`) to get _more_ verbose output, which can be handy for
   debugging. Similarly, many tools have a `--quiet` flag for making it
   only print something on error.
 - In many tools, `-` in place of a file name means "standard input" or
   "standard output", depending on the argument.
 - Possibly destructive tools are generally not recursive by default,
   but support a "recursive" flag (often `-r`) to make them recurse.
 - Sometimes, you want to pass something that _looks_ like a flag as a
   normal argument. For example, imagine you wanted to remove a file
   called `-r`. Or you want to run one program "through" another, like
   `ssh machine foo`, and you want to pass a flag to the "inner" program
   (`foo`). The special argument `--` makes a program _stop_ processing
   flags and options (things starting with `-`) in what follows, letting
   you pass things that look like flags without them being interpreted
   as such: `rm -- -r` or `ssh machine --for-ssh -- foo --for-foo`.
   
### Android

### Linux

### Windows
- [Powershell](https://docs.microsoft.com/powershell/scripting/overview?view=powershell-7?WT.mc_id=academic-13441-cxa) 💻  
- [Command Line](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands?WT.mc_id=academic-13441-cxa) (also known as CMD) 💻  
- [Windows Terminal](https://docs.microsoft.com/windows/terminal/?WT.mc_id=academic-13441-cxa)  
- [mintty](https://mintty.github.io/)  
- [Bash](https://www.gnu.org/software/bash/manual/html_node/index.html) 💻 
- [nullsoft scriptable install system (NSIS)](http://nsis.sourceforge.net/Download) - a professional open source system to create Windows installers 

#### Folder Usage
| Folder | Description |  
| --- | --- |  
|`../`|Parent Directory – moves up one level then traverses the folders.|  
|`./`|Current “root” directory – traverses folders from this point|  

# Popular Command Line Tools
- [Git](https://git-scm.com/) (💻 on most operating systems)  
- [NPM](https://www.npmjs.com/)  
- [Yarn](https://classic.yarnpkg.com/en/docs/cli/)  

# Resources

- [ASCIINEMA](https://asciinema.org/) – record your terminal sessions  

- [Bro pages](http://bropages.org/) -   are a highly readable supplement to man pages. Bro pages show concise, common-case examples for Unix commands. The examples are submitted by the user base, and can be voted up or down; the best entries are what people see first when they look up a command.  

- [Cheat](https://github.com/cheat/cheat) - allows you to create and view interactive cheatsheets on the command-line. It was designed to help remind *nix system administrators of options for commands that they use frequently, but not frequently enough to remember.

- [cheat.sh](https://cheat.sh/) - Aggregates cheat sheets from multiple sources (including tldr-pages) into 1 unified interface.

- [devhints](https://devhints.io/) - Rico's cheatsheets are not just focused on the command-line and include a plethora of other cheatsheets related to programming.

- [eg](https://github.com/srsudar/eg) - provides detailed examples with explanations on the command-line. Examples come from the repository, but `eg` supports displaying custom examples and commands alongside the defaults.
  
- [kb](https://github.com/gnebbia/kb) - is a minimalist command-line knowledge base manager. kb can be used to organize your notes and cheatsheets in a minimalist and clean way. It also supports non-text files.

- [navi](https://github.com/denisidoro/navi) - is an interactive cheatsheet tool, which allows you to browse through specific examples or complete commands on the fly.
## [TLDR (tl;dr)](https://tldr.sh/)  
- [TLDR on GitHub]( https://github.com/tldr-pages/)  
- [TLDR Gitter channel](https://gitter.im/tldr-pages/tldr)  
- [Too Long; Didn’t Read](https://www.howtogeek.com/435266/what-does-tldr-mean-and-how-do-you-use-it/)   
- [PDF version](https://tldr.sh/assets/tldr-book.pdf).

