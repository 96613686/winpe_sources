# StartTokenHandling

- ea: `0x1800c0d44`
- end: `0x1800c1006`
- name: `StartTokenHandling`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bca54`

## callees

- `0x180034260`
- `0x18008172c`
- `0x1800b8428`
- `0x1800c0d44`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800c0e87`
- `ntdll!RtlInitializeCriticalSection` at `0x1800c0e87`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0daf`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0e42`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0daf`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0f6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c0ea8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c0ea8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c0f2d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c0f2d`
- `KERNELBASE!LocalAlloc` at `0x1800c0ed5`
- `KERNELBASE!LocalAlloc` at `0x1800c0ed5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800c0fcd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800c0fcd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800c0e30`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800c0e30`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800c0e1e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800c0e1e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800c0d9d`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800c0d9d`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800c0fb0`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800c0fb0`

## string_xrefs

- `0x1800c0e00`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800c0df9`: `StartTokenHandling`

## pseudocode

```c

```
