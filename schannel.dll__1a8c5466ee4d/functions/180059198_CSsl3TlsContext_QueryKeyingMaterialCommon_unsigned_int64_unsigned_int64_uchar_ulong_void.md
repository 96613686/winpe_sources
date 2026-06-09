# CSsl3TlsContext::QueryKeyingMaterialCommon(unsigned __int64,unsigned __int64,uchar *,ulong,void *)

- ea: `0x180059198`
- end: `0x1800593b9`
- name: `?QueryKeyingMaterialCommon@CSsl3TlsContext@@IEAAK_K0PEAEKPEAX@Z`
- size: `545`
- prototype: `unsigned int __fastcall(CSsl3TlsContext *__hidden this, unsigned __int64, unsigned __int64, unsigned __int8 *, unsigned int, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059080`
- `0x1800590c0`
- `0x180059100`

## callees

- `0x180014240`
- `0x180021eb0`
- `0x180057c8c`
- `0x180059198`
- `0x180091010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800593a4`
- `ntdll!RtlNtStatusToDosError` at `0x1800593a4`
- `ncrypt!SslExportKeyingMaterial` at `0x180059311`
- `ncrypt!SslExportKeyingMaterial` at `0x180059311`

## pseudocode

```c

```
