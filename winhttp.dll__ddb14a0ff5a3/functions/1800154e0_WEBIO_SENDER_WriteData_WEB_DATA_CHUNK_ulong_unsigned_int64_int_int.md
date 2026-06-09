# WEBIO_SENDER::WriteData(_WEB_DATA_CHUNK *,ulong *,unsigned __int64,int,int)

- ea: `0x1800154e0`
- end: `0x180015889`
- name: `?WriteData@WEBIO_SENDER@@QEAAKPEAU_WEB_DATA_CHUNK@@PEAK_KHH@Z`
- size: `937`
- prototype: `unsigned int __usercall@<eax>(WEBIO_SENDER *__hidden this@<rcx>, struct _WEB_DATA_CHUNK *@<rdx>, unsigned int *@<r8>, unsigned __int64@<r9>, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180038e30`

## callees

- `0x1800154e0`
- `0x180015aa0`
- `0x180015d30`
- `0x180098320`
- `0x18009b9d4`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800dbc40`
- `0x1800dc054`
- `0x1800dc628`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155b5`
- `ntdll!EtwEventActivityIdControl` at `0x18001558a`
- `ntdll!EtwEventActivityIdControl` at `0x180015617`
- `ntdll!EtwEventActivityIdControl` at `0x18001558a`
- `ntdll!EtwEventActivityIdControl` at `0x180015617`
- `webio!__imp_WebSendHttpRequestEntity` at `0x18001570a`
- `webio!__imp_WebSendHttpRequestEntity` at `0x18001570a`

## pseudocode

```c

```
