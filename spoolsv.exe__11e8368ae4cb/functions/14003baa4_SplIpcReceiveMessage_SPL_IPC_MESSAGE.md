# SplIpcReceiveMessage(_SPL_IPC_MESSAGE * *)

- ea: `0x14003baa4`
- end: `0x14003bd58`
- name: `?SplIpcReceiveMessage@@YAJPEAPEAU_SPL_IPC_MESSAGE@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(struct _SPL_IPC_MESSAGE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003c240`
- `0x140047fc0`

## callees

- `0x1400160a0`
- `0x14002f030`
- `0x14003b640`
- `0x14003b74c`
- `0x14003baa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003bcc5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003bcce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003bcc5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003bcce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003bb6f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003bb6f`
- `ntdll!AlpcGetMessageAttribute` at `0x14003bb1d`
- `ntdll!AlpcGetMessageAttribute` at `0x14003bb1d`
- `ntdll!NtAlpcAcceptConnectPort` at `0x14003bc32`
- `ntdll!NtAlpcAcceptConnectPort` at `0x14003bc32`
- `ntdll!NtAlpcCancelMessage` at `0x14003bcb7`
- `ntdll!NtAlpcCancelMessage` at `0x14003bcb7`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003bb4e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003bbbd`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003bb4e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14003bbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003bd1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003bd1f`

## string_xrefs

- `0x14003bc57`: `[%s] Accepted incoming connection request`
- `0x14003bcf1`: `[%s] Failed to accept incoming connection request 0x%x`

## pseudocode

```c

```
