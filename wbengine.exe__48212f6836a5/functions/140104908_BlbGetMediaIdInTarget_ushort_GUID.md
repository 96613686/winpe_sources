# BlbGetMediaIdInTarget(ushort *,_GUID *)

- ea: `0x140104908`
- end: `0x140104b45`
- name: `?BlbGetMediaIdInTarget@@YAJPEAGPEAU_GUID@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *)`
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1400160a8`
- `0x14001fbb0`
- `0x140021210`
- `0x14004504c`
- `0x140048e00`
- `0x140049700`
- `0x14004dd70`
- `0x140102cd8`
- `0x140104348`
- `0x140104b4c`

## callees

- `0x140014260`
- `0x14008863c`
- `0x140104908`
- `0x140134d20`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140104a1f`
- `KERNEL32!ReadFile` at `0x140104a1f`
- `KERNEL32!CreateFileW` at `0x140104997`
- `KERNEL32!CreateFileW` at `0x140104997`
- `KERNEL32!CloseHandle` at `0x140104ae3`
- `KERNEL32!CloseHandle` at `0x140104ae3`
- `KERNEL32!GetLastError` at `0x1401049a6`
- `KERNEL32!GetLastError` at `0x140104a29`
- `KERNEL32!GetLastError` at `0x1401049a6`
- `KERNEL32!GetLastError` at `0x140104a29`
- `ole32!CoTaskMemFree` at `0x140104aad`
- `ole32!CoTaskMemFree` at `0x140104aad`
- `RPCRT4!UuidToStringW` at `0x140104a7a`
- `RPCRT4!UuidToStringW` at `0x140104a7a`
- `RPCRT4!RpcStringFreeW` at `0x140104ac5`
- `RPCRT4!RpcStringFreeW` at `0x140104ac5`

## pseudocode

```c

```
