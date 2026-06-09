# WlanSaveTemporaryProfile

- ea: `0x180020180`
- end: `0x18002040d`
- name: `WlanSaveTemporaryProfile`
- size: `653`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, LPCWSTR strProfileName, LPCWSTR strAllUserProfileSecurity, DWORD dwFlags, BOOL bOverWrite, PVOID pReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x180020180`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800202f1`
- `RPCRT4!NdrClientCall3` at `0x1800202f1`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800203b9`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800203b9`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180020264`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180020264`

## pseudocode

```c

```
