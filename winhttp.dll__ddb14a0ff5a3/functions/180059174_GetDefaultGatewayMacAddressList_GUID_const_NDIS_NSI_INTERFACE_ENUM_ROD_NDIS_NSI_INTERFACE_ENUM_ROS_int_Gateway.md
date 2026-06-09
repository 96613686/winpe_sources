# GetDefaultGatewayMacAddressList(_GUID const *,_NDIS_NSI_INTERFACE_ENUM_ROD *,_NDIS_NSI_INTERFACE_ENUM_ROS *,int *,_GatewayMacAddressList * *,int *)

- ea: `0x180059174`
- end: `0x18005966d`
- name: `?GetDefaultGatewayMacAddressList@@YAKPEBU_GUID@@PEAU_NDIS_NSI_INTERFACE_ENUM_ROD@@PEAU_NDIS_NSI_INTERFACE_ENUM_ROS@@PEAHPEAPEAU_GatewayMacAddressList@@3@Z`
- size: `1273`
- prototype: `unsigned int __usercall@<eax>(GUID *InterfaceGuid@<rcx>, struct _NDIS_NSI_INTERFACE_ENUM_ROD *@<rdx>, struct _NDIS_NSI_INTERFACE_ENUM_ROS *@<r8>, int *@<r9>, struct _GatewayMacAddressList **, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180058fc4`

## callees

- `0x180059174`
- `0x180059674`
- `0x1800596e8`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf124`
- `0x1800cf4c4`
- `0x1800d3260`
- `0x1800da214`
- `0x1800da28c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180059235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180059235`
- `IPHLPAPI!GetIfEntry2Ex` at `0x180059286`
- `IPHLPAPI!GetIfEntry2Ex` at `0x180059286`
- `IPHLPAPI!GetIpForwardTable2` at `0x1800592e7`
- `IPHLPAPI!GetIpForwardTable2` at `0x1800592e7`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18005925e`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18005925e`
- `IPHLPAPI!GetIpNetEntry2` at `0x18005935e`
- `IPHLPAPI!GetIpNetEntry2` at `0x18005935e`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x180059465`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x180059465`
- `IPHLPAPI!FreeMibTable` at `0x180059409`
- `IPHLPAPI!FreeMibTable` at `0x180059409`

## pseudocode

```c

```
