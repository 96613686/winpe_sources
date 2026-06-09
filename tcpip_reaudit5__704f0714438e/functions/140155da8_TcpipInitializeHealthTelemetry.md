# TcpipInitializeHealthTelemetry

- ea: `0x140155da8`
- end: `0x140155f3c`
- name: `TcpipInitializeHealthTelemetry`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1402801b8`

## callees

- `0x140155da8`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140155dd2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140155dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140155ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140155ec0`
- `NETIO!NetioOpenKey` at `0x140155e32`
- `NETIO!NetioOpenKey` at `0x140155e32`
- `NETIO!NetioQueryValueKey` at `0x140155e78`
- `NETIO!NetioQueryValueKey` at `0x140155e78`
- `NETIO!NetioTimerWorkItemInitialize` at `0x140155f07`
- `NETIO!NetioTimerWorkItemInitialize` at `0x140155f07`
- `NETIO!NetioTimerWorkItemStart` at `0x140155f25`
- `NETIO!NetioTimerWorkItemStart` at `0x140155f25`
- `NETIO!NetioCloseKey` at `0x140155eda`
- `NETIO!NetioCloseKey` at `0x140155eda`

## string_xrefs

- `0x140155e0c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c

```
