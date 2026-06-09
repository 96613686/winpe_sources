# CSessionCacheTable::CacheGetInfo(ulong,_SSL_SESSION_CACHE_INFO_RESPONSE *)

- ea: `0x18007388c`
- end: `0x18007392f`
- name: `?CacheGetInfo@CSessionCacheTable@@QEAAKKPEAU_SSL_SESSION_CACHE_INFO_RESPONSE@@@Z`
- size: `163`
- prototype: `unsigned int __fastcall(CSessionCacheTable *__hidden this, unsigned int, struct _SSL_SESSION_CACHE_INFO_RESPONSE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180068d54`

## callees

- `0x18007388c`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800738ac`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800738ac`
- `ntdll!RtlReleaseResource` at `0x18007391a`
- `ntdll!RtlReleaseResource` at `0x18007391a`

## pseudocode

```c

```
