# YEnumPrinterDataEx(void *,ushort const *,uchar *,ulong,ulong *,ulong *,Call_Route)

- ea: `0x14000b670`
- end: `0x14000b840`
- name: `?YEnumPrinterDataEx@@YAKPEAXPEBGPEAEKPEAK3W4Call_Route@@@Z`
- size: `464`
- prototype: `unsigned int __high(void *, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int *, enum Call_Route)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140012af0`

## callees

- `0x1400028e0`
- `0x140004790`
- `0x14000b670`
- `0x14000b850`
- `0x140080828`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b7ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b7ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b6ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b76c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b79c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b6ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b76c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b79c`
- `RPCRT4!RpcRevertToSelf` at `0x14000b78e`
- `RPCRT4!RpcRevertToSelf` at `0x14000b78e`
- `RPCRT4!RpcImpersonateClient` at `0x14000b6bc`
- `RPCRT4!RpcImpersonateClient` at `0x14000b6bc`

## pseudocode

```c

```
