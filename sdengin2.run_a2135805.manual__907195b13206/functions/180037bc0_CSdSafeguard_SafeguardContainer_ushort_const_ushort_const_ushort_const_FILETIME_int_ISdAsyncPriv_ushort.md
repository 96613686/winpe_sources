# CSdSafeguard::SafeguardContainer(ushort const *,ushort const *,ushort const *,_FILETIME,int,ISdAsyncPriv *,ushort * *)

- ea: `0x180037bc0`
- end: `0x180038005`
- name: `?SafeguardContainer@CSdSafeguard@@UEAAJPEBG00U_FILETIME@@HPEAUISdAsyncPriv@@PEAPEAG@Z`
- size: `1093`
- prototype: `__int64 __fastcall(CSdSafeguard *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, int, struct ISdAsyncPriv *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800083a0`
- `0x180009f0c`
- `0x180037bc0`
- `0x180038578`
- `0x1800392c0`
- `0x1800395b8`
- `0x180072e08`
- `0x180072f14`
- `0x18007d318`
- `0x1800935fc`
- `0x18009e208`
- `0x18009e8c4`
- `0x18009e904`
- `0x18009f560`
- `0x1800d1010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180037cdf`
- `msvcrt!wcsrchr` at `0x180037cdf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180037c95`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180037f8b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180037c95`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180037f8b`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180037db0`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180037db0`

## pseudocode

```c

```
