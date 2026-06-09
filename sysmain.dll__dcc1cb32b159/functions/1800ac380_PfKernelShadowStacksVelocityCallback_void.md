# PfKernelShadowStacksVelocityCallback(void *)

- ea: `0x1800ac380`
- end: `0x1800ac410`
- name: `?PfKernelShadowStacksVelocityCallback@@YAXPEAX@Z`
- size: `144`
- prototype: `void __fastcall(void *context)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ac5d0`

## callees

- `0x1800ac380`
- `0x1800ac418`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800ac394`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800ac394`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800ac3f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800ac3f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac405`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ac3da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ac3da`

## pseudocode

```c

```
