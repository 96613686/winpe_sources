# SampInitializeRegistry(ushort const *,_NT_PRODUCT_TYPE *,_POLICY_LSA_SERVER_ROLE *,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_PRIMARY_DOMAIN_INFO *,uchar)

- ea: `0x180041430`
- end: `0x180041557`
- name: `?SampInitializeRegistry@@YAJPEBGPEAW4_NT_PRODUCT_TYPE@@PEAW4_POLICY_LSA_SERVER_ROLE@@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@PEAU_POLICY_PRIMARY_DOMAIN_INFO@@E@Z`
- size: `295`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum _NT_PRODUCT_TYPE *, enum _POLICY_LSA_SERVER_ROLE *, struct _POLICY_ACCOUNT_DOMAIN_INFO *, struct _POLICY_PRIMARY_DOMAIN_INFO *, unsigned __int8)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180071af0`
- `0x1800722d0`
- `0x1800799a8`

## callees

- `0x1800372ac`
- `0x18003d938`
- `0x18003e2d4`
- `0x18003ebb8`
- `0x18003f354`
- `0x18003f850`
- `0x180041430`

## import_xrefs

- `ntdll!NtFlushKey` at `0x1800414e7`
- `ntdll!NtFlushKey` at `0x1800414e7`
- `ntdll!RtlFreeHeap` at `0x1800414cf`
- `ntdll!RtlFreeHeap` at `0x1800414cf`
- `ntdll!NtClose` at `0x180041529`
- `ntdll!NtClose` at `0x180041546`
- `ntdll!NtClose` at `0x180041529`
- `ntdll!NtClose` at `0x180041546`
- `LSASRV!LsarClose` at `0x1800414a8`
- `LSASRV!LsarClose` at `0x1800414a8`

## pseudocode

```c

```
