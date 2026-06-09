# SAAManager::LookupOrCreateShadowAdminAccount(void *,ShadowAdminAccount * *)

- ea: `0x180092b08`
- end: `0x180092ca0`
- name: `?LookupOrCreateShadowAdminAccount@SAAManager@@QEAAJPEAXPEAPEAVShadowAdminAccount@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(SAAManager *__hidden this, void *, struct ShadowAdminAccount **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18008fcd8`

## callees

- `0x180027e24`
- `0x18002d720`
- `0x180090ec4`
- `0x180090f8c`
- `0x180092b08`
- `0x180093818`
- `0x1800bb5cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180092b59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180092b59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180092b84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180092b84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180092bb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180092bb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092c1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092c1c`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180092be1`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180092be1`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180092b6a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180092bbd`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180092b6a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180092bbd`

## pseudocode

```c

```
