# UpdateAliasXReference(ulong,void *)

- ea: `0x18004b9c4`
- end: `0x18004bb8a`
- name: `?UpdateAliasXReference@@YAJKPEAX@Z`
- size: `454`
- prototype: `int(unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18003dd78`

## callees

- `0x1800400ac`
- `0x1800401f0`
- `0x180041560`
- `0x18004b9c4`

## import_xrefs

- `ntdll!RtlpNtSetValueKey` at `0x18004bb46`
- `ntdll!RtlpNtSetValueKey` at `0x18004bb46`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004b9e6`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004b9e6`
- `ntdll!RtlFreeHeap` at `0x18004bb64`
- `ntdll!RtlFreeHeap` at `0x18004bb64`
- `ntdll!RtlAllocateHeap` at `0x18004bab9`
- `ntdll!RtlAllocateHeap` at `0x18004bab9`
- `ntdll!NtClose` at `0x18004ba3a`
- `ntdll!NtClose` at `0x18004bb6e`
- `ntdll!NtClose` at `0x18004ba3a`
- `ntdll!NtClose` at `0x18004bb6e`
- `ntdll!RtlpNtQueryValueKey` at `0x18004ba7b`
- `ntdll!RtlpNtQueryValueKey` at `0x18004baf2`
- `ntdll!RtlpNtQueryValueKey` at `0x18004ba7b`
- `ntdll!RtlpNtQueryValueKey` at `0x18004baf2`

## pseudocode

```c

```
