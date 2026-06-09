# WorkerModule::InitializeVirtualMachine(_GUID const &,VmInitParameters const *,IVmSimpleTask *)

- ea: `0x1400d3dd4`
- end: `0x1400d41d6`
- name: `?InitializeVirtualMachine@WorkerModule@@QEAAXAEBU_GUID@@PEBUVmInitParameters@@PEAUIVmSimpleTask@@@Z`
- size: `1026`
- prototype: `void(WorkerModule *__hidden this, const struct _GUID *, const struct VmInitParameters *, struct IVmSimpleTask *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update`

## callers

- `0x140135b50`

## callees

- `0x140032620`
- `0x1400364a0`
- `0x140042a68`
- `0x14004314c`
- `0x140046770`
- `0x1400545bc`
- `0x140058dfc`
- `0x140078628`
- `0x1400ba144`
- `0x1400c6050`
- `0x1400d3dd4`
- `0x1400d41dc`
- `0x1400d426c`
- `0x1400d4994`
- `0x1400d4a54`
- `0x1400d4a7c`
- `0x1400d8fec`
- `0x1400d9018`
- `0x1400df2e4`
- `0x140102580`
- `0x14011edec`
- `0x14011f6fc`
- `0x140121a29`
- `0x140129208`
- `0x14012b0a4`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400d4007`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400d4007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400d4037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400d4037`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400d4195`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400d4195`
- `vmprox!GetVmErrInfo` at `0x1400d414b`
- `vmprox!GetVmErrInfo` at `0x1400d414b`

## pseudocode

```c

```
