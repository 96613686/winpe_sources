# BlbFlushMountedVhds(ushort * *,ulong)

- ea: `0x140103fd4`
- end: `0x14010413f`
- name: `?BlbFlushMountedVhds@@YAJPEAPEAGK@Z`
- size: `363`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x140105850`
- `0x140105e20`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140103fd4`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x14010407f`
- `KERNEL32!FlushFileBuffers` at `0x14010407f`
- `KERNEL32!CreateFileW` at `0x14010406d`
- `KERNEL32!CreateFileW` at `0x14010406d`
- `KERNEL32!CloseHandle` at `0x14010408c`
- `KERNEL32!CloseHandle` at `0x1401040e4`
- `KERNEL32!CloseHandle` at `0x14010408c`
- `KERNEL32!CloseHandle` at `0x1401040e4`
- `KERNEL32!GetLastError` at `0x1401040cc`
- `KERNEL32!GetLastError` at `0x1401040ec`
- `KERNEL32!GetLastError` at `0x1401040cc`
- `KERNEL32!GetLastError` at `0x1401040ec`
- `ntdll!RtlGetLastNtStatus` at `0x140104096`
- `ntdll!RtlGetLastNtStatus` at `0x140104096`

## string_xrefs

- `0x140103fe9`: `rgVolumeMountedVhdPaths`

## pseudocode

```c

```
