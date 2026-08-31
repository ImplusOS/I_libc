# ImplusOS I_libc

A minimal freestanding C library used by both the ImplusOS kernel and its
userland: `string.h`, `stdlib.h`, `stdio.h`, `math.h`, `errno.h`,
plus POSIX-ish headers (`unistd.h`, `fcntl.h`, `pthread.h`,
`sys/socket.h`, ...). The architecture-specific trap ABI lives in
`src/sys/{x86_64,arm64}/hal_syscall.c`.

This repository is a component of **[ImplusOS](https://github.com/ImplusOS)**,
a hobby operating system with a monolithic kernel, loadable driver modules,
a minimal freestanding C library, and a small graphical userland. It is not
meant to be built in isolation -- it is consumed as a checkout alongside
ImplusOS's other component repositories (see `Docs` for the full
architecture and `ImplusOS/Makefile` for how the pieces are wired together).

## Layout

```
I_libc/
├── libc/      All source for this component, structure preserved from ImplusOS
└── README.md  This file
```

## Build

No standalone Makefile: sources here are compiled directly by the
[Kernel](https://github.com/ImplusOS/Kernel) Makefile and by
[Userland-Common](https://github.com/ImplusOS/Userland-Common)'s
`AppCommon.mk` for userland apps.

## License

MIT, matching the parent [ImplusOS](https://github.com/ImplusOS/ImplusOS) project.
