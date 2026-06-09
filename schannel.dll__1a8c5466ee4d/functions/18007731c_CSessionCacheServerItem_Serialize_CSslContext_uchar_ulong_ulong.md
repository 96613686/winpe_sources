# CSessionCacheServerItem::Serialize(CSslContext *,uchar *,ulong,ulong *)

- ea: `0x18007731c`
- end: `0x180077532`
- name: `?Serialize@CSessionCacheServerItem@@QEAAKPEAVCSslContext@@PEAEKPEAK@Z`
- size: `534`
- prototype: `unsigned int __fastcall(CSessionCacheServerItem *__hidden this, struct CSslContext *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007ce4c`

## callees

- `0x18007731c`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180077456`
- `ntdll!RtlReleaseResource` at `0x180077456`
- `ntdll!RtlAcquireResourceShared` at `0x18007736e`
- `ntdll!RtlAcquireResourceShared` at `0x18007736e`
- `ncrypt!SslExportKey` at `0x180077426`
- `ncrypt!SslExportKey` at `0x180077426`

## pseudocode

```c

```
