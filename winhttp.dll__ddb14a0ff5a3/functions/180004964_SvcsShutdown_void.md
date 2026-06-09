# _SvcsShutdown(void)

- ea: `0x180004964`
- end: `0x180004a56`
- name: `?_SvcsShutdown@@YAXXZ`
- size: `242`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000416c`

## callees

- `0x18000409c`
- `0x180004964`
- `0x1800cf008`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000498e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000498e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a02`
- `ntdll!RtlDllShutdownInProgress` at `0x180004977`
- `ntdll!RtlDllShutdownInProgress` at `0x180004977`
- `RPCRT4!RpcBindingFree` at `0x1800049ad`
- `RPCRT4!RpcBindingFree` at `0x1800049c3`
- `RPCRT4!RpcBindingFree` at `0x1800049ad`
- `RPCRT4!RpcBindingFree` at `0x1800049c3`

## pseudocode

```c

```
