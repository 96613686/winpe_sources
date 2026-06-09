# UrlCacheCreateFileEx(char const *,int,CAppCacheHandle *,unsigned __int64,char const *,char const *,ushort const *,CWxString *,void * *)

- ea: `0x180097e40`
- end: `0x18009828a`
- name: `?UrlCacheCreateFileEx@@YAKPEBDHPEAVCAppCacheHandle@@_K00PEBGPEAVCWxString@@PEAPEAX@Z`
- size: `1098`
- prototype: `unsigned int __usercall@<eax>(LPCCH lpMultiByteStr@<rcx>, int@<edx>, struct CAppCacheHandle *@<r8>, unsigned __int64@<r9>, LPCCH, const char *, const unsigned __int16 *, struct CWxString *, void **)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002e9bc`
- `0x18012fa90`
- `0x180184980`

## callees

- `0x180008380`
- `0x18001e86c`
- `0x180097e40`
- `0x18009970c`
- `0x180125950`
- `0x18014a7a0`
- `0x1801924b4`
- `0x1801e1790`
- `0x1801e18d0`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097fbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009803a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009803a`
- `ntdll!RtlNtStatusToDosError` at `0x18009824b`
- `ntdll!RtlNtStatusToDosError` at `0x18009826f`
- `ntdll!RtlNtStatusToDosError` at `0x18009824b`
- `ntdll!RtlNtStatusToDosError` at `0x18009826f`

## pseudocode

```c

```
