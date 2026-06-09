# ItSpStopIdleDetection(_ITSRV_GLOBAL_CONTEXT *)

- ea: `0x18007729c`
- end: `0x180077451`
- name: `?ItSpStopIdleDetection@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@@Z`
- size: `437`
- prototype: `void __fastcall(struct _ITSRV_GLOBAL_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800787fc`

## callees

- `0x18007729c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800772a7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800772a7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800772bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800772bf`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18007731d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18007731d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800773d3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800773d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180077400`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180077400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800773ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800773ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180077418`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180077418`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180077434`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180077434`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800772d7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800772fa`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180077340`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180077363`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180077386`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800773a9`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800772d7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800772fa`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180077340`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180077363`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180077386`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800773a9`

## pseudocode

```c
void __fastcall ItSpStopIdleDetection(struct _ITSRV_GLOBAL_CONTEXT *a1)
{
  ResetEvent(hHandle);
  if ( qword_1800C1410 )
    SetEvent(qword_1800C1410);
  if ( RegistrationHandle )
  {
    PowerSettingUnregisterNotification(RegistrationHandle);
    RegistrationHandle = 0;
  }
  if ( qword_1800C15B0 )
  {
    PowerSettingUnregisterNotification(qword_1800C15B0);
    qword_1800C15B0 = 0;
  }
  if ( qword_1800C15B8 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    qword_1800C15B8 = 0;
  }
  if ( qword_1800C15F8 )
  {
    PowerSettingUnregisterNotification(qword_1800C15F8);
    qword_1800C15F8 = 0;
  }
  if ( qword_1800C15E8 )
  {
    PowerSettingUnregisterNotification(qword_1800C15E8);
    qword_1800C15E8 = 0;
  }
  if ( qword_1800C15D8 )
  {
    PowerSettingUnregisterNotification(qword_1800C15D8);
    qword_1800C15D8 = 0;
  }
  if ( qword_1800C1608 )
  {
    PowerSettingUnregisterNotification(qword_1800C1608);
    qword_1800C1608 = 0;
  }
  if ( ptpcg )
  {
    RtlAcquireSRWLockExclusive(&stru_1800C13F8);
    CloseThreadpoolCleanupGroupMembers(ptpcg, 1, 0);
    RtlReleaseSRWLockExclusive(&stru_1800C13F8);
    if ( ptpcg )
      CloseThreadpoolCleanupGroup(ptpcg);
  }
  DeleteTimerQueueTimer(0, Timer, hHandle);
  Timer = 0;
}

```

## disassembly

```asm
0x18007729c  sub     rsp, 28h
0x1800772a0  mov     rcx, cs:hHandle; hEvent
0x1800772a7  call    cs:__imp_ResetEvent
0x1800772ae  nop     dword ptr [rax+rax+00h]
0x1800772b3  mov     rcx, cs:qword_1800C1410; hEvent
0x1800772ba  test    rcx, rcx
0x1800772bd  jz      short loc_1800772CB
0x1800772bf  call    cs:__imp_SetEvent
0x1800772c6  nop     dword ptr [rax+rax+00h]
0x1800772cb  mov     rcx, cs:RegistrationHandle; RegistrationHandle
0x1800772d2  test    rcx, rcx
0x1800772d5  jz      short loc_1800772EE
0x1800772d7  call    cs:__imp_PowerSettingUnregisterNotification
0x1800772de  nop     dword ptr [rax+rax+00h]
0x1800772e3  mov     cs:RegistrationHandle, 0
0x1800772ee  mov     rcx, cs:qword_1800C15B0; RegistrationHandle
0x1800772f5  test    rcx, rcx
0x1800772f8  jz      short loc_180077311
0x1800772fa  call    cs:__imp_PowerSettingUnregisterNotification
0x180077301  nop     dword ptr [rax+rax+00h]
0x180077306  mov     cs:qword_1800C15B0, 0
0x180077311  mov     rcx, cs:qword_1800C15B8
0x180077318  test    rcx, rcx
0x18007731b  jz      short loc_180077334
0x18007731d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180077324  nop     dword ptr [rax+rax+00h]
0x180077329  mov     cs:qword_1800C15B8, 0
0x180077334  mov     rcx, cs:qword_1800C15F8; RegistrationHandle
0x18007733b  test    rcx, rcx
0x18007733e  jz      short loc_180077357
0x180077340  call    cs:__imp_PowerSettingUnregisterNotification
0x180077347  nop     dword ptr [rax+rax+00h]
0x18007734c  mov     cs:qword_1800C15F8, 0
0x180077357  mov     rcx, cs:qword_1800C15E8; RegistrationHandle
0x18007735e  test    rcx, rcx
0x180077361  jz      short loc_18007737A
0x180077363  call    cs:__imp_PowerSettingUnregisterNotification
0x18007736a  nop     dword ptr [rax+rax+00h]
0x18007736f  mov     cs:qword_1800C15E8, 0
0x18007737a  mov     rcx, cs:qword_1800C15D8; RegistrationHandle
0x180077381  test    rcx, rcx
0x180077384  jz      short loc_18007739D
0x180077386  call    cs:__imp_PowerSettingUnregisterNotification
0x18007738d  nop     dword ptr [rax+rax+00h]
0x180077392  mov     cs:qword_1800C15D8, 0
0x18007739d  mov     rcx, cs:qword_1800C1608; RegistrationHandle
0x1800773a4  test    rcx, rcx
0x1800773a7  jz      short loc_1800773C0
0x1800773a9  call    cs:__imp_PowerSettingUnregisterNotification
0x1800773b0  nop     dword ptr [rax+rax+00h]
0x1800773b5  mov     cs:qword_1800C1608, 0
0x1800773c0  mov     rcx, cs:ptpcg
0x1800773c7  test    rcx, rcx
0x1800773ca  jz      short loc_180077424
0x1800773cc  lea     rcx, stru_1800C13F8
0x1800773d3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800773da  nop     dword ptr [rax+rax+00h]
0x1800773df  mov     rcx, cs:ptpcg; ptpcg
0x1800773e6  xor     r8d, r8d; pvCleanupContext
0x1800773e9  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800773ed  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800773f4  nop     dword ptr [rax+rax+00h]
0x1800773f9  lea     rcx, stru_1800C13F8
0x180077400  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180077407  nop     dword ptr [rax+rax+00h]
0x18007740c  mov     rcx, cs:ptpcg; ptpcg
0x180077413  test    rcx, rcx
0x180077416  jz      short loc_180077424
0x180077418  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18007741f  nop     dword ptr [rax+rax+00h]
0x180077424  mov     r8, cs:hHandle; CompletionEvent
0x18007742b  xor     ecx, ecx; TimerQueue
0x18007742d  mov     rdx, cs:Timer; Timer
0x180077434  call    cs:__imp_DeleteTimerQueueTimer
0x18007743b  nop     dword ptr [rax+rax+00h]
0x180077440  mov     cs:Timer, 0
0x18007744b  add     rsp, 28h
0x18007744f  retn
```
