# Updte on 2023-03-11

This newly compiled Windows binary comes with SQLite support compiled in. It has been reported that it works with Org-roam. emacs-29.0.60_1-installer.exe 2023-03-10 13:25 69M

Ensure the following:

- Function sqlite-available-p returns t (to confirm that SQLite built-in support in your Emacs is available)
- Install emacs-sqlite-builtin (in addition to org-roam and its dependencies, which include emacs-sqlite)
- User option org-roam-database-connector is set to sqlite-builtin (this should be the default if you meet the conditions above)

With emacs-sqlite-builtin, you will not need to compile emacsql-sqlite.exe (effectively, the information in this page will be superseded).

# emacsql-sqlite.exe

This repository contains a binary `emacsql-sqlite.exe` for Windows.
This is purely for convenience for [Org-roam V2](https://github.com/org-roam/org-roam) users who have trouble compiling `emacsq-sqlite.exe` on Windows on their own.

# How to Build an Executable on Your Machine

I simply did the following to build the executable. 

It's **recommended** that you try to build an executable on your own rather than use a copy of the executable hosted in this repository—It may not work on your machine unlike the one you build on your very machine.

1. Install `msys2` as instructed on its [official website](https://www.msys2.org/)
2. Within `msys2`, install `gcc` (via command `pacman -S`; the instruction on the webiste)
3. On Windows, add `C:\msys64\usr\bin` (command `where gcc` in MSYS2 terminal can tell you the directory) to `PATH` in your environmental variables
4. On Emacs, install `emacsql-sqlite` package and start Org-roam (v2)
   
   Emacs will start compiling the executable automatically

Refer to the following only as your last resort when you really struggle to build the executable on your own.

# Executable I complied
As a last resort, you might have luck by using a copy of the `.exe` file I compiled.
 
## Check hash

- SHA256: E3589CFD5836C07971AE2EFB8137891C07AD747C0012C75ED058EA693D190502
- Length: 1613868
- Name: emacsql-sqlite.exe
- My machine's CPU: Intel i7-8650U 64-bit
- Windows OS 64-bit (the binary should be compiled as i686 compatible; works on my 64-bit machine too)
- Compiled with `gcc` 10.3.0 in MinGW-w64 Win32 Shell

  This way, the executable should not require `msys2.dll` according to [this](https://www.davidegrayson.com/windev/msys2/).

You can use PowerShell on your Windows machine to check the hash of the file. For example, if the exe file is in your Download

```
cd  C:\Users\<username>\Downloads
Get-FileHash .\emacsql-sqlite.exe
```

## 2021-07-28 emacsql-sqlite.exe is now compiled using the MinGW-w64 Win32 Shell 
- Source: https://www.davidegrayson.com/windev/msys2/
- This executable should not require `msys2.dll` (refer to issue #2).
- Modified make file -- see repo (I could have just called `gcc` directly)

# Install

Simply place the executable in a subfolder named `sqlite` within the `emacsql-sqlite` folder; in it, you should see source `.c` file and etc.. If you use Emacs' built-in `package.el`, it should be located somewhere under your `elpa` folder within Emacs directory like this:

```
C:\Users\<username>\emacs.d\elpa\emacsql-sqlite-20190727.1710\sqlite
```

# No guarantee, no support

I do not guarantee that it works for every Windows machine. It is provided as is, and I will assume no responsibility if it does not work for you. I will not respond to any request for support.

# License of Used Software

- gcc 10.2.0 is GNU General Public License
  https://gcc.gnu.org/onlinedocs/gcc-10.2.0/gcc/Copying.html#Copying
  
- emacsql is Unlicense License
  https://github.com/skeeto/emacsql/blob/master/UNLICENSE

- sqlite is Public Domain
  https://sqlite.org/copyright.html
