# TcpipInitializeHealthTelemetry

- ea: `0x140157c88`
- end: `0x140157e1c`
- name: `TcpipInitializeHealthTelemetry`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1402841b8`

## callees

- `0x140157c88`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140157cb2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140157cb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157da0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157da0`
- `NETIO!NetioOpenKey` at `0x140157d12`
- `NETIO!NetioOpenKey` at `0x140157d12`
- `NETIO!NetioQueryValueKey` at `0x140157d58`
- `NETIO!NetioQueryValueKey` at `0x140157d58`
- `NETIO!NetioTimerWorkItemInitialize` at `0x140157de7`
- `NETIO!NetioTimerWorkItemInitialize` at `0x140157de7`
- `NETIO!NetioTimerWorkItemStart` at `0x140157e05`
- `NETIO!NetioTimerWorkItemStart` at `0x140157e05`
- `NETIO!NetioCloseKey` at `0x140157dba`
- `NETIO!NetioCloseKey` at `0x140157dba`

## string_xrefs

- `0x140157cec`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c

```
