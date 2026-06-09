# ItSpStopIdleDetection(_ITSRV_GLOBAL_CONTEXT *)

- ea: `0x1800736b8`
- end: `0x180073818`
- name: `?ItSpStopIdleDetection@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@@Z`
- size: `352`
- prototype: `void __fastcall(struct _ITSRV_GLOBAL_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180074918`

## callees

- `0x1800736b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800736c3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800736c3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800736d5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800736d5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180073721`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180073721`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800737b9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800737b9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800737da`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800737da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800737cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800737cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800737ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800737ec`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180073802`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180073802`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800736e7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180073704`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18007373e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18007375b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180073778`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180073795`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800736e7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180073704`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18007373e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18007375b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180073778`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180073795`

## pseudocode

```c
void __fastcall ItSpStopIdleDetection(struct _ITSRV_GLOBAL_CONTEXT *a1)
{
  ResetEvent(hHandle);
  if ( qword_1800BD310 )
    SetEvent(qword_1800BD310);
  if ( RegistrationHandle )
  {
    PowerSettingUnregisterNotification(RegistrationHandle);
    RegistrationHandle = 0;
  }
  if ( qword_1800BD4B0 )
  {
    PowerSettingUnregisterNotification(qword_1800BD4B0);
    qword_1800BD4B0 = 0;
  }
  if ( qword_1800BD4B8 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    qword_1800BD4B8 = 0;
  }
  if ( qword_1800BD4F8 )
  {
    PowerSettingUnregisterNotification(qword_1800BD4F8);
    qword_1800BD4F8 = 0;
  }
  if ( qword_1800BD4E8 )
  {
    PowerSettingUnregisterNotification(qword_1800BD4E8);
    qword_1800BD4E8 = 0;
  }
  if ( qword_1800BD4D8 )
  {
    PowerSettingUnregisterNotification(qword_1800BD4D8);
    qword_1800BD4D8 = 0;
  }
  if ( qword_1800BD508 )
  {
    PowerSettingUnregisterNotification(qword_1800BD508);
    qword_1800BD508 = 0;
  }
  if ( ptpcg )
  {
    RtlAcquireSRWLockExclusive(&stru_1800BD2F8);
    CloseThreadpoolCleanupGroupMembers(ptpcg, 1, 0);
    RtlReleaseSRWLockExclusive(&stru_1800BD2F8);
    if ( ptpcg )
      CloseThreadpoolCleanupGroup(ptpcg);
  }
  DeleteTimerQueueTimer(0, Timer, hHandle);
  Timer = 0;
}

```

## disassembly

```asm
0x1800736b8  sub     rsp, 28h
0x1800736bc  mov     rcx, cs:hHandle; hEvent
0x1800736c3  call    cs:__imp_ResetEvent
0x1800736c9  mov     rcx, cs:qword_1800BD310; hEvent
0x1800736d0  test    rcx, rcx
0x1800736d3  jz      short loc_1800736DB
0x1800736d5  call    cs:__imp_SetEvent
0x1800736db  mov     rcx, cs:RegistrationHandle; RegistrationHandle
0x1800736e2  test    rcx, rcx
0x1800736e5  jz      short loc_1800736F8
0x1800736e7  call    cs:__imp_PowerSettingUnregisterNotification
0x1800736ed  mov     cs:RegistrationHandle, 0
0x1800736f8  mov     rcx, cs:qword_1800BD4B0; RegistrationHandle
0x1800736ff  test    rcx, rcx
0x180073702  jz      short loc_180073715
0x180073704  call    cs:__imp_PowerSettingUnregisterNotification
0x18007370a  mov     cs:qword_1800BD4B0, 0
0x180073715  mov     rcx, cs:qword_1800BD4B8
0x18007371c  test    rcx, rcx
0x18007371f  jz      short loc_180073732
0x180073721  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180073727  mov     cs:qword_1800BD4B8, 0
0x180073732  mov     rcx, cs:qword_1800BD4F8; RegistrationHandle
0x180073739  test    rcx, rcx
0x18007373c  jz      short loc_18007374F
0x18007373e  call    cs:__imp_PowerSettingUnregisterNotification
0x180073744  mov     cs:qword_1800BD4F8, 0
0x18007374f  mov     rcx, cs:qword_1800BD4E8; RegistrationHandle
0x180073756  test    rcx, rcx
0x180073759  jz      short loc_18007376C
0x18007375b  call    cs:__imp_PowerSettingUnregisterNotification
0x180073761  mov     cs:qword_1800BD4E8, 0
0x18007376c  mov     rcx, cs:qword_1800BD4D8; RegistrationHandle
0x180073773  test    rcx, rcx
0x180073776  jz      short loc_180073789
0x180073778  call    cs:__imp_PowerSettingUnregisterNotification
0x18007377e  mov     cs:qword_1800BD4D8, 0
0x180073789  mov     rcx, cs:qword_1800BD508; RegistrationHandle
0x180073790  test    rcx, rcx
0x180073793  jz      short loc_1800737A6
0x180073795  call    cs:__imp_PowerSettingUnregisterNotification
0x18007379b  mov     cs:qword_1800BD508, 0
0x1800737a6  mov     rcx, cs:ptpcg
0x1800737ad  test    rcx, rcx
0x1800737b0  jz      short loc_1800737F2
0x1800737b2  lea     rcx, stru_1800BD2F8
0x1800737b9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800737bf  mov     rcx, cs:ptpcg; ptpcg
0x1800737c6  xor     r8d, r8d; pvCleanupContext
0x1800737c9  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800737cd  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800737d3  lea     rcx, stru_1800BD2F8
0x1800737da  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800737e0  mov     rcx, cs:ptpcg; ptpcg
0x1800737e7  test    rcx, rcx
0x1800737ea  jz      short loc_1800737F2
0x1800737ec  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800737f2  mov     r8, cs:hHandle; CompletionEvent
0x1800737f9  xor     ecx, ecx; TimerQueue
0x1800737fb  mov     rdx, cs:Timer; Timer
0x180073802  call    cs:__imp_DeleteTimerQueueTimer
0x180073808  mov     cs:Timer, 0
0x180073813  add     rsp, 28h
0x180073817  retn
```
