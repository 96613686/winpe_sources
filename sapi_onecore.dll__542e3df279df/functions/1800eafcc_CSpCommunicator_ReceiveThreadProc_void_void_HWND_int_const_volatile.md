# CSpCommunicator::ReceiveThreadProc(void *,void *,HWND__ *,int const volatile *)

- ea: `0x1800eafcc`
- end: `0x1800eb274`
- name: `?ReceiveThreadProc@CSpCommunicator@@AEAAJPEAX0PEAUHWND__@@PEDH@Z`
- size: `680`
- prototype: `__int64 __fastcall(HANDLE *this, void *, void *, HWND, const volatile int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ebab0`

## callees

- `0x18000be70`
- `0x180013ec0`
- `0x1800e9cd8`
- `0x1800ea838`
- `0x1800eada8`
- `0x1800eafcc`
- `0x1800ec1f0`
- `0x1800ec240`
- `0x1800ec564`
- `0x1800ec750`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eb22d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eb22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb201`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800eb1f7`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800eb1f7`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800eb0f7`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800eb0f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800eb13a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800eb13a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800eb120`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800eb120`

## string_xrefs

- `0x1800eb1a7`: `Cannot read a message from pipe, Error = %X. Assuming the other process has terminated.`
- `0x1800eb07e`: `CSpCommunicator::ProcessReceivedMessage: Received unexpected IPC message, ID = %u`

## pseudocode

```c

```
