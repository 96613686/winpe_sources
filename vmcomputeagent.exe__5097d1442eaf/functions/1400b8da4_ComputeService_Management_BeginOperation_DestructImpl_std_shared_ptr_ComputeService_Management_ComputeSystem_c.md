# ComputeService::Management::BeginOperation_DestructImpl(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::DestructInfo const &,std::unique_ptr<ComputeService::Management::ActivityHolder,std::default_delete<ComputeService::Management::ActivityHolder>>,std::shared_ptr<ComputeService::Management::StateOperationContext>,void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::CompletedStateOperation &))

- ea: `0x1400b8da4`
- end: `0x1400b95a2`
- name: `?BeginOperation_DestructImpl@Management@ComputeService@@YA?AVActiveStateOperation@12@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBUDestructInfo@12@V?$unique_ptr@VActivityHolder@Management@ComputeService@@U?$default_delete@VActivityHolder@Management@ComputeService@@@std@@@5@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@5@P6AX0AEAVCompletedStateOperation@12@@Z@Z`
- size: `2046`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x140088e10`
- `0x14009b370`
- `0x1400a4ee0`

## callees

- `0x140005360`
- `0x1400056fc`
- `0x1400083bc`
- `0x14000ea60`
- `0x140034170`
- `0x140039474`
- `0x1400395f8`
- `0x14003f850`
- `0x14004199c`
- `0x140083dec`
- `0x140083f0c`
- `0x1400b601c`
- `0x1400b6188`
- `0x1400b6700`
- `0x1400b73a4`
- `0x1400b8870`
- `0x1400b8da4`
- `0x1400ba34c`
- `0x1400ba68c`
- `0x1400bb058`
- `0x1400bb0e4`
- `0x1400bb1c4`
- `0x1400bb5a0`
- `0x1400dd4d0`
- `0x1400e6e84`
- `0x1400e6f08`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b93ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b94b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b93ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b94b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b8e3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b8e3f`

## string_xrefs

- `0x1400b955a`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400b9542`: `onecore\vm\compute\management\shared\compute\StateOperation.h`
- `0x1400b9590`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`

## pseudocode

```c

```
