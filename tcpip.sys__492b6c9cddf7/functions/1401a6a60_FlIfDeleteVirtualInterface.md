# FlIfDeleteVirtualInterface

- ea: `0x1401a6a60`
- end: `0x1401a6d86`
- name: `FlIfDeleteVirtualInterface`
- size: `806`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1401a6d8c`
- `0x1401a8140`

## callees

- `0x1401a6a60`
- `0x1401a7c64`
- `0x1401a7d88`
- `0x1401a8120`
- `0x1401a8b00`
- `0x1401b3138`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a6d4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a6d4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a6d43`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a6d43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6ab7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6ab7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a6aa2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a6aa2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6bbe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6bbe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a6b93`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a6b93`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a6d1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a6d1b`
- `NETIO!NsiSetAllParameters` at `0x1401a6cd5`
- `NETIO!NsiSetAllParameters` at `0x1401a6cd5`
- `NDIS!NdisIfDeregisterInterface` at `0x1401a6b6a`
- `NDIS!NdisIfDeregisterInterface` at `0x1401a6b6a`
- `NDIS!NdisIfFreeNetLuidIndex` at `0x1401a6cf1`
- `NDIS!NdisIfFreeNetLuidIndex` at `0x1401a6cf1`

## string_xrefs

- `0x1401a6c67`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`
- `0x1401a6c76`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c

```
