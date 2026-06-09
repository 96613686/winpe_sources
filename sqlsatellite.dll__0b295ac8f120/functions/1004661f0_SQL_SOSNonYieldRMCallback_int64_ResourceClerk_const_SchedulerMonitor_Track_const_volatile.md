# SQL_SOSNonYieldRMCallback(__int64,ResourceClerk const *,SchedulerMonitor::Track const * volatile)

- ea: `0x1004661f0`
- end: `0x1004666f9`
- name: `?SQL_SOSNonYieldRMCallback@@YAX_JPEBVResourceClerk@@REBVTrack@SchedulerMonitor@@@Z`
- size: `1289`
- prototype: `void __fastcall(__int64, const struct ResourceClerk *, const struct SchedulerMonitor::Track *volatile)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x10040cc90`
- `0x1004191d0`
- `0x100450ce0`
- `0x100455f90`
- `0x10045d370`
- `0x10045d5d0`
- `0x100464c60`
- `0x100465270`
- `0x1004661f0`
- `0x100466b20`
- `0x1004680b0`
- `0x1004681c0`
- `0x100486af0`
- `0x100487cd6`
- `0x1004880d0`

## import_xrefs

- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10046659d`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004664dd`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004664dd`
- `sqldk!?sm_CpuConsumers@SOS_PublicGlobals@@2JC` at `0x100466287`
- `sqldk!?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ` at `0x100466663`
- `sqldk!?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ` at `0x100466663`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x1004663df`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x1004663df`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100466396`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100466396`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100466242`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100466368`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10046637d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004663a4`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100466242`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100466368`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10046637d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004663a4`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10046638f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004665a9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004665a9`

## string_xrefs

- `0x1004663c0`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c

```
