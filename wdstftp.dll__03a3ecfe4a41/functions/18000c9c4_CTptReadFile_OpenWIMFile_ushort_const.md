# CTptReadFile::OpenWIMFile(ushort const *)

- ea: `0x18000c9c4`
- end: `0x18000cacb`
- name: `?OpenWIMFile@CTptReadFile@@AEAAKPEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000c5fc`

## callees

- `0x18000c9c4`
- `0x18000d740`
- `0x18000d84c`
- `0x18000d8dc`
- `0x18000db70`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c9d9`
- `KERNEL32!EnterCriticalSection` at `0x18000c9d9`
- `KERNEL32!LeaveCriticalSection` at `0x18000caad`
- `KERNEL32!LeaveCriticalSection` at `0x18000caad`
- `KERNEL32!GetLastError` at `0x18000ca22`
- `KERNEL32!GetLastError` at `0x18000ca22`

## string_xrefs

- `0x18000ca90`: `base\eco\wds\transport\lib\tptreadfile.cpp`

## pseudocode

```c

```
