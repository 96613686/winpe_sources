# WlanGetNetworkBssList

- ea: `0x180004790`
- end: `0x180004afe`
- name: `WlanGetNetworkBssList`
- size: `878`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, const PDOT11_SSID pDot11Ssid, DOT11_BSS_TYPE dot11BssType, BOOL bSecurityEnabled, PVOID pReserved, PWLAN_BSS_LIST *ppWlanBssList)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800042a0`
- `0x180016570`

## callees

- `0x180004790`
- `0x1800063a0`
- `0x180006934`
- `0x180007d88`
- `0x1800108f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800049d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800049d6`
- `RPCRT4!RpcExceptionFilter` at `0x18006038e`
- `RPCRT4!RpcExceptionFilter` at `0x18006038e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800049d0`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800049d0`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000485b`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000485b`

## pseudocode

```c

```
