# CCodeDownload::GetNextOnInternetSearchPath(_GUID const &,void * *,ulong *,ushort *,ulong,ushort * *,FILEXTN *)

- ea: `0x1800c8ea0`
- end: `0x1800c923f`
- name: `?GetNextOnInternetSearchPath@CCodeDownload@@QEAAJAEBU_GUID@@PEAPEAXPEAKPEAGKPEAPEAGPEAW4FILEXTN@@@Z`
- size: `927`
- prototype: `__int64 __fastcall(CCodeDownload *this, const struct _GUID *, void **, unsigned int *, unsigned __int16 *, unsigned int, unsigned __int16 **, enum FILEXTN *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c6c60`
- `0x1800c76e4`

## callees

- `0x18001db50`
- `0x18004d7f0`
- `0x18005789c`
- `0x18005e1c0`
- `0x1800a5d70`
- `0x1800c8e10`
- `0x1800c8ea0`
- `0x1800cda78`
- `0x1800ce1a4`
- `0x1800cfb58`
- `0x180128660`

## import_xrefs

- `iertutil!__imp_IERegGetBufferSizeSz` at `0x1800c8f36`
- `iertutil!__imp_IERegGetBufferSizeSz` at `0x1800c8f36`
- `iertutil!__imp_IERegGetSz` at `0x1800c8f88`
- `iertutil!__imp_IERegGetSz` at `0x1800c8f88`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c9066`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c9084`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c90a3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c9066`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c9084`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c90a3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c902c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c902c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c91a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c91a1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c918d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c918d`

## string_xrefs

- `0x1800c9072`: `CLSID=%s`
- `0x1800c90af`: `EXTENSION=%s`

## pseudocode

```c

```
