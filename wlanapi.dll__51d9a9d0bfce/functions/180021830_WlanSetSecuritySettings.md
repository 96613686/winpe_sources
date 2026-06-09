# WlanSetSecuritySettings

- ea: `0x180021830`
- end: `0x180021a64`
- name: `WlanSetSecuritySettings`
- size: `564`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, WLAN_SECURABLE_OBJECT SecurableObject, LPCWSTR strModifiedSDDL)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ee10`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x180021830`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002194f`
- `RPCRT4!NdrClientCall3` at `0x18002194f`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180021a16`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180021a16`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800218d7`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800218d7`

## pseudocode

```c

```
