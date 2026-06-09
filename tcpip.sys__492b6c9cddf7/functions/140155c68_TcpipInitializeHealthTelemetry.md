# TcpipInitializeHealthTelemetry

- ea: `0x140155c68`
- end: `0x140155dfc`
- name: `TcpipInitializeHealthTelemetry`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1402801b8`

## callees

- `0x140155c68`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140155c92`
- `ntoskrnl!KeInitializeSpinLock` at `0x140155c92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140155d80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140155d80`
- `NETIO!NetioOpenKey` at `0x140155cf2`
- `NETIO!NetioOpenKey` at `0x140155cf2`
- `NETIO!NetioQueryValueKey` at `0x140155d38`
- `NETIO!NetioQueryValueKey` at `0x140155d38`
- `NETIO!NetioTimerWorkItemInitialize` at `0x140155dc7`
- `NETIO!NetioTimerWorkItemInitialize` at `0x140155dc7`
- `NETIO!NetioTimerWorkItemStart` at `0x140155de5`
- `NETIO!NetioTimerWorkItemStart` at `0x140155de5`
- `NETIO!NetioCloseKey` at `0x140155d9a`
- `NETIO!NetioCloseKey` at `0x140155d9a`

## string_xrefs

- `0x140155ccc`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c

```
