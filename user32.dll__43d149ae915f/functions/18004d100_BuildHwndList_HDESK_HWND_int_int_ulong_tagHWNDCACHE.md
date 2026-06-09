# BuildHwndList(HDESK__ *,HWND__ *,int,int,ulong,_tagHWNDCACHE * *)

- ea: `0x18004d100`
- end: `0x18004d24e`
- name: `?BuildHwndList@@YAKPEAUHDESK__@@PEAUHWND__@@HHKPEAPEAU_tagHWNDCACHE@@@Z`
- size: `334`
- prototype: `unsigned int __fastcall(HDESK, HWND, int, int, unsigned int, struct _tagHWNDCACHE **)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004cff4`
- `0x180078a08`
- `0x180078bd8`
- `0x18008705c`
- `0x1800872a0`
- `0x18008776c`
- `0x180088c9c`

## callees

- `0x18004d100`

## import_xrefs

- `win32u!NtUserBuildHwndList` at `0x18004d160`
- `win32u!NtUserBuildHwndList` at `0x18004d243`
- `win32u!NtUserBuildHwndList` at `0x18004d160`
- `win32u!NtUserBuildHwndList` at `0x18004d243`
- `ntdll!RtlFreeHeap` at `0x18004d1a6`
- `ntdll!RtlFreeHeap` at `0x18004d1e8`
- `ntdll!RtlFreeHeap` at `0x18004d1a6`
- `ntdll!RtlFreeHeap` at `0x18004d1e8`
- `ntdll!RtlAllocateHeap` at `0x18004d1bf`
- `ntdll!RtlAllocateHeap` at `0x18004d204`
- `ntdll!RtlAllocateHeap` at `0x18004d1bf`
- `ntdll!RtlAllocateHeap` at `0x18004d204`

## pseudocode

```c

```
