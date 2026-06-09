# CredSerializationHelper::EncryptBufferForSameLogon(IWinApiLite *,uchar * const,ulong,uchar * *,ulong *)

- ea: `0x18004be20`
- end: `0x18004c046`
- name: `?EncryptBufferForSameLogon@CredSerializationHelper@@SAJPEAVIWinApiLite@@QEAEKPEAPEAEPEAK@Z`
- size: `550`
- prototype: `static int(struct IWinApiLite *, unsigned __int8 *const, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180025bbc`
- `0x18004c2a4`

## callees

- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180013434`
- `0x18001abbe`
- `0x18001ac3c`
- `0x18004be20`
- `0x1800535d8`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004bedc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004bedc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004bfa3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004bfa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf50`

## string_xrefs

- `0x18004bfba`: `hr = SafeCopyMemory(pBuffer, bufferSize, pData, dataSize)`

## pseudocode

```c

```
