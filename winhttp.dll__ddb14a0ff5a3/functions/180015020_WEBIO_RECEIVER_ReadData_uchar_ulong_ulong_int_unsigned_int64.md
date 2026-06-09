# WEBIO_RECEIVER::ReadData(uchar *,ulong,ulong *,int,unsigned __int64)

- ea: `0x180015020`
- end: `0x1800153fb`
- name: `?ReadData@WEBIO_RECEIVER@@QEAAKPEAEKPEAKH_K@Z`
- size: `987`
- prototype: `unsigned int __usercall@<eax>(WEBIO_RECEIVER *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18002f050`
- `0x180037d40`

## callees

- `0x180015020`
- `0x180015aa0`
- `0x180015bd0`
- `0x180098320`
- `0x18009b670`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800dbc40`
- `0x1800dc054`
- `0x1800dc628`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015112`
- `ntdll!EtwEventActivityIdControl` at `0x1800150e7`
- `ntdll!EtwEventActivityIdControl` at `0x180015177`
- `ntdll!EtwEventActivityIdControl` at `0x1800150e7`
- `ntdll!EtwEventActivityIdControl` at `0x180015177`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x18001526e`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x18001526e`

## string_xrefs

- `0x1800153e0`: `_READING_DATA`

## pseudocode

```c

```
