# WorkerModule::InitializeVirtualMachine(_GUID const &,VmInitParameters const *,IVmSimpleTask *)

- ea: `0x1400e4104`
- end: `0x1400e4506`
- name: `?InitializeVirtualMachine@WorkerModule@@QEAAXAEBU_GUID@@PEBUVmInitParameters@@PEAUIVmSimpleTask@@@Z`
- size: `1026`
- prototype: `void(WorkerModule *__hidden this, const struct _GUID *, const struct VmInitParameters *, struct IVmSimpleTask *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update`

## callers

- `0x140149940`

## callees

- `0x14003366c`
- `0x140042260`
- `0x1400450d8`
- `0x1400457bc`
- `0x140047b90`
- `0x140054a90`
- `0x14006af58`
- `0x140092e58`
- `0x14009d7cc`
- `0x1400d6ef0`
- `0x1400e4104`
- `0x1400e450c`
- `0x1400e459c`
- `0x1400e4cc4`
- `0x1400e4d84`
- `0x1400e4dac`
- `0x1400e7d0c`
- `0x1400e7d38`
- `0x1400ee334`
- `0x140111090`
- `0x140132d0c`
- `0x14013361c`
- `0x140135949`
- `0x14013d128`
- `0x14013efc4`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400e4337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400e4337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400e4367`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400e4367`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400e44c5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400e44c5`
- `vmprox!GetVmErrInfo` at `0x1400e447b`
- `vmprox!GetVmErrInfo` at `0x1400e447b`

## pseudocode

```c

```
