# SplIpcReceiveMessage(_SPL_IPC_MESSAGE * *)

- ea: `0x14003f278`
- end: `0x14003f566`
- name: `?SplIpcReceiveMessage@@YAJPEAPEAU_SPL_IPC_MESSAGE@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(struct _SPL_IPC_MESSAGE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003fa90`
- `0x14004c400`

## callees

- `0x14001748c`
- `0x140031720`
- `0x14003edb8`
- `0x14003eedc`
- `0x14003f278`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003f4bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003f4cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003f4bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003f4cc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003f34f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003f34f`
- `ntdll!AlpcGetMessageAttribute` at `0x14003f2f1`
- `ntdll!AlpcGetMessageAttribute` at `0x14003f2f1`
- `ntdll!NtAlpcAcceptConnectPort` at `0x14003f41e`
- `ntdll!NtAlpcAcceptConnectPort` at `0x14003f41e`
- `ntdll!NtAlpcCancelMessage` at `0x14003f4a9`
- `ntdll!NtAlpcCancelMessage` at `0x14003f4a9`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003f328`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003f3a3`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003f328`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003f3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f527`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f527`

## string_xrefs

- `0x14003f449`: `[%s] Accepted incoming connection request`
- `0x14003f4f6`: `[%s] Failed to accept incoming connection request 0x%x`

## pseudocode

```c

```
