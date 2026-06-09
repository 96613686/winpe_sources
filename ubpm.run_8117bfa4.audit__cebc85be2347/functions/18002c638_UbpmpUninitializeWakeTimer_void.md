# UbpmpUninitializeWakeTimer(void)

- ea: `0x18002c638`
- end: `0x18002c6d9`
- name: `?UbpmpUninitializeWakeTimer@@YAXXZ`
- size: `161`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180032acc`
- `0x1800390b0`

## callees

- `0x18002c638`
- `0x180036d44`

## import_xrefs

- `EventAggregation!EADeleteAggregateEvent` at `0x18002c648`
- `EventAggregation!EADeleteAggregateEvent` at `0x18002c648`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18002c680`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18002c680`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18002c6b5`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18002c6b5`

## pseudocode

```c
void UbpmpUninitializeWakeTimer(void)
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( qword_18004FC10 )
  {
    if ( (unsigned int)EADeleteAggregateEvent() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v0);
    qword_18004FC10 = 0;
  }
  if ( qword_18004FC08 )
  {
    if ( (unsigned int)DabUnregisterTriggerConsumer(&qword_18004FC08, 1, 0) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v1);
    qword_18004FC08 = 0;
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
0x18002c638  sub     rsp, 28h
0x18002c63c  mov     rcx, cs:qword_18004FC10
0x18002c643  test    rcx, rcx
0x18002c646  jz      short loc_18002C668
0x18002c648  call    cs:__imp_EADeleteAggregateEvent
0x18002c64f  nop     dword ptr [rax+rax+00h]
0x18002c654  test    eax, eax
0x18002c656  jz      short loc_18002C65D
0x18002c658  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c65d  mov     cs:qword_18004FC10, 0
0x18002c668  cmp     cs:qword_18004FC08, 0
0x18002c670  jz      short loc_18002C6A2
0x18002c672  xor     r8d, r8d
0x18002c675  lea     rcx, qword_18004FC08
0x18002c67c  lea     edx, [r8+1]
0x18002c680  call    cs:__imp_DabUnregisterTriggerConsumer
0x18002c687  nop     dword ptr [rax+rax+00h]
0x18002c68c  test    eax, eax
0x18002c68e  jz      short loc_18002C695
0x18002c690  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c695  mov     cs:qword_18004FC08, 0
0x18002c6a0  jmp     short loc_18002C6D3
0x18002c6a2  mov     rcx, cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002c6a9  test    ecx, ecx
0x18002c6ab  jnz     short loc_18002C6B5
0x18002c6ad  cmp     dword ptr cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A+4, ecx; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002c6b3  jz      short loc_18002C6D3
0x18002c6b5  call    cs:__imp_TbDeleteCEvent
0x18002c6bc  nop     dword ptr [rax+rax+00h]
0x18002c6c1  test    eax, eax
0x18002c6c3  jns     short loc_18002C6CA
0x18002c6c5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c6ca  xor     eax, eax
0x18002c6cc  mov     cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A, rax; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002c6d3  add     rsp, 28h
0x18002c6d7  retn
```
