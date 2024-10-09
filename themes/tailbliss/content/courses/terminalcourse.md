---
title: "Conquering the Terminal"
date: 2024-09-02T16:22:36+08:00
draft: false
language: en
featured_image: ../assets/images/featured/command-line.png
display_image: true
summary: A know-nothing introduction to the terminal and basic commands to get you started
description: 
author: Cooper
authorimage: ../assets/images/global/author.webp
categories: Courses
tags: ["Course", "ECE1181"]
---
# Overview
If you have never worked with the Command Line before, it can seem very daunting at first. Even if you have been coding for years, your first experience with the Command Line can be a shocking reality check into just how deep the CS Iceberg goes.

Right now, everything may seem like a jumble of letters, commands, and confusing sequences, but the Command Line is made to be logical. You don't need to memorize everything. In fact, **you will only need to know about 5-6 commands to be successful in most classes.** Any additional commands will probably need to be looked up in the moment, as many have very specific input parameters.

# Terminology
Before we dive into the exact commands, it is important to know what the Command Line is, and how it differs from the Terminal, Shell, and Console.

Most people use these four terms interchangeably. And, to be fair, they are very similar. If you confuse them, don't worry, people will still know what you are talking about, and they all refer to the same thing. So here is the layman definitions of these interfaces:
### Console
The console was originally the only way to access a computer. It refers to the physical components that let you interact with the device. Technically, your keyboard and mouse are part of the console, since you use them to interact with your screen. Nowadays, people usually refer to the console like a Terminal or a way for the computer to show you information (like the console in VSCode).
### Terminal
The terminal is an app on your computer that gives you access to the Shell. All computers have a Terminal app installed by default.
### Shell
The shell is the actual computer part of the console. It is what reads, processes, and executes commands. It is generally considered the "core" of the console/terminal/command-line system.
### Command Line / CLI
The Command Line, or CLI (for Command Line Interface) is the place in the shell where you input commands. It generally has the character `>` or `$` preceding it to show where to type, as well as listing the current directory. You will often hear that a piece of software has "Command Line Interface/CLI", which just means you can interact with the app through the command line.
### WSL (Windows Subsystem Linux)
Most popular commands originally stem from the Linux operating system. Mac uses these commands, which simplifies the Terminal quite a bit. However, Windows computers don't use these same commands (besides a few of the most basic ones, including the ones below). Thus, to streamline the process, it is highly suggested that you download [WSL](https://learn.microsoft.com/en-us/windows/wsl/install). This is a new terminal for your computer that runs on a Linux system so you can use all the native Linux commands. When you want to use it, be sure to launch the "WSL" app and not the "PowerShell" or "Terminal" apps.


# Entering the Terminal
So, now that you know what the Command Line is, let's move on to how to use it. 

For the first interactive part of this lab, go ahead and open up `Terminal` if you are on Mac, or `Windows PowerShell` if you are on Windows. These come preinstalled on your computer, and they can be found with the search bar.

You should see a line that looks like this if you are on Windows (it will look similarly, but not exactly the same on Mac):

```
C:\Users\YourName>
```

where `YourName` is the name of your computer.

This line is called the "prompt." It will show up before every line that you type (sometimes it will show different text, and that's okay! It just means you are in a different place). If the command line does not have a prompt, then that means it is loading or processing a big command. Give it a few seconds and it should pop up again.

# Viewing Directories and Files
When you open up the command line, you are placed in something called a **directory**. <u>A directory is just a fancy name for a folder.</u> You usually start in the Home directory, which you can find on your computer in the File Explorer (or Finder on Mac). The home directory is the base folder your computer uses as reference. It is the directory your computer opens when first opening the Command Line. 

## Viewing Directories

To see what directory you are in, type out `pwd` and click Enter.

---
### Command
`pwd` — Displays the name of the current directory. It stands for Print Working Directory.

---

Congratulations! You just executed your first Linux command! You should see something that looks like this (may look slightly different for Mac):
```
PS C:\Users\YourName> pwd

Path
----
C:\Users\YourName


PS C:\Users\YourName>
```
If you get a red error message instead, don't worry. Odds are you are just using a command line without Linux commands installed. If you are on Windows, make sure you are in POWERSHELL, not TERMINAL. If that still doesn't work, check out the [WSL (Windows Subsystem Linux)](#wsl-windows-subsystem-linux) section for more info.

So, what just happened? Basically, you used the Command Line to tell the computer that you wanted the name of your current directory/folder. The computer processed your request (the `pwd` command), and printed out the result. Then, it opened up the command line again and waited for a new command (which is why you see the C:\\\\ line at the bottom). 

## Viewing Files
Now, let's see what is inside the current directory (you can always check what the "current directory" is using the `pwd` command). To list the files in the current directory, use the `ls` command.

---
### Command
`ls` — Displays the contents of the current directory. It is short for "LiSt" (as in "list" the files).

---

You should see something like this (may vary slightly on Mac):

```
Mode                 LastWriteTime         Length Name
\----                 -------------         ------ ----
d-r---          3/2/2023   6:49 PM                Contacts
d-r---         1/31/2024  12:26 AM                Desktop
d-r---         1/24/2024   8:59 PM                Documents
d-r---         2/11/2024   6:19 PM                Downloads
d-r---          3/2/2023   6:49 PM                Favorites
```

(But yours will likely include many more files)

The `ls` command is going to be your favorite and most used command from now on. It will help you navigate through directories, find out where you are, and display useful information about files.

Here are some important things to note about using `ls`. If you are using `Windows PowerShell` and not `WSL`, then some of these next notes won't apply to you. I highly suggest making the switch so you can practice seeing these things. Here are some important notes about how `ls` displays files with color coding:
- Blue — Directory
- White/Black — Code file
- Green — Executable

## Changing Directories

Odds are, when you used the `ls` command in your home directory, your `Downloads` file was displayed in blue text. That means that `Downloads` is a directory! Just like the home directory, you can enter the `Downloads` directory and see what's inside. To do that, we use the command `cd`.

---
### Command
`cd fileName` — Changes the directory that you are in. It stands for "Change Directory."

---

There is something different about the `cd` command. Instead of just typing the command, you have to add something else to the line. This other part is called an "argument" (you may recognize the term if you are familiar with functions in coding). An argument is a value that you give to the command to tell it what to do. In this case, you are giving the `cd` command the argument `fileName`, where `fileName` is the name of the directory you want to go to.

So, if you want to go to the `Downloads` folder, you would type the command:
```bash
cd Downloads
```
If it worked correctly, some things should change. First, the prompt should change from
`C:\Users\YourName`
to
`C:\Users\YourName\Downloads`

Another thing you should notice is that nothing is outputted after you enter the command. That's okay. Not all commands print out responses, but if it doesn't give you a big red error, then odds are that it worked. However, to make sure, try printing out the name of the directory. Do you remember what the command to print the name of the directory is? (Hint: it's the first one you learned).

Two important things to note:
1. You can only `cd` into directories (always listed in blue). If you try to `cd` into a code file, you will get an error.
2. If you type out the first couple letters of the file name and click `Tab`, then the Commands Line will autofill the rest of the file name. How handy! This will help you avoid making typos and speed up the process, especially for long fine names. (One thing to note is that if multiple files have the same few letters, you can keep hitting `Tab` to cycle through all of your options).

Now that you are in the `Downloads` directory, try listing out the files. Do you remember the command? (Hint: it is the second one we learned). You should get an output similar to the first example, but this time, it only lists files in the Downloads file on your computer. You can actually check this by going to File Explorer (Windows) or Finder (Mac) and comparing your results. They may not be in the same order, but you should see all the files listed there!

# Creating Directories and Files
## Creating Directories
Since we now know how to go into a directory, let's learn how to make our own. The command for creating your own directory is `mkdir directoryName`, where directoryName is what you want to call the new directory. You can call it whatever you like (or just `FirstNameLastName` for simplicity).

---
### Command
`mkdir directoryName` — Creates a directory inside the current directory. It stands for "MaKe DIRectory."

---

If you list out the files again, you should see your new, shiny blue directory among the list. Congrats! It's your very own directory. There are many like it, but this one is yours. Now, go ahead and enter into your new directory. Do you remember the command? (Hint: it is the third one we learned).


## Creating Files
Now that you're inside your new directory, try listing out the files using the command we learned. You should notice something strange: nothing gets displayed. That's because when we create a directory, it starts off empty. How sad! Let's make a file to fill our new directory. The command to make a new file is `touch fileName`, where fileName is the name of the file we want to create (including the extension, aka: .s .py .txt .mp3 etc). You can call it whatever you like (or just `myFile.txt` for simplicity).

---
### Command
`touch fileName` — Creates a code file inside the current directory. Think about it as "putting your fingerprints on a new file."

---

Beautiful! Go ahead and list the contents one more time to make sure your new file is in there (it should be in White text. If it's blue, you made a directory by mistake! Make sure to use `touch` and not `mkdir`).

## Leaving Directories
Now that you've finished making your own directory and file, let's learn how to go back up into the `Downloads` directory. If you try to use `cd Downloads`, you will see that you get an error. That's because `Downloads` is the "parent" directory. Think of it as a set of Russian Nesting Dolls, with each directory inside of each other. Each doll/directory can only see what is inside of itself, not what's above it (the "parent" doll if you will). So, to go "up" a directory, we need a special command: `cd ..` (that's two periods, to be clear)

---
### Command
`cd ..` — Go "up" one directory (to the parent directory). `..` always stands for the parent of a directory.

---

You should be back in `Downloads`! Try using the command again to get back to your Home directory (`C:\Users\YourName`). 

# Conclusion
Congratulations! You just learned all of the basic Linux commands you will need for this course! There are a few more that you will learn later on (including `ssh`), but these are the main ones and the ones you should know by heart. I'll leave you with just one more command, but this one is just for aesthetics. Entering `clear` will clear the terminal, leaving it nice and sparkly! Don't worry, this doesn't change which directory you are in, and it doesn't mess with your files. It just removes the clutter from the screen.

---
### Command
`clear` — Clear the old commands on the terminal screen. Useful to hide error messages and remove clutter.

---

That should be it for this section of Lab 0. But before you move on to the next section, check the `Downloads` folder of your computer using Finder or File Explorer. See if you can find the directory and file that you made. Now you can see how to use the Command Line to affect real files on your computer!

# What's Next?
Want to start putting your Command Line knowledge to good use? One of my favorite resources is [OverTheWire](https://overthewire.org/wargames/bandit/), which is a game built around using the terminal. Though it is mainly used to train Red Team Cybersecurity hackers, the beginner stages are a great intro to the terminal. 

I suggest working your way through at least level 8 to start feeling comfortable writing commands. You will start out with `ssh`, which lets you connect to computers other than your own. Each level has some handy resources with commands you might need. 

The point of the game is finding information on your own like a real coder. This means Googling for information, testing things that may not work, and finding out how to use commands in practice. Though we encourage you to try and find solutions on your own, there are plenty of people who are able to help you and will work through it with you step by step!

# Feedback
Please give me some feedback on this course! Things you liked, things you didn't like, things you want to see in the next one. Shoot me an email at coopershapard@duck.com with any feedback you have!