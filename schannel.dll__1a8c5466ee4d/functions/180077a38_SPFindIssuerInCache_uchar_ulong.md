# SPFindIssuerInCache(uchar *,ulong)

- ea: `0x180077a38`
- end: `0x180077b02`
- name: `?SPFindIssuerInCache@@YAHPEAEK@Z`
- size: `202`
- prototype: `__int64 __fastcall(unsigned __int8 *Buf1, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180066a98`
- `0x180077920`

## callees

- `0x1800345c0`
- `0x180077818`
- `0x180077a38`
- `0x180088a48`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180077a7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180077a7c`
- `ntdll!RtlReleaseResource` at `0x180077ae9`
- `ntdll!RtlReleaseResource` at `0x180077ae9`
- `ntdll!RtlAcquireResourceShared` at `0x180077a8e`
- `ntdll!RtlAcquireResourceShared` at `0x180077a8e`

## pseudocode

```c

```
