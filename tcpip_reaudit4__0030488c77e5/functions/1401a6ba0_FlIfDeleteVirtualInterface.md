# FlIfDeleteVirtualInterface

- ea: `0x1401a6ba0`
- end: `0x1401a6ec6`
- name: `FlIfDeleteVirtualInterface`
- size: `806`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1401a6ecc`
- `0x1401a8280`

## callees

- `0x1401a6ba0`
- `0x1401a7da4`
- `0x1401a7ec8`
- `0x1401a8260`
- `0x1401a8c40`
- `0x1401b3278`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a6e8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a6e8f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a6e83`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a6e83`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6bf7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6bf7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a6be2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a6be2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6cfe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6cfe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a6cd3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a6cd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a6e5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a6e5b`
- `NETIO!NsiSetAllParameters` at `0x1401a6e15`
- `NETIO!NsiSetAllParameters` at `0x1401a6e15`
- `NDIS!NdisIfDeregisterInterface` at `0x1401a6caa`
- `NDIS!NdisIfDeregisterInterface` at `0x1401a6caa`
- `NDIS!NdisIfFreeNetLuidIndex` at `0x1401a6e31`
- `NDIS!NdisIfFreeNetLuidIndex` at `0x1401a6e31`

## string_xrefs

- `0x1401a6db6`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x1401a6da7`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c

```
