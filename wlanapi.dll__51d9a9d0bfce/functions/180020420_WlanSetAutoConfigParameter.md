# WlanSetAutoConfigParameter

- ea: `0x180020420`
- end: `0x1800205ea`
- name: `WlanSetAutoConfigParameter`
- size: `458`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, WLAN_AUTOCONF_OPCODE OpCode, DWORD dwDataSize, const PVOID pData, PVOID pReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x180020420`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800204fe`
- `RPCRT4!NdrClientCall3` at `0x1800204fe`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800205a2`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800205a2`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800204c1`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800204c1`

## pseudocode

```c

```
