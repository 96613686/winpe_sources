# CSessionCacheServerItem::ComputeSerializedCacheItemLen(CSslContext *,ulong *)

- ea: `0x1800769d4`
- end: `0x180076af6`
- name: `?ComputeSerializedCacheItemLen@CSessionCacheServerItem@@QEAAKPEAVCSslContext@@PEAK@Z`
- size: `290`
- prototype: `unsigned int __fastcall(CSessionCacheServerItem *__hidden this, struct CSslContext *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007ce4c`

## callees

- `0x1800769d4`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180076ad4`
- `ntdll!RtlReleaseResource` at `0x180076ad4`
- `ntdll!RtlAcquireResourceShared` at `0x180076a0b`
- `ntdll!RtlAcquireResourceShared` at `0x180076a0b`
- `ncrypt!SslExportKey` at `0x180076a8b`
- `ncrypt!SslExportKey` at `0x180076a8b`

## pseudocode

```c

```
