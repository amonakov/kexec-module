# kexec-module
Light scaffolding for building kexec as a loadable kernel module

`kernel/`: build `kexec-mod.ko` module that exposes kexec functionality as
ioctls on `/dev/kexec`.
Unlike [ford_kexec](https://github.com/chaosmaster/ford_kexec) this avoids
files that are almost, but not quite, exact copies of in-tree functionality.
Some hacks are still needed of course, but at least you can easily see what
they are. The hacks are currently tuned for 3.8 x86 and arm kernels.

`user/`: build `redir.so` that acts as an LD_PRELOAD interposer for syscall()
and reboot() libc.so calls to allow use of unpatched `kexec-tools`.
