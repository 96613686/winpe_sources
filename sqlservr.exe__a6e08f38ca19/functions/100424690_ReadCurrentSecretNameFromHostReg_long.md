# ReadCurrentSecretNameFromHostReg(long *)

- ea: `0x100424690`
- end: `0x1004247ed`
- name: `?ReadCurrentSecretNameFromHostReg@@YAPEA_WPEAJ@Z`
- size: `349`
- prototype: `wchar_t *__fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100425030`

## callees

- `0x100402880`
- `0x100424690`

## import_xrefs

- `KERNEL32!Sleep` at `0x100424751`
- `KERNEL32!Sleep` at `0x100424751`
- `KERNEL32!HeapFree` at `0x10042477f`
- `KERNEL32!HeapFree` at `0x10042477f`
- `KERNEL32!GetProcessHeap` at `0x1004246ac`
- `KERNEL32!GetProcessHeap` at `0x100424771`
- `KERNEL32!GetProcessHeap` at `0x1004247a7`
- `KERNEL32!GetProcessHeap` at `0x1004246ac`
- `KERNEL32!GetProcessHeap` at `0x100424771`
- `KERNEL32!GetProcessHeap` at `0x1004247a7`
- `KERNEL32!HeapAlloc` at `0x1004246be`
- `KERNEL32!HeapAlloc` at `0x1004247b9`
- `KERNEL32!HeapAlloc` at `0x1004246be`
- `KERNEL32!HeapAlloc` at `0x1004247b9`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x10042471c`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x10042471c`
- `hostregdll!HostReg_GetApplicationName` at `0x1004246df`
- `hostregdll!HostReg_GetApplicationName` at `0x1004246df`

## pseudocode

```c

```
