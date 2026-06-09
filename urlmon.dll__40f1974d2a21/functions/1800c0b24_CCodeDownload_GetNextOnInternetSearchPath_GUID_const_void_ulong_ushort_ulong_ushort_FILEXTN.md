# CCodeDownload::GetNextOnInternetSearchPath(_GUID const &,void * *,ulong *,ushort *,ulong,ushort * *,FILEXTN *)

- ea: `0x1800c0b24`
- end: `0x1800c0e92`
- name: `?GetNextOnInternetSearchPath@CCodeDownload@@QEAAJAEBU_GUID@@PEAPEAXPEAKPEAGKPEAPEAGPEAW4FILEXTN@@@Z`
- size: `878`
- prototype: `__int64 __usercall@<rax>(CCodeDownload *__hidden this@<rcx>, const struct _GUID *@<rdx>, void **@<r8>, unsigned int *@<r9>, unsigned __int16 *, unsigned int, unsigned __int16 **, enum FILEXTN *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bea40`
- `0x1800bf484`

## callees

- `0x1800150e0`
- `0x180044b84`
- `0x180058738`
- `0x18005cc10`
- `0x18009ef68`
- `0x1800c0a98`
- `0x1800c0b24`
- `0x1800c5570`
- `0x1800c5c70`
- `0x1800c7490`
- `0x18011baa0`

## import_xrefs

- `iertutil!__imp_IERegGetBufferSizeSz` at `0x1800c0bba`
- `iertutil!__imp_IERegGetBufferSizeSz` at `0x1800c0bba`
- `iertutil!__imp_IERegGetSz` at `0x1800c0c06`
- `iertutil!__imp_IERegGetSz` at `0x1800c0c06`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c0cd8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c0cf0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c0d09`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c0cd8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c0cf0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c0d09`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0ca4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c0ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0dfb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c0ded`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c0ded`

## string_xrefs

- `0x1800c0cde`: `CLSID=%s`
- `0x1800c0d0f`: `EXTENSION=%s`

## pseudocode

```c

```
