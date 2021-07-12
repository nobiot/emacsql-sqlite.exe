# emacsql-sqlite.exe

This repository contains a binary `emacsql-sqlite.exe` for Windows.
This is purely for convenience for [Org-roam V2](https://github.com/org-roam/org-roam) users who have trouble compiling `emacsq-sqlite.exe` on Windows on their own.

# How to Build an Executable on Your Machine

I simply did the following to build the executable. 

It's **recommended** that you try to build an executable on your own rather than use a copy of the executable hosted in this repository—It may not work on your machine unlike the one you build on your very machine.

1. Install `msys2` as instructed on its [official website](https://www.msys2.org/)
2. Within `msys2`, install `gcc` (via command `pacman -S`; the instruction on the webiste)
3. Add `msys2`'s bin directory to the environmental variable
4. On Emacs, install `emacsql-sqlite` package and start Org-roam (v2)
   Emacs starts compiling the executable automatically

Refer to the following only as your last resort when you really struggle to build the executable on your own.

# Check hash

- SHA256: 1D4129FDB22F643713640F3112B1BF209F3F9754EFDC84C3C6C8AB2D261ED8BB
- Length: 1171169
- Name: emacsql-sqlite.exe
- My machine's CPU: Intel i7-8650U 64-bit
- Windows OS 64-bit (so I believe the binary is compiled as x86-64 compatible)
- `gcc` version 10.2.0

You can use PowerShell on your Windows machine to check the hash of the file. For example, if the exe file is in your Download

```
cd  C:\Users\<username>\Downloads
Get-FileHash .\emacsql-sqlite.exe
```

# Install

Simply place the executable in the `emacsql-sqlite` folder. If you use Emacs' built-in `package.el`, it should be located somewhere under your `elpa` folder within Emacs directory like this:

```
C:\Users\<username>\emacs.d\elpa\emacsql-sqlite-20190727.1710\sqlite
```

# No guarantee, no support

I do not guarantee that it works for every Window machine. It is provided as is, and I will assume no responsibility if it does not work for you. I will not respond to any request for support.

# License of Used Software

- gcc 10.2.0 is GNU General Public License
  https://gcc.gnu.org/onlinedocs/gcc-10.2.0/gcc/Copying.html#Copying
  
- emacsql is Unlicense License
  https://github.com/skeeto/emacsql/blob/master/UNLICENSE

- sqlite is Public Domain
  https://sqlite.org/copyright.html
