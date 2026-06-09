# LrpcPrepareMachineAccountSid(int,LRPC_CLIENT_IO *,ulong)

- ea: `0x1800637f0`
- end: `0x180063a85`
- name: `?LrpcPrepareMachineAccountSid@@YAJHPEAVLRPC_CLIENT_IO@@K@Z`
- size: `661`
- prototype: `__int64 __fastcall(int, struct LRPC_CLIENT_IO *, unsigned int)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180033100`
- `0x18004fcf8`
- `0x180083094`
- `0x1800bce90`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x180022870`
- `0x18002b94c`
- `0x180030578`
- `0x180031800`
- `0x180031ae4`
- `0x180032620`
- `0x1800339d4`
- `0x18005ddc0`
- `0x1800636e8`
- `0x1800637f0`
- `0x180063a8c`
- `0x18008fc98`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180063840`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180063840`
- `ntdll!RtlLeaveCriticalSection` at `0x180063933`
- `ntdll!RtlLeaveCriticalSection` at `0x180063a70`
- `ntdll!RtlLeaveCriticalSection` at `0x180063933`
- `ntdll!RtlLeaveCriticalSection` at `0x180063a70`
- `ntdll!RtlEnterCriticalSection` at `0x18006385b`
- `ntdll!RtlEnterCriticalSection` at `0x1800639b7`
- `ntdll!RtlEnterCriticalSection` at `0x180063a1c`
- `ntdll!RtlEnterCriticalSection` at `0x18006385b`
- `ntdll!RtlEnterCriticalSection` at `0x1800639b7`
- `ntdll!RtlEnterCriticalSection` at `0x180063a1c`

## pseudocode

```c

```
