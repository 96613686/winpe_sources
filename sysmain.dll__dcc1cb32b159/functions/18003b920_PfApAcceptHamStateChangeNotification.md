# PfApAcceptHamStateChangeNotification

- ea: `0x18003b920`
- end: `0x18003bab4`
- name: `PfApAcceptHamStateChangeNotification`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003b920`
- `0x18003babc`
- `0x18003bafc`
- `0x18003cbe4`
- `0x18003cffc`
- `0x1800b645a`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003b952`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003b952`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ba45`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ba91`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ba45`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ba91`
- `ntdll!RtlNtStatusToDosError` at `0x18003ba88`
- `ntdll!RtlNtStatusToDosError` at `0x18003ba88`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003ba32`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003ba32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003baac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003baac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b992`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b992`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18003b9d0`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18003b9d0`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetApplicationNameFromKey` at `0x18003b9f5`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetApplicationNameFromKey` at `0x18003b9f5`

## pseudocode

```c

```
