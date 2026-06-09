# CredSerializationHelper::EncryptBufferForSameLogon(IWinApiLite *,uchar * const,ulong,uchar * *,ulong *)

- ea: `0x18005142c`
- end: `0x180051635`
- name: `?EncryptBufferForSameLogon@CredSerializationHelper@@SAJPEAVIWinApiLite@@QEAEKPEAPEAEPEAK@Z`
- size: `521`
- prototype: `static int(struct IWinApiLite *, unsigned __int8 *const, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800516b4`

## callees

- `0x1800039e4`
- `0x18000a1a8`
- `0x18000af14`
- `0x18000cc9c`
- `0x18000e870`
- `0x180051250`
- `0x1800512f8`
- `0x18005142c`
- `0x180053890`
- `0x180063010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800514e8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800514e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005155a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005155a`

## string_xrefs

- `0x1800515a9`: `hr = SafeCopyMemory(pBuffer, bufferSize, pData, dataSize)`

## pseudocode

```c

```
