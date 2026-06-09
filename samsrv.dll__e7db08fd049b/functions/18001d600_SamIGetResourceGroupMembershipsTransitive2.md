# SamIGetResourceGroupMembershipsTransitive2

- ea: `0x18001d600`
- end: `0x18001d959`
- name: `SamIGetResourceGroupMembershipsTransitive2`
- size: `857`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, struct _SAMPR_PSID_ARRAY *, unsigned int, struct _SAMPR_PSID_ARRAY **, __int64 Buffer)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001d5b0`

## callees

- `0x180009620`
- `0x18001d600`
- `0x180027e24`
- `0x180027fa0`
- `0x1800372ac`
- `0x1800771dc`
- `0x180077ae0`
- `0x1800a85bc`

## import_xrefs

- `ntdll!NtSetEvent` at `0x18001d7b3`
- `ntdll!NtSetEvent` at `0x18001d7b3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001d668`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001d668`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001d643`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001d643`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001d658`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001d658`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d872`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d872`

## pseudocode

```c

```
