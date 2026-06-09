# CTftpReadFileManager::Shutdown(void)

- ea: `0x1800094bc`
- end: `0x18000960c`
- name: `?Shutdown@CTftpReadFileManager@@QEAAKXZ`
- size: `336`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180001754`
- `0x180005c50`

## callees

- `0x180002ccc`
- `0x180002f8c`
- `0x180002ff4`
- `0x180005850`
- `0x1800094bc`
- `0x180009614`
- `0x18000a68c`
- `0x18000a800`
- `0x18000a960`
- `0x18003c514`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009566`
- `KERNEL32!EnterCriticalSection` at `0x180009566`
- `KERNEL32!LeaveCriticalSection` at `0x1800095ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800095ce`

## string_xrefs

- `0x180009555`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`

## pseudocode

```c

```
