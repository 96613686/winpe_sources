# NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(SQLSOS_NonYieldCopiedStackRecord::NonYieldType,__int64 (**)(void),uint,ulong,ulong,SOS_Task *,Worker *,ulong,long,unsigned __int64,unsigned __int64)

- ea: `0x100407ea0`
- end: `0x10040806f`
- name: `?StoreCopiedNonYieldStackRingBuffer@NonYieldSystemInformation@@QEAAXW4NonYieldType@SQLSOS_NonYieldCopiedStackRecord@@PEAP6A_JXZIKKPEAVSOS_Task@@PEAVWorker@@KJ_K4@Z`
- size: `463`
- prototype: `void __high(enum SQLSOS_NonYieldCopiedStackRecord::NonYieldType, __int64 (__high **)(void), unsigned int, unsigned int, unsigned int, struct SOS_Task *, struct Worker *, unsigned int, int, unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x100405b20`
- `0x100406350`
- `0x100406750`
- `0x100406c30`

## callees

- `0x100402880`
- `0x100407ea0`
- `0x1004534f8`

## import_xrefs

- `sqllang!?IsNonYieldCopiedStackRecordMatchingEventEnabled@@YAHXZ` at `0x10040802b`
- `sqllang!?IsNonYieldCopiedStackRecordMatchingEventEnabled@@YAHXZ` at `0x10040802b`
- `sqllang!?PublishNonYieldCopiedStackRecordEvent@@YAXPEAVSQLSOS_NonYieldCopiedStackRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10040803e`
- `sqllang!?PublishNonYieldCopiedStackRecordEvent@@YAXPEAVSQLSOS_NonYieldCopiedStackRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10040803e`
- `sqldk!?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA` at `0x100407fc7`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100408050`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100408050`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100407f7d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100407f8b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100407f7d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100407f8b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100407f97`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100407f97`

## pseudocode

```c

```
