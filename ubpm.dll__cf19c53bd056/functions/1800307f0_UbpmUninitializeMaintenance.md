# UbpmUninitializeMaintenance

- ea: `0x1800307f0`
- end: `0x1800308e4`
- name: `UbpmUninitializeMaintenance`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029c70`

## callees

- `0x18002a750`
- `0x18002aa0c`
- `0x1800307f0`
- `0x1800308ec`
- `0x18003099c`
- `0x18003488c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800307fb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003089f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800307fb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003089f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003082a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003082a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800308dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800308a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800308a5`
- `EventAggregation!EADeleteAggregateEvent` at `0x18003083c`
- `EventAggregation!EADeleteAggregateEvent` at `0x180030857`
- `EventAggregation!EADeleteAggregateEvent` at `0x18003083c`
- `EventAggregation!EADeleteAggregateEvent` at `0x180030857`
- `UMPDC!SleepstudyHelperDestroyLibrary` at `0x1800308bd`
- `UMPDC!SleepstudyHelperDestroyLibrary` at `0x1800308bd`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18003087f`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18003087f`

## pseudocode

```c
__int64 UbpmUninitializeMaintenance()
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  __int64 v2; // rcx

  RtlAcquireSRWLockExclusive(&g_MaintenancePilotLock);
  dword_18004CF00 = GetCurrentThreadId();
  byte_18004CB30 = 0;
  UbpmpUninitializeWakeTimer();
  dword_18004CF00 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenancePilotLock);
  if ( qword_18004CB18 && (unsigned int)EADeleteAggregateEvent() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v0);
  if ( qword_18004CB28 && (unsigned int)EADeleteAggregateEvent() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v1);
  if ( qword_18004CB20 && (int)TbDeleteCEvent(qword_18004CB20) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  UbpmMaintenanceUninitializeTaskTriggers();
  UbpmpUninitializeMaintenanceLevels();
  RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
  dword_18004CEE8 = GetCurrentThreadId();
  if ( qword_18004CB48 )
    SleepstudyHelperDestroyLibrary();
  UbpmpUnregisterPdcClient();
  dword_18004CEE8 = 0;
  return RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
}

```

## disassembly

```asm
0x1800307f0  sub     rsp, 28h
0x1800307f4  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x1800307fb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180030801  call    cs:__imp_GetCurrentThreadId
0x180030807  mov     cs:dword_18004CF00, eax
0x18003080d  mov     cs:byte_18004CB30, 0
0x180030814  call    ?UbpmpUninitializeWakeTimer@@YAXXZ; UbpmpUninitializeWakeTimer(void)
0x180030819  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x180030820  mov     cs:dword_18004CF00, 0
0x18003082a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180030830  mov     rcx, cs:qword_18004CB18
0x180030837  test    rcx, rcx
0x18003083a  jz      short loc_18003084B
0x18003083c  call    cs:__imp_EADeleteAggregateEvent
0x180030842  test    eax, eax
0x180030844  jz      short loc_18003084B
0x180030846  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003084b  mov     rcx, cs:qword_18004CB28
0x180030852  test    rcx, rcx
0x180030855  jz      short loc_180030866
0x180030857  call    cs:__imp_EADeleteAggregateEvent
0x18003085d  test    eax, eax
0x18003085f  jz      short loc_180030866
0x180030861  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030866  cmp     dword ptr cs:qword_18004CB20, 0
0x18003086d  jnz     short loc_180030878
0x18003086f  cmp     dword ptr cs:qword_18004CB20+4, 0
0x180030876  jz      short loc_18003088E
0x180030878  mov     rcx, cs:qword_18004CB20
0x18003087f  call    cs:__imp_TbDeleteCEvent
0x180030885  test    eax, eax
0x180030887  jns     short loc_18003088E
0x180030889  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003088e  call    UbpmMaintenanceUninitializeTaskTriggers
0x180030893  call    ?UbpmpUninitializeMaintenanceLevels@@YAXXZ; UbpmpUninitializeMaintenanceLevels(void)
0x180030898  lea     rcx, g_MaintenanceLaunchLock
0x18003089f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800308a5  call    cs:__imp_GetCurrentThreadId
0x1800308ab  mov     rcx, cs:qword_18004CB48
0x1800308b2  mov     cs:dword_18004CEE8, eax
0x1800308b8  test    rcx, rcx
0x1800308bb  jz      short loc_1800308C3
0x1800308bd  call    cs:__imp_SleepstudyHelperDestroyLibrary
0x1800308c3  call    ?UbpmpUnregisterPdcClient@@YAXXZ; UbpmpUnregisterPdcClient(void)
0x1800308c8  lea     rcx, g_MaintenanceLaunchLock
0x1800308cf  mov     cs:dword_18004CEE8, 0
0x1800308d9  add     rsp, 28h
0x1800308dd  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
