# CSdSafeguard::SafeguardContainer(ushort const *,ushort const *,ushort const *,_FILETIME,int,ISdAsyncPriv *,ushort * *)

- ea: `0x180036730`
- end: `0x180036b5c`
- name: `?SafeguardContainer@CSdSafeguard@@UEAAJPEBG00U_FILETIME@@HPEAUISdAsyncPriv@@PEAPEAG@Z`
- size: `1068`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, int, struct ISdAsyncPriv *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008200`
- `0x180009c88`
- `0x180036730`
- `0x1800370d8`
- `0x180037d84`
- `0x180038058`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18007a118`
- `0x18008f5d0`
- `0x180099bb0`
- `0x18009a20c`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800cb010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180036849`
- `msvcrt!wcsrchr` at `0x180036849`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036805`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036ae9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036805`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036ae9`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180036914`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180036914`

## pseudocode

```c

```
