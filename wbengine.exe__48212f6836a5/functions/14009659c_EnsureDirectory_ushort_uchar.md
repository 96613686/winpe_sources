# EnsureDirectory(ushort *,uchar)

- ea: `0x14009659c`
- end: `0x1400967fb`
- name: `?EnsureDirectory@@YAJPEAGE@Z`
- size: `607`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400927d0`
- `0x140092a20`
- `0x1400932c4`
- `0x140095c58`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140014260`
- `0x14003c54c`
- `0x1400945d0`
- `0x1400964c4`
- `0x14009659c`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140096635`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140096635`
- `KERNEL32!DeleteFileW` at `0x140096721`
- `KERNEL32!DeleteFileW` at `0x140096721`
- `KERNEL32!CreateDirectoryW` at `0x140096778`
- `KERNEL32!CreateDirectoryW` at `0x140096778`
- `KERNEL32!GetFileAttributesW` at `0x1400966b2`
- `KERNEL32!GetFileAttributesW` at `0x1400966b2`
- `KERNEL32!GetLastError` at `0x14009663f`
- `KERNEL32!GetLastError` at `0x14009672b`
- `KERNEL32!GetLastError` at `0x140096782`
- `KERNEL32!GetLastError` at `0x14009663f`
- `KERNEL32!GetLastError` at `0x14009672b`
- `KERNEL32!GetLastError` at `0x140096782`

## pseudocode

```c

```
