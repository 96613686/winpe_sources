# SQL_SOSNonYieldIOCPCallback(SchedulerMonitor::Track const * volatile)

- ea: `0x100465cb0`
- end: `0x10046609e`
- name: `?SQL_SOSNonYieldIOCPCallback@@YAXREBVTrack@SchedulerMonitor@@@Z`
- size: `1006`
- prototype: `void __fastcall(const struct SchedulerMonitor::Track *volatile)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1004191d0`
- `0x100450ce0`
- `0x100455f90`
- `0x10045d370`
- `0x10045d5d0`
- `0x100465270`
- `0x100465cb0`
- `0x100466b20`
- `0x1004680b0`
- `0x1004681c0`
- `0x100486af0`
- `0x100487cd6`
- `0x1004880d0`

## import_xrefs

- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100465f68`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100465f68`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100465dff`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100465e82`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100465e82`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100465e39`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100465e39`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465cf4`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465df0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465e0b`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465e20`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465e47`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465cf4`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465df0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465e0b`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465e20`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100465e47`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100465e32`

## string_xrefs

- `0x100465e63`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c

```
