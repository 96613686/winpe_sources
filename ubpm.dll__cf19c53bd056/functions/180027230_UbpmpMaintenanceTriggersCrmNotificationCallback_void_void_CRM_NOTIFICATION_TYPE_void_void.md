# UbpmpMaintenanceTriggersCrmNotificationCallback(void *,void *,_CRM_NOTIFICATION_TYPE,void *,void *)

- ea: `0x180027230`
- end: `0x1800272d4`
- name: `?UbpmpMaintenanceTriggersCrmNotificationCallback@@YAXPEAX0W4_CRM_NOTIFICATION_TYPE@@00@Z`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180027230`
- `0x1800272dc`
- `0x180027424`
- `0x1800274e4`
- `0x18003488c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027257`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027257`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002728e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002728e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002725d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002725d`

## pseudocode

```c
void __fastcall UbpmpMaintenanceTriggersCrmNotificationCallback(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int8 *a5)
{
  __int64 v6; // rdi
  __int64 v7; // rdx
  unsigned __int8 *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx

  if ( a3 <= 1 )
  {
    v6 = *a5;
    RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
    dword_18004CEE8 = GetCurrentThreadId();
    v8 = a5 + 40;
    LOBYTE(v9) = v6;
    if ( a3 )
    {
      a5[32] = 0;
      UbpmTelemMaintenanceWindowStopped(v9, v7, v8);
    }
    else
    {
      a5[32] = 1;
      UbpmTelemMaintenanceWindowStarted(v9, v7, v8);
      if ( (int)PubSebEdgeEventValueInternal(*(&g_MaintenanceTriggers + 2 * v6), v10, 0, 0) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    }
    dword_18004CEE8 = 0;
    RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
  }
}

```

## disassembly

```asm
0x180027230  cmp     r8d, 1
0x180027234  ja      short locret_1800272A3
0x180027236  mov     [rsp+arg_0], rbx
0x18002723b  mov     [rsp+arg_8], rsi
0x180027240  push    rdi
0x180027241  sub     rsp, 40h
0x180027245  mov     rbx, [rsp+48h+arg_20]
0x18002724a  lea     rcx, g_MaintenanceLaunchLock
0x180027251  mov     esi, r8d
0x180027254  movzx   edi, byte ptr [rbx]
0x180027257  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002725d  call    cs:__imp_GetCurrentThreadId
0x180027263  mov     cs:dword_18004CEE8, eax
0x180027269  lea     r8, [rbx+28h]
0x18002726d  mov     cl, dil
0x180027270  test    esi, esi
0x180027272  jz      short loc_1800272A4
0x180027274  mov     byte ptr [rbx+20h], 0
0x180027278  call    UbpmTelemMaintenanceWindowStopped
0x18002727d  lea     rcx, g_MaintenanceLaunchLock
0x180027284  mov     cs:dword_18004CEE8, 0
0x18002728e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180027294  mov     rbx, [rsp+48h+arg_0]
0x180027299  mov     rsi, [rsp+48h+arg_8]
0x18002729e  add     rsp, 40h
0x1800272a2  pop     rdi
0x1800272a3  retn
0x1800272a4  mov     byte ptr [rbx+20h], 1
0x1800272a8  call    UbpmTelemMaintenanceWindowStarted
0x1800272ad  lea     rax, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x1800272b4  mov     rcx, rdi
0x1800272b7  add     rcx, rcx
0x1800272ba  xor     r9d, r9d
0x1800272bd  xor     r8d, r8d
0x1800272c0  mov     rcx, [rax+rcx*8]
0x1800272c4  call    PubSebEdgeEventValueInternal
0x1800272c9  test    eax, eax
0x1800272cb  jns     short loc_18002727D
0x1800272cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800272d2  jmp     short loc_18002727D
```
