# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140010da0`
- end: `0x140010e10`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140010da0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140010dca`
- `KERNEL32!GetModuleHandleW` at `0x140010dca`
- `KERNEL32!FormatMessageW` at `0x140010dfa`
- `KERNEL32!FormatMessageW` at `0x140010dfa`

## string_xrefs

- `0x140010dc3`: `ntdll.dll`

## pseudocode

```c

```
