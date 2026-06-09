# SetWindowsHookExAW

- ea: `0x180050c80`
- end: `0x180050d9a`
- name: `SetWindowsHookExAW`
- size: `282`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, __int64 (*)(int, unsigned __int64, __int64)@<rdx>, HMODULE hModule@<r8>, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180050c40`
- `0x180050c60`

## callees

- `0x180050c80`
- `0x18007471c`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserSetWindowsHookEx` at `0x180050d3a`
- `win32u!NtUserSetWindowsHookEx` at `0x180050d3a`
- `ntdll!RtlInitUnicodeString` at `0x180050d1c`
- `ntdll!RtlInitUnicodeString` at `0x180050d1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180050cc6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180050cc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050d62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050d62`

## pseudocode

```c

```
