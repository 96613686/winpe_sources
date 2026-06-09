# CRegAccount::GetAccountNameFromResourceFile(ushort *,ulong,uint,ushort *,ulong,uint)

- ea: `0x180023c94`
- end: `0x180023e5a`
- name: `?GetAccountNameFromResourceFile@CRegAccount@@CAJPEAGKI0KI@Z`
- size: `454`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, DWORD dwMessageId, unsigned __int16 *, unsigned int, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800227f4`

## callees

- `0x180002584`
- `0x180023c94`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180023d59`
- `KERNEL32!lstrlenW` at `0x180023de6`
- `KERNEL32!lstrlenW` at `0x180023d59`
- `KERNEL32!lstrlenW` at `0x180023de6`
- `KERNEL32!FormatMessageW` at `0x180023d2e`
- `KERNEL32!FormatMessageW` at `0x180023dbe`
- `KERNEL32!FormatMessageW` at `0x180023d2e`
- `KERNEL32!FormatMessageW` at `0x180023dbe`

## string_xrefs

- `0x180023dcb`: `Account used for running the ASP.Net tasks`

## pseudocode

```c

```
