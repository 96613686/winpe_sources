# ReadWriteData

- ea: `0x180010938`
- end: `0x180010ae2`
- name: `ReadWriteData`
- size: `426`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010730`
- `0x180010b50`
- `0x180012ccc`
- `0x1800130c0`
- `0x180013308`
- `0x180013a30`
- `0x180014110`
- `0x180017994`
- `0x180017c14`
- `0x18001879c`
- `0x18001b8c4`
- `0x18001bf60`
- `0x18001da04`
- `0x18001dfe0`
- `0x18001e57c`
- `0x18001edf0`
- `0x1800226e4`
- `0x180022d7c`

## callees

- `0x18001074c`
- `0x180010938`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010abf`
- `KERNEL32!SetLastError` at `0x180010abf`
- `ntdll!RtlNtStatusToDosError` at `0x180010a86`
- `ntdll!RtlNtStatusToDosError` at `0x180010a9b`
- `ntdll!RtlNtStatusToDosError` at `0x180010a86`
- `ntdll!RtlNtStatusToDosError` at `0x180010a9b`

## pseudocode

```c

```
