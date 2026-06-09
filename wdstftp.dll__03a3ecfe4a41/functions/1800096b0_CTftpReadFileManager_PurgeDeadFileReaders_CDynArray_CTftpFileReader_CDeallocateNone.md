# CTftpReadFileManager::PurgeDeadFileReaders(CDynArray<CTftpFileReader *,CDeallocateNone> &)

- ea: `0x1800096b0`
- end: `0x180009897`
- name: `?PurgeDeadFileReaders@CTftpReadFileManager@@AEAAXAEAV?$CDynArray@PEAVCTftpFileReader@@VCDeallocateNone@@@@@Z`
- size: `487`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800098a0`

## callees

- `0x180005850`
- `0x1800096b0`
- `0x18000a68c`
- `0x18000a800`
- `0x18003c084`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800096c4`
- `KERNEL32!EnterCriticalSection` at `0x1800096c4`
- `KERNEL32!LeaveCriticalSection` at `0x18000988b`

## string_xrefs

- `0x1800097f4`: `CTftpReadFileManager::PurgeDeadFileReaders: Dead Cache Threshold is reached. Delete CTftpFileReader instance for file: %s (CacheSize = %I64u bytes).`

## pseudocode

```c

```
