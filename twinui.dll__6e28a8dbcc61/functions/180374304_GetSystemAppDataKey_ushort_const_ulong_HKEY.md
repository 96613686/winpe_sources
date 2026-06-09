# GetSystemAppDataKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x180374304`
- end: `0x180374470`
- name: `?GetSystemAppDataKey@@YAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `364`
- prototype: `int(const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801333e4`

## callees

- `0x180047224`
- `0x18005f2d0`
- `0x18009f240`
- `0x18013d7f4`
- `0x18013f648`
- `0x180374304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18037433c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18037433c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18037432a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18037432a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180374420`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180374420`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18037435c`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18037435c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18037438c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1803743f6`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18037438c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1803743f6`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180374454`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180374454`

## pseudocode

```c

```
