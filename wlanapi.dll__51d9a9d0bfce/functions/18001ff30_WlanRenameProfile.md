# WlanRenameProfile

- ea: `0x18001ff30`
- end: `0x180020179`
- name: `WlanRenameProfile`
- size: `585`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, LPCWSTR strOldProfileName, LPCWSTR strNewProfileName, PVOID pReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x18001ff30`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180020069`
- `RPCRT4!NdrClientCall3` at `0x180020069`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180020131`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180020131`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001ffec`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001ffec`

## pseudocode

```c

```
