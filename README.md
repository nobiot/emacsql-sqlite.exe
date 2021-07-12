# emacsql-sqlite.exe

This repository contains a binary `emacsql-sqlite.exe` for Windows.
This is purely for convenience for [Org-roam V2](https://github.com/org-roam/org-roam) users who have trouble compiling `emacsq-sqlite.exe` on Windows on their own.

- SHA256: 1D4129FDB22F643713640F3112B1BF209F3F9754EFDC84C3C6C8AB2D261ED8BB
- Length: 1171169
- Name: emacsql-sqlite.exe

I simply did the following to build the executable.
- My machine's CPU: Intel i7-8650U 64-bit
- Windows OS 64-bit (so I believe the binary was compiled into x86-64 compatible)
- `gcc` version 10.2.0

1. Install `msys2`
2. Within `msys2`, install `gcc` (via command pacman -S)
3. Add `msys2`'s bin directory to the environmental variable
4. On Emacs, install `emacsql-sqlite` package and start Org-roam (v2)
   Emacs starts compiling the executable automatically

# Check hash

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
