# UbpmpUninitializeWakeTimer(void)

- ea: `0x18002aa0c`
- end: `0x18002aa9a`
- name: `?UbpmpUninitializeWakeTimer@@YAXXZ`
- size: `142`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800307f0`
- `0x180036a90`

## callees

- `0x18002aa0c`
- `0x18003488c`

## import_xrefs

- `EventAggregation!EADeleteAggregateEvent` at `0x18002aa1c`
- `EventAggregation!EADeleteAggregateEvent` at `0x18002aa1c`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18002aa4e`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18002aa4e`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18002aa7d`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18002aa7d`

## pseudocode

```c
void UbpmpUninitializeWakeTimer(void)
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( qword_18004CB10 )
  {
    if ( (unsigned int)EADeleteAggregateEvent() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v0);
    qword_18004CB10 = 0;
  }
  if ( qword_18004CB08 )
  {
    if ( (unsigned int)DabUnregisterTriggerConsumer(&qword_18004CB08, 1, 0) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v1);
    qword_18004CB08 = 0;
  }
  else if ( g_MaintenancePilot || *(&g_MaintenancePilot + 1) )
  {
    if ( (int)TbDeleteCEvent(g_MaintenancePilot) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    g_MaintenancePilot = 0;
  }
}

```

## disassembly

```asm
0x18002aa0c  sub     rsp, 28h
0x18002aa10  mov     rcx, cs:qword_18004CB10
0x18002aa17  test    rcx, rcx
0x18002aa1a  jz      short loc_18002AA36
0x18002aa1c  call    cs:__imp_EADeleteAggregateEvent
0x18002aa22  test    eax, eax
0x18002aa24  jz      short loc_18002AA2B
0x18002aa26  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002aa2b  mov     cs:qword_18004CB10, 0
0x18002aa36  cmp     cs:qword_18004CB08, 0
0x18002aa3e  jz      short loc_18002AA6A
0x18002aa40  xor     r8d, r8d
0x18002aa43  lea     rcx, qword_18004CB08
0x18002aa4a  lea     edx, [r8+1]
0x18002aa4e  call    cs:__imp_DabUnregisterTriggerConsumer
0x18002aa54  test    eax, eax
0x18002aa56  jz      short loc_18002AA5D
0x18002aa58  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002aa5d  mov     cs:qword_18004CB08, 0
0x18002aa68  jmp     short loc_18002AA95
0x18002aa6a  mov     rcx, cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002aa71  test    ecx, ecx
0x18002aa73  jnz     short loc_18002AA7D
0x18002aa75  cmp     dword ptr cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A+4, ecx; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002aa7b  jz      short loc_18002AA95
0x18002aa7d  call    cs:__imp_TbDeleteCEvent
0x18002aa83  test    eax, eax
0x18002aa85  jns     short loc_18002AA8C
0x18002aa87  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002aa8c  xor     eax, eax
0x18002aa8e  mov     cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A, rax; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002aa95  add     rsp, 28h
0x18002aa99  retn
```
