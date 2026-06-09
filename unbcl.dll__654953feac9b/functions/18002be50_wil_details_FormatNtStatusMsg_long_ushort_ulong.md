# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18002be50`
- end: `0x18002bec0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002be50`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002be7a`
- `KERNEL32!GetModuleHandleW` at `0x18002be7a`
- `KERNEL32!FormatMessageW` at `0x18002beaa`
- `KERNEL32!FormatMessageW` at `0x18002beaa`

## string_xrefs

- `0x18002be73`: `ntdll.dll`

## pseudocode

```c

```
