# CSessionCacheServerItem::Deserialize(CSslContext *,uchar *,ulong)

- ea: `0x180076b98`
- end: `0x180076e2d`
- name: `?Deserialize@CSessionCacheServerItem@@QEAAKPEAVCSslContext@@PEAEK@Z`
- size: `661`
- prototype: `unsigned int __fastcall(CSessionCacheServerItem *__hidden this, struct CSslContext *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180006f1c`

## callees

- `0x180021eb0`
- `0x180057c8c`
- `0x180076b98`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180076be4`
- `ntdll!RtlAcquireResourceExclusive` at `0x180076be4`
- `ntdll!RtlReleaseResource` at `0x180076e10`
- `ntdll!RtlReleaseResource` at `0x180076e10`
- `ncrypt!SslImportKey` at `0x180076cc4`
- `ncrypt!SslImportKey` at `0x180076cc4`

## pseudocode

```c

```
