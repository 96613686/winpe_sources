# WlanGetSecuritySettings

- ea: `0x18000bb70`
- end: `0x18000be53`
- name: `WlanGetSecuritySettings`
- size: `739`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, WLAN_SECURABLE_OBJECT SecurableObject, PWLAN_OPCODE_VALUE_TYPE pValueType, LPWSTR *pstrCurrentSDDL, PDWORD pdwGrantedAccess)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eac0`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18000bb70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000bc70`
- `RPCRT4!NdrClientCall3` at `0x18000bc70`
- `RPCRT4!RpcExceptionFilter` at `0x1800605ee`
- `RPCRT4!RpcExceptionFilter` at `0x1800605ee`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000bd16`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000bd16`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000bc27`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000bc27`

## pseudocode

```c

```
