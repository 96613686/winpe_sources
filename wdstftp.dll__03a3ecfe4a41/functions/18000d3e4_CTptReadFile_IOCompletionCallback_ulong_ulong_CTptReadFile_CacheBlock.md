# CTptReadFile::IOCompletionCallback(ulong,ulong,CTptReadFile::CacheBlock *)

- ea: `0x18000d3e4`
- end: `0x18000d569`
- name: `?IOCompletionCallback@CTptReadFile@@QEAAXKKPEAUCacheBlock@1@@Z`
- size: `389`
- prototype: `void __fastcall(char *lpCriticalSection, unsigned int, unsigned int, struct CTptReadFile::CacheBlock *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d650`

## callees

- `0x18000a960`
- `0x18000d3e4`
- `0x18003aa68`
- `0x18003ab60`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d40d`
- `KERNEL32!EnterCriticalSection` at `0x18000d40d`
- `KERNEL32!LeaveCriticalSection` at `0x18000d44e`
- `KERNEL32!LeaveCriticalSection` at `0x18000d44e`
- `KERNEL32!SetEvent` at `0x18000d53f`
- `KERNEL32!SetEvent` at `0x18000d53f`

## pseudocode

```c

```
