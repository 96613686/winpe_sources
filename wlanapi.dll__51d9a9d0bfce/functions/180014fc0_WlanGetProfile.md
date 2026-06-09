# WlanGetProfile

- ea: `0x180014fc0`
- end: `0x1800152d7`
- name: `WlanGetProfile`
- size: `791`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, LPCWSTR strProfileName, PVOID pReserved, LPWSTR *pstrProfileXml, DWORD *pdwFlags, DWORD *pdwGrantedAccess)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016570`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180008190`
- `0x180010160`
- `0x180014fc0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x180060fbe`
- `RPCRT4!RpcExceptionFilter` at `0x180060fbe`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180015285`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180015285`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800150ea`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800150ea`

## pseudocode

```c

```
