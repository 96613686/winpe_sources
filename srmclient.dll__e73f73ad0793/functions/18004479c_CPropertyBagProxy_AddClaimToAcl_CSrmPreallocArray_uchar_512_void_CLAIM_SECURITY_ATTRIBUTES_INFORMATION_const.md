# CPropertyBagProxy::AddClaimToAcl(CSrmPreallocArray<uchar,512> &,void *,_CLAIM_SECURITY_ATTRIBUTES_INFORMATION const &)

- ea: `0x18004479c`
- end: `0x180044a0a`
- name: `?AddClaimToAcl@CPropertyBagProxy@@AEAAXAEAV?$CSrmPreallocArray@E$0CAA@@@PEAXAEBU_CLAIM_SECURITY_ATTRIBUTES_INFORMATION@@@Z`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180044b40`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18004479c`
- `0x1800479e0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004489c`
- `KERNEL32!GetLastError` at `0x18004489c`
- `api-ms-win-security-base-l1-2-0!AddResourceAttributeAce` at `0x18004488e`
- `api-ms-win-security-base-l1-2-0!AddResourceAttributeAce` at `0x180044917`
- `api-ms-win-security-base-l1-2-0!AddResourceAttributeAce` at `0x18004488e`
- `api-ms-win-security-base-l1-2-0!AddResourceAttributeAce` at `0x180044917`

## string_xrefs

- `0x1800447de`: `base\fs\fsrm\service\modulewrp\propertybagproxy.cpp`
- `0x1800447ea`: `CPropertyBagProxy::AddClaimToAcl`

## pseudocode

```c

```
