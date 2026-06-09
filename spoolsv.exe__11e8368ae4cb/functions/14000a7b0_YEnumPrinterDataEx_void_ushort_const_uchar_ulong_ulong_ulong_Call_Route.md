# YEnumPrinterDataEx(void *,ushort const *,uchar *,ulong,ulong *,ulong *,Call_Route)

- ea: `0x14000a7b0`
- end: `0x14000a943`
- name: `?YEnumPrinterDataEx@@YAKPEAXPEBGPEAEKPEAK3W4Call_Route@@@Z`
- size: `403`
- prototype: `unsigned int __high(void *, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int *, enum Call_Route)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140011710`

## callees

- `0x140002a70`
- `0x1400041c0`
- `0x14000a7b0`
- `0x14000a950`
- `0x140079338`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a90f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a84c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a8a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a84c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a8a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a8de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a808`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a894`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a8b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a808`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a894`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a8b2`
- `RPCRT4!RpcRevertToSelf` at `0x14000a8aa`
- `RPCRT4!RpcRevertToSelf` at `0x14000a8aa`
- `RPCRT4!RpcImpersonateClient` at `0x14000a7fc`
- `RPCRT4!RpcImpersonateClient` at `0x14000a7fc`

## pseudocode

```c

```
