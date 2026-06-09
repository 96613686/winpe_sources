# SampRemoveCredentials(_UNICODE_STRING *,_UNICODE_STRING *,int *,_UNICODE_STRING *)

- ea: `0x18004e8dc`
- end: `0x18004eabf`
- name: `?SampRemoveCredentials@@YAJPEAU_UNICODE_STRING@@0PEAH0@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, int *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18004f408`

## callees

- `0x180027e24`
- `0x18004e8dc`
- `0x1800b464c`
- `0x1800b4cd0`
- `0x1800b50a4`
- `0x1800b52c0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004e927`
- `ntdll!RtlInitUnicodeString` at `0x18004ea04`
- `ntdll!RtlInitUnicodeString` at `0x18004ea3e`
- `ntdll!RtlInitUnicodeString` at `0x18004e927`
- `ntdll!RtlInitUnicodeString` at `0x18004ea04`
- `ntdll!RtlInitUnicodeString` at `0x18004ea3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004e93d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004e93d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea72`

## pseudocode

```c

```
