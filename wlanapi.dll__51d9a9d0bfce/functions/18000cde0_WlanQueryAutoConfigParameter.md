# WlanQueryAutoConfigParameter

- ea: `0x18000cde0`
- end: `0x18000d0ba`
- name: `WlanQueryAutoConfigParameter`
- size: `730`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, WLAN_AUTOCONF_OPCODE OpCode, PVOID pReserved, PDWORD pdwDataSize, PVOID *ppData, PWLAN_OPCODE_VALUE_TYPE pWlanOpcodeValueType)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x18000cde0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ceec`
- `RPCRT4!NdrClientCall3` at `0x18000ceec`
- `RPCRT4!RpcExceptionFilter` at `0x1800606fe`
- `RPCRT4!RpcExceptionFilter` at `0x1800606fe`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000cfdd`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000cfdd`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000ce8e`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000ce8e`

## pseudocode

```c

```
