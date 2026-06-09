# FlIfDeleteVirtualInterface

- ea: `0x1401a8760`
- end: `0x1401a8a86`
- name: `FlIfDeleteVirtualInterface`
- size: `806`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1401a8a8c`
- `0x1401a9e40`

## callees

- `0x1401a8760`
- `0x1401a9964`
- `0x1401a9a88`
- `0x1401a9e20`
- `0x1401aa800`
- `0x1401b4e38`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a8a4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a8a4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8a43`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8a43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a87b7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a87b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a87a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a87a2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a88be`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a88be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a8893`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a8893`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a8a1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a8a1b`
- `NETIO!NsiSetAllParameters` at `0x1401a89d5`
- `NETIO!NsiSetAllParameters` at `0x1401a89d5`
- `NDIS!NdisIfDeregisterInterface` at `0x1401a886a`
- `NDIS!NdisIfDeregisterInterface` at `0x1401a886a`
- `NDIS!NdisIfFreeNetLuidIndex` at `0x1401a89f1`
- `NDIS!NdisIfFreeNetLuidIndex` at `0x1401a89f1`

## string_xrefs

- `0x1401a8976`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x1401a8967`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c

```
