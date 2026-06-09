# Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero(void)

- ea: `0x18000df10`
- end: `0x18000e113`
- name: `?WaitUntilAllocatedObjectCountIsZero@VmSharableObject@Vml@@SAXXZ`
- size: `515`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c9c`

## callees

- `0x180002f50`
- `0x18000929c`
- `0x18000abc0`
- `0x18000df10`
- `0x18000f024`
- `0x18000f2fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e077`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000e01a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000e01a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000df7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000df7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000dfb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000dfe7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e039`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e04e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000dfb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000dfe7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e039`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e04e`

## string_xrefs

- `0x18000e0dc`: `Detected a leaked instance - this leak should be fixed ASAP - terminating process rather than waiting forever or risking crash during module cleanup due to invalid state.\n`

## pseudocode

```c

```
