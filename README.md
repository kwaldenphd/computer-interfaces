# How Computers Work (Part 2): Software

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Overview & Goals

This lab covers a variety of topics related to how computers "work." This lab is designed to help you gain an understanding of how the operating system and other software applications interact with the underlying hardware, focusing on common core operating system tasks. Finally, this lab introduces students to the concept of a command-line interface and provides a foundation for navigating the machine using the shell.

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=ff776195-c52e-4083-b903-aef40171360f">Lecture/Live Coding Playlist</a></td>
  </tr>
  </table>

## Acknowledgements

The author consulted Chapter 10, "Operating Systems" from Nell Dale and John Lewis' *[Computer Science Illuminated, Seventh Edition](https://www.jblearning.com/catalog/productdetails/9781284155617)* textbook (Jones & Barlett Learning, 2020; ISBN: 9781284155617) when writing this lab.

The sections of this lab that involve working at the command line are based on and adapts content from the following tutorials:
- Ian Milligan and James Baker, "Introduction to the Bash Command Line," The Programming Historian 3 (2014), https://doi.org/10.46430/phen0037.
- Miriam Posner, "[Getting Started With Unix](https://github.com/miriamposner/unix/blob/main/getting_started_with_commandline.md)" tutorial

This lab's lecture segments were adapted from the following PBS *[Crash Course Computer Science](https://www.pbs.org/show/crash-course-computer-science/)* episodes:
- "[Operating Systems](https://www.pbs.org/video/operating-systems-crash-course-computer-science-18-wwc9c2/)"

# Table of Contents
- [Lecture & Live Coding](#lecture--live-coding)
- [Key Terms](#key-terms)
- [Lab Notebook Template](#lab-notebook-template)
- [Operating Systems](#operating-systems)
- [Working at the Command Line](#working-at-the-command-line)
- [Putting It All Together](#putting-it-all-together)
- [Lab Notebook Questions](#lab-notebook-questions)

## Lecture & Live Coding

Throughout this lab, you will see a Panopto icon at the start of select sections.

This icon indicates there is lecture/live coding asynchronous content that accompanies this section of the lab. 

You can click the link in the figure caption to access these materials (ND users only).

Example:

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=ff776195-c52e-4083-b903-aef40171360f">Lecture/Live Coding Playlist</a></td>
  </tr>
  </table>

## Key Terms

[Click here](https://github.com/kwaldenphd/computer-interfaces/blob/main/key-terms.md) for a full list of key terms and definitions for this lab.

## Lab Notebook Template

[Link to lab notebook template](https://docs.google.com/document/d/11zPRqQiJG_UBU3Ja6DB32oKqM_6VGXCGbjGXuzSoHR4/copy) (ND users, Google Doc)

# Operating Systems

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=5f20ce06-d598-4e9c-b5c6-aef401676d36">Operating Systems</a></td>
  </tr>
  </table>

## Key Terms

<p align="center"><img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/OS_Diagram.png?raw=true" width="500"></p>

**Operating System**
- "An operating system (OS) is system software that manages computer hardware, software resources, and provides common services for computer programs...For hardware functions such as input and output and memory allocation, the operating system acts as an intermediary between programs and the computer hardware...Operating systems are found on many devices that contain a computer – from cellular phones and video game consoles to web servers and supercomputers" ([Wikipedia](https://en.wikipedia.org/wiki/Operating_system))

Core OS tasks:
- Process management: allocates resources, executes programs, calls processes
- Memory management: allocates memory, controls memory hardware access
- File system management: interfaces with hardware to transmit, process, and store file system objects
- Device management: oversees system calls for efficient device management

Examples of specific operating systems include:
- Microsoft Windows
- MacOS/iOS
- Linux
- Android
- Chromium

<p align="center"><img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/OS_Layers.png?raw=true" width="500"></p>

**The Kernel**
- core of the OS, controls access to computer hardware, performs scheduling tasks

**Device Drivers**
- software that allows the OS to interface with hardware (graphics cards, printers, network adapters, etc.)

**Application Programming Interfaces (APIs) & Application Software**
- software that allows the user to interact with the OS

**Virtual Memory**
- An approach to managing memory that provides "an idealized abstraction of the storage resources that are actually avaialble on a given machine" (Abhishek Bhattacharjee and Daniel Lustig, *[Architectural and Operating System Support for Virtual Memory](https://link.springer.com/book/10.1007/978-3-031-01757-5).* Springer, 2017. pp. 1) 

<p align="center"><img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Computer_Terminal.png?raw=true" width="500"></p>

**Computer Terminal**
- "[a] device usually made up of a display unit and a keyboard which allows entry and display of information when on-line to central computer system" ([Wikipedia](https://simple.wikipedia.org/wiki/Computer_terminal))

**Unix**
- "a family of multitasking, multiuser computer operating systems that derive from the original AT&T Unix, whose development started in 1969 at the Bell Labs research center by Ken Thompson, Dennis Ritchie, and others" ([Wikipedia](https://en.wikipedia.org/wiki/Unix))
- [Click here](https://www.opengroup.org/membership/forums/platform/unix) to learn more about Unix and its parent organization, The Open Group.

<p align="center"><img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Personal_Computer.png?raw=true" width="500"></p>

**Personal Computer**
- "A personal computer (PC) is a multi-purpose microcomputer whose size, capabilities, and price make it feasible for individual use. Personal computers are intended to be operated directly by an end user, rather than by a computer expert or technician" ([Wikipedia](https://en.wikipedia.org/wiki/Personal_computer))

[Click here](https://github.com/kwaldenphd/computer-interfaces/blob/main/key-terms.md) for a full list of key terms and definitions for this lab.

## Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSekaVq9K2sQCJb61GqFzcVeyL5ZKfdxMvU5KCszX5-_r0bTMQ/viewform?usp=sf_link">OS Comprehension Check</a></td>
  </tr>
  </table>
  
## Application

QX: Explore your OS something something. Get your OS specs, what changed in the last update, what's coming up in the next update, what are the big changes

### Additional Resources

- Tim Bower, *[Operating Systems Study Guide](http://faculty.salina.k-state.edu/tim/ossg/index.html)* (K-State Polytechnic, 2009-2015)
- Remzi Arpaci-Dusseau and Andrea Arpaci-Dusseau, *[Operating Systems: Three Easy Pieces](http://pages.cs.wisc.edu/~remzi/OSTEP/)* (Arpaci-Dusseau Books, 2018)
- Naresh Chauhan, *Principles of Operating Systems* (Oxford University Press, 2014). [Link to access through Notre Dame Libraries](https://onesearch.library.nd.edu/permalink/f/1phik6l/ndu_aleph004609730)

# Working at the Command Line

*The Programming Historian* is a multi-language, peer-reviewed online resource with "novice-friendly, peer-reviewed tutorials that help humanists learn a wide range of digital tools, techniques, and workflows to facilitate research and teaching" (["The Programming Historian"](https://programminghistorian.org/))
 
The sections of this lab that involve working at the command line are based on and adapts content from the following tutorials:
- Ian Milligan and James Baker, "Introduction to the Bash Command Line," The Programming Historian 3 (2014), https://doi.org/10.46430/phen0037.
- Miriam Posner, "[Getting Started With Unix](https://github.com/miriamposner/unix/blob/main/getting_started_with_commandline.md)" tutorial

<p align="center"><img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Mac_GUI.png?raw=true" width="500"></p>

The usual way that computer users today interact with their system is through a Graphical-User Interface, or GUI. This means that when you go into a folder, you click on a picture of a file folder; when you run a program, you click on it; and when you browse the web, you use your mouse to interact with various elements on a webpage. Before the rise of GUIs in the late 1980s, however, the primary way to interact with a computer was through a command-line interface (CLI).

<p align="center"><img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Shell.png?raw=true" width="500"></p>

Command-line interfaces allow for more detail when running some programs, because you can add modifiers to specify exactly how you want your program to run. They can be easily automated through scripts, which are essentially recipes of text-based commands.

There are two main command-line interfaces, or "shells." On Mac OS or many Linux installations, the shell is known as `bash`, or the ‘Bourne-again shell.’ For users on Windows-based systems, the command-line interface is by default `MS-DOS-based`, which uses different commands and syntax, but can often achieve similar tasks. This tutorial provides a basic introduction to the `bash` terminal, and Windows users can follow along by installing popular shells such as Cygwin or Git Bash.

For Mac users (and most Linux installations), you’re in luck — you already have a bash shell installed. 

Windows users will need to take one extra step and install Git Bash. 
- Download the most recent ‘Full installer’ at [this page](https://git-for-windows.github.io)
- Instructions for installation are available at [Open Hatch](https://web.archive.org/web/20190114082523/https://openhatch.org/missions/windows-setup/install-git-bash)

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=a62d663b-d047-474f-abc5-aef4018603f7">Keyboards, Command-Line Interfaces & Graphical User Interfaces</a></td>
  </tr>
  </table>

## Key Terms

**Graphical User Interface (GUI)**
- "The graphical user interface (GUI) is a form of user interface that allows users to interact with electronic devices through graphical icons and audio indicator such as primary notation, instead of text-based user interfaces, typed command labels or text navigation. GUIs were introduced in reaction to the perceived steep learning curve of command-line interfaces (CLIs), which require commands to be typed on a computer keyboard" ([Wikipedia](https://en.wikipedia.org/wiki/Graphical_user_interface))

**Command Line Interface (CLI)**
- "A command-line interface (CLI) processes commands to a computer program in the form of lines of text. The program which handles the interface is called a command-line interpreter or command-line processor. Operating systems implement a command-line interface in a shell for interactive access to operating system functions or services" ([Wikipedia](https://en.wikipedia.org/wiki/Command-line_interface))

**Shell**
- The shell is the user interface for accessing all of the operating system’s services and applications. The shell is the layer of code surrounding the operating system kernel. Your operating system’s shell is the command processor that runs in the CLI (command-line interface) as opposed to the GUI interface that we typically use.

[Click here](https://github.com/kwaldenphd/computer-interfaces/blob/main/key-terms.md) for a full list of key terms and definitions for this lab.

For more background and additional information:
- [Crash Course Computer Science, "Keyboards & Command Line Interfaces"](https://nerdfighteria.info/v/4RPtJ9UyHS0/)
- [Crash Course Computer Science, "Graphical User Interfaces"](https://nerdfighteria.info/v/XIGSJshYb90/)

## Opening Your Shell

*NOTE: The following screenshots show the Mac OS terminal/shell. Folks with other operating systems should still be able to follow the procedural steps.*

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_A1.png?raw=true" alt="Image of Mac Shell icon"></p>
 
To launch the terminal...

Mac:
- By default, the shell is located in `Applications -> Utilities -> Terminal`

Windows:
- Run Git Bash from the directory that you installed it in. You will have to run it as an administrator - to do so, right click on the program and select 'Run as Administrator.'

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_A.png?raw=true" alt="Image of Mac Shell"></p>
 
When the terminal or shell is running, you will see a window that looks similar to the image above.

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_B.png?raw=true" alt="Image of Mac terminal settings"></p>
 
For Mac users who want to customize the terminal's visual appearance:
- Open the `Settings` menu (in `Preferences`, under `Terminal`)
- Click the `Settings` tab to change the color scheme

Windows users can right-click on the application's top bar and select `Properties` to open the `Properties` tab.

## Terminal Wayfinding

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_C.jpeg?raw=true" alt="Image of Mac shell"></p>

*NOTE: The following text and images are adapted from UCLA faculty member Miriam Posner's "[Getting Started With Unix](https://github.com/miriamposner/unix/blob/main/getting_started_with_commandline.md)" tutorial*

This is a terminal window, also called a `shell`. The active cursor showing up in the window is a `command prompt`. This is where you will type commands or instructions.

First, we can check your username using the `whoami` command. Type `whoami` in the shell and hit the `Enter` or `Return` key. The terminal returns your username, and the command prompt is ready for another command or instruction.

Let's try another command- this type, we'll use `echo` to repeat a set of characters in quotation marks. Type `echo 'Hello world!' into the terminal and hit the 'Enter' or 'Return' key. The `echo` command instructs the terminal to repeat whichever characters you include in the quotation marks.

## Typing Commands in the Terminal

You may have already noticed you're not able to navigate the terminal using your mouse or cursor. We can navigate the terminal using the keyboard. The `up` and `down` arrow keys let you move back (up) and forward (down) through previously typed commands. The `left` and `right` arrow keys let you move within characters or symbols for a specific command.

Press the `up` arrow once to show the previously-typed `echo` command. Then, use the `left` and `right` arrow keys to navigate to the characters within the quotation marks and replace them with another word or phrase of your choosing. Press `Return` or `Enter` to run the modified command. 

A couple other useful navigation tools:
- Press `Control` + `A` to move to the start of a line
- Press `Control` + `E` to move to the end of a line
- Type `clear` into the terminal and press `Return`/`Enter` to clear the screen
- When you're ready to close the terminal window, type `exit` and press `Return`/`Enter`

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_D.jpeg?raw=true" alt="Diagram illustrating terminal syntax"></p>

A couple notes on terminal syntax:
- `commands` tell the computer to perform an action 
- `options` modify the command and use a hyphen (`-`) symbol
  * Sometimes `options` are called `flags` or `switches`
- `arguments` specify what the command operation will be performed on (i.e. a specific file or directory)

Not all commands require arguments or options, but some commands can have one or more of each. You can also chain multiple commands together using the vertical bar `|` symbol. This is often called a `pipe`.

### Navigating Your File System

#### Key Terms

**File Manager (or File Browser)**
- "A file manager or file browser is a computer program that provides a user interface to manage files and folders. The most common operations performed on files or groups of files include creating, opening (e.g. viewing, playing, editing or printing), renaming, copying, moving, deleting and searching for files, as well as modifying file attributes, properties and file permissions. Folders and files may be displayed in a hierarchical tree based on their directory structure" ([Wikipedia](https://en.wikipedia.org/wiki/File_manager))
- Examples: Finder (Mac), File Explorer (Windows)

**File Extension (or Filename Extension)**
- "A filename extension, file name extension or file extension is a suffix to the name of a computer file (e.g., `.txt`, `.docx`, `.md`). The extension indicates a characteristic of the file contents or its intended use. A filename extension is typically delimited from the rest of the filename with a full stop (period)" ([Wikipedia](https://en.wikipedia.org/wiki/Filename_extension))

**Directory**
- "In computing, a directory is a file system cataloging structure which contains references to other computer files, and possibly other directories. On many computers, directories are known as folders" ([Wikipedia](https://en.wikipedia.org/wiki/Directory_(computing)))

**Path**
- "A path is a string of characters used to uniquely identify a location in a directory structure. It is composed by following the directory tree hierarchy in which components, separated by a delimiting character, represent each directory. The delimiting character is most commonly the slash `/`, the backslash character `\`, or colon `:`" ([Wikipedia](https://en.wikipedia.org/wiki/Path_(computing)))

**Absolute Path**
- "An absolute or full path points to the same location in a file system, regardless of the current working directory. To do that, it must include the root directory" ([Wikipedia](https://en.wikipedia.org/wiki/Path_(computing)#Absolute_and_relative_paths))

**Relative Path**
- "a relative path starts from some given working directory, avoiding the need to provide the full absolute path" ([Wikipedia](https://en.wikipedia.org/wiki/Path_(computing)#Absolute_and_relative_paths))

[Click here](https://github.com/kwaldenphd/computer-interfaces/blob/main/key-terms.md) for a full list of key terms and definitions for this lab.

Before we start moving around, let's use the `pwd` (print working directory` command to show your current location. Type `pwd` in the terminal and press `Enter` or `Return`. Your output might look something like this:
```
/Users/kwalden
```

This directory information is called a `path` (sometimes called a `file path` when dealing with specific files).
- The backslash `/` at the start of the path stands for your computer's `root`
- Subsequent slashes indicate subfolders or subdirectories

So in the `/Users/kwalden` example, the terminal is running in the `kwalden` subfolder which is located in the `Users` folder. The `Users` folder is located at my computer's `root`.

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_E.jpeg?raw=true" alt="Diagram illustrating computer directory structure"></p>

The inverted tree diagram shown above shows one example of a computer's file system.
- The `root` (top of the tree) is your computer's hard drive.
- The next set of branches are a set of folders (`directories`) that are used by everyone who uses the computer
- The `users` folder includes different specific user profiles
- The folders located under a specific username are associated with that user profile
  * These folders commonly include `Applications`, `Desktop`, `Documents`, `Downloads`, etc.

If you have ever used `File Explorer` (Windows) or `Finder` (Mac), you have navigated this tree structure using the graphical user interface (GUI). Now let's think about how we navigate this structure using the command line interface (CLI).

#### `ls`

Typically by default, your terminal will open in the folder or directory for your user profile.
- But you can check this using the `pwd` (print working directory) command

Let's see what other files and subdirectories are located in your current path by using the list command (`ls`). Type `ls` in the terminal and press `Enter`/`Return`.

<p align="center"><img align="center" src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/Fig_F.jpeg?raw=true" alt="Terminal screenshot showing directory contents"></p>

Items that are followed by a file extension (e.g. `.docx`, `.txt`, `.xlsx`, etc) are generally individual files. Items that do not have a file extension are typically subfolders or subdirectories.

#### `cd`

We can move down the tree using the `change directory` command (`cd`). Let's move from your user profile folder to the Desktop.

Type `cd Desktop` and press `Enter`/`Return`.
- You can also type `cd Desk` and press the `Tab` key (before `Enter`/`Return`) to autocomplete the command

When using the `cd` (change directory) command, we are navigating the computer's file system using `relative paths`. This means the location information we are specifying in the terminal is relative to our current position or location in the file system. The previous `cd Desktop` command is an example of a relative path. 

`Absolute paths` always start at the `root` and use backslash `/` symbols to indicate subfolders.
- `/Users/kwalden/Desktop` would be the absolute path version of the previous command
- NOTE: Be sure to replace `kwalden` with your user name

We can use the `ls` command again to see the materials located on our Desktop. We can also move back up the file system tree using the `cd` command.

Instead of using `cd` followed by a relative or absolute path, we can use `cd ..` (`cd` followed by a space and two periods) to move up one level in the tree. Type `cd ..` in the terminal and press `Enter`/`Return`. You can test using `pwd` if needed, but you should be back in the specific user profile folder.

## Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/computer-interfaces/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLScAShWrKHVdEpMv6tzRdRvzML9s3lr0gItllyyR42SMj6_QZA/viewform?usp=sf_link">CLI Comprehension Check</a></td>
  </tr>
  </table>

COMPREHENSION CHECK

describe CLI vs GUI in your own words

Describe shell in your own words

Describe/explain what these commands do:
- ls
- cd
- pwd

Difference between relative and absolute path

## Additional Resources

If you want to further explore command line syntax:
- Software Carpentries, "[The Unix Shell](https://swcarpentry.github.io/shell-novice/)" lesson
- Mary Brent, "[Linux Command Cheat Sheet](https://www.guru99.com/linux-commands-cheat-sheet.html)", *Guru99* (28 May 2022)
- Ian Milligan and James Baker, "Introduction to the Bash Command Line," The Programming Historian 3 (2014), https://doi.org/10.46430/phen0037.
- Miriam Posner, "[Getting Started With Unix](https://github.com/miriamposner/unix/blob/main/getting_started_with_commandline.md)" tutorial

## Application

QX: Describe experience working through different tasks in the previous section of the lab. How does your navigation of the computer at the command line compare other ways of navigating a computer’s user interface?

QX: When you use the ls -l (lower-case letter l, lower-case letter s, space, dash, lower-case letter l) command, can you decipher the information that is displayed? Watch https://youtu.be/exQNuYxqFpA to help decode the information.

# Lab Notebook Questions

All of the required questions are listed here for you to reference. Be sure to answer each question completely, including an explanation of how you arrived at your answer.

[Link to lab notebook template](https://docs.google.com/document/d/11zPRqQiJG_UBU3Ja6DB32oKqM_6VGXCGbjGXuzSoHR4/copy) (ND users, Google Doc)

QX: Explore your OS something something. Get your OS specs, what changed in the last update, what's coming up in the next update, what are the big changes

QX: Describe experience working through different tasks in the previous section of the lab. How does your navigation of the computer at the command line compare other ways of navigating a computer’s user interface?

QX: When you use the ls -l (lower-case letter l, lower-case letter s, space, dash, lower-case letter l) command, can you decipher the information that is displayed? Watch https://youtu.be/exQNuYxqFpA to help decode the information.
