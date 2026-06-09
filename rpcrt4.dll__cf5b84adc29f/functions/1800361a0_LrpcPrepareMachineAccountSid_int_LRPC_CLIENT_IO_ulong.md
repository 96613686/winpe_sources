# LrpcPrepareMachineAccountSid(int,LRPC_CLIENT_IO *,ulong)

- ea: `0x1800361a0`
- end: `0x18003645d`
- name: `?LrpcPrepareMachineAccountSid@@YAJHPEAVLRPC_CLIENT_IO@@K@Z`
- size: `701`
- prototype: `__int64 __fastcall(unsigned int, struct LRPC_CLIENT_IO *, int)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180010690`
- `0x1800345ac`
- `0x180084958`
- `0x1800c1610`

## callees

- `0x180022e80`
- `0x180023020`
- `0x180023a40`
- `0x18002cc40`
- `0x180031908`
- `0x180031c08`
- `0x180032f20`
- `0x180033aa4`
- `0x1800349d4`
- `0x180034dc4`
- `0x1800361a0`
- `0x180036464`
- `0x18006e470`
- `0x180094090`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800361f0`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800361f0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800362ef`
- `ntdll!RtlLeaveCriticalSection` at `0x180036441`
- `ntdll!RtlLeaveCriticalSection` at `0x1800362ef`
- `ntdll!RtlLeaveCriticalSection` at `0x180036441`
- `ntdll!RtlEnterCriticalSection` at `0x180036211`
- `ntdll!RtlEnterCriticalSection` at `0x180036379`
- `ntdll!RtlEnterCriticalSection` at `0x1800363e7`
- `ntdll!RtlEnterCriticalSection` at `0x180036211`
- `ntdll!RtlEnterCriticalSection` at `0x180036379`
- `ntdll!RtlEnterCriticalSection` at `0x1800363e7`

## pseudocode

```c

```
