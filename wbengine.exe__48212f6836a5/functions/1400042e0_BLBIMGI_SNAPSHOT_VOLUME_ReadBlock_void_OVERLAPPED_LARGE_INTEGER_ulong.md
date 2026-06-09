# BLBIMGI_SNAPSHOT_VOLUME::ReadBlock(void *,_OVERLAPPED *,_LARGE_INTEGER *,ulong *)

- ea: `0x1400042e0`
- end: `0x140004981`
- name: `?ReadBlock@BLBIMGI_SNAPSHOT_VOLUME@@QEAAEPEAXPEAU_OVERLAPPED@@PEAT_LARGE_INTEGER@@PEAK@Z`
- size: `1697`
- prototype: `unsigned __int8 __usercall@<al>(BLBIMGI_SNAPSHOT_VOLUME *__hidden this@<rcx>, void *@<rdx>, struct _OVERLAPPED *@<r8>, union _LARGE_INTEGER *@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1400020d0`
- `0x1400c1f5c`

## callees

- `0x1400042e0`
- `0x140004990`
- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c434`
- `0x1400c3d08`
- `0x1400cfb7c`
- `0x1400d0d70`
- `0x1400d0dd4`
- `0x140134cd2`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x140004687`
- `KERNEL32!GetOverlappedResult` at `0x140004805`
- `KERNEL32!GetOverlappedResult` at `0x14000491e`
- `KERNEL32!GetOverlappedResult` at `0x140004687`
- `KERNEL32!GetOverlappedResult` at `0x140004805`
- `KERNEL32!GetOverlappedResult` at `0x14000491e`
- `KERNEL32!GetLastError` at `0x140004730`
- `KERNEL32!GetLastError` at `0x1400048d1`
- `KERNEL32!GetLastError` at `0x140004730`
- `KERNEL32!GetLastError` at `0x1400048d1`
- `ntdll!RtlAreBitsSet` at `0x1400045e4`
- `ntdll!RtlAreBitsSet` at `0x14000464b`
- `ntdll!RtlAreBitsSet` at `0x1400045e4`
- `ntdll!RtlAreBitsSet` at `0x14000464b`
- `ntdll!RtlAreBitsClear` at `0x1400045ca`
- `ntdll!RtlAreBitsClear` at `0x1400045ca`

## string_xrefs

- `0x140004763`: `bytesRead == len`

## pseudocode

```c

```
