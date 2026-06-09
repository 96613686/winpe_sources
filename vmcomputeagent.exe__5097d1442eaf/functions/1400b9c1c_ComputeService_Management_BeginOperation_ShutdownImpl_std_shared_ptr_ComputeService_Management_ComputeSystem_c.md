# ComputeService::Management::BeginOperation_ShutdownImpl(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveServerOperation,std::unique_ptr<ComputeService::Management::ActivityHolder,std::default_delete<ComputeService::Management::ActivityHolder>>,std::shared_ptr<ComputeService::Management::StateOperationContext>,void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::CompletedStateOperation &))

- ea: `0x1400b9c1c`
- end: `0x1400ba037`
- name: `?BeginOperation_ShutdownImpl@Management@ComputeService@@YA?AVActiveStateOperation@12@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveServerOperation@12@V?$unique_ptr@VActivityHolder@Management@ComputeService@@U?$default_delete@VActivityHolder@Management@ComputeService@@@std@@@5@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@5@P6AX0AEAVCompletedStateOperation@12@@Z@Z`
- size: `1051`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008cc20`
- `0x14009cd50`
- `0x1400a6c30`

## callees

- `0x140005360`
- `0x1400083bc`
- `0x14000ea60`
- `0x140034170`
- `0x14004199c`
- `0x1400b8870`
- `0x1400b9c1c`
- `0x1400ba34c`
- `0x1400bb0e4`
- `0x1400dc6e8`
- `0x1400dd4d0`
- `0x1400e6e84`
- `0x1400e6f08`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9e0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9f0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9e0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9f0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b9cc5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b9cc5`

## string_xrefs

- `0x1400b9fda`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400ba00d`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`
- `0x1400ba025`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`

## pseudocode

```c

```
