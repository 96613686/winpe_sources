# UmpoNotifyClose

- ea: `0x18000dc64`
- end: `0x18000deaa`
- name: `UmpoNotifyClose`
- size: `582`
- prototype: `void()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015280`

## callees

- `0x18000dc64`
- `0x18000f3dc`
- `0x18000f7d8`
- `0x18000f864`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000ddda`
- `ntdll!RtlFreeHeap` at `0x18000ddec`
- `ntdll!RtlFreeHeap` at `0x18000ddda`
- `ntdll!RtlFreeHeap` at `0x18000ddec`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dcd6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dcef`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd08`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd21`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd3a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd53`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd6c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dcd6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dcef`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd08`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd21`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd3a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd53`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000dd6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000dc85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000dcb0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000dc85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000dcb0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000dc92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000dcbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000dc92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000dcbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd98`

## pseudocode

```c
void UmpoNotifyClose()
{
  _QWORD *v0; // rcx
  PVOID *v1; // rax
  void *v2; // r8
  _QWORD *v3; // rbx

  if ( UmpoPnpInitWork )
  {
    WaitForThreadpoolWorkCallbacks(UmpoPnpInitWork, 1);
    CloseThreadpoolWork(UmpoPnpInitWork);
    UmpoPnpInitWork = 0;
  }
  if ( UmpoPowerStatusChangeWorker )
  {
    WaitForThreadpoolWorkCallbacks(UmpoPowerStatusChangeWorker, 1);
    CloseThreadpoolWork(UmpoPowerStatusChangeWorker);
    UmpoPowerStatusChangeWorker = 0;
  }
  if ( UmpoGlobalUserPresenceHostStateWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoGlobalUserPresenceHostStateWnfSubscription);
    UmpoGlobalUserPresenceHostStateWnfSubscription = 0;
  }
  if ( UmpoBatterySaverHostStateWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoBatterySaverHostStateWnfSubscription);
    UmpoBatterySaverHostStateWnfSubscription = 0;
  }
  if ( UmpoBatteryInfoWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoBatteryInfoWnfSubscription);
    UmpoBatteryInfoWnfSubscription = 0;
  }
  if ( UmpoBatterySaverWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoBatterySaverWnfSubscription);
    UmpoBatterySaverWnfSubscription = 0;
  }
  if ( UmpoProvEngineWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoProvEngineWnfSubscription);
    UmpoProvEngineWnfSubscription = 0;
  }
  if ( UmpoScmWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoScmWnfSubscription);
    UmpoScmWnfSubscription = 0;
  }
  if ( UmpoEnergySaverOverrideWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoEnergySaverOverrideWnfSubscription);
    UmpoEnergySaverOverrideWnfSubscription = 0;
  }
  UmpoUninitializeEffectivePowerModeCallbacks();
  UmpoUnregisterPpmProfiles();
  if ( byte_180024F48 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoNotification);
  while ( 1 )
  {
    v3 = UmpoLegacyEventRegistrantList;
    if ( UmpoLegacyEventRegistrantList == &UmpoLegacyEventRegistrantList )
      break;
    v0 = *(_QWORD **)UmpoLegacyEventRegistrantList;
    if ( *(PVOID *)(*(_QWORD *)UmpoLegacyEventRegistrantList + 8LL) != UmpoLegacyEventRegistrantList
      || (v1 = (PVOID *)*((_QWORD *)UmpoLegacyEventRegistrantList + 1), *v1 != UmpoLegacyEventRegistrantList) )
    {
      __fastfail(3u);
    }
    *v1 = v0;
    v0[1] = v1;
    v2 = (void *)v3[4];
    if ( v2 )
      RtlFreeHeap(UmpoHeapHandle, 0, v2);
    RtlFreeHeap(UmpoHeapHandle, 0, v3);
  }
  if ( byte_180024F48 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoNotification);
  if ( byte_180024FA8 )
  {
    DeleteCriticalSection(&UmpoSchemeLock);
    byte_180024FA8 = 0;
  }
  if ( byte_180024F48 )
  {
    DeleteCriticalSection(&UmpoNotification);
    byte_180024F48 = 0;
  }
  if ( byte_180024E88 )
  {
    DeleteCriticalSection(&UmpoPowerStateNotificationLock);
    byte_180024E88 = 0;
  }
  if ( UmpoLegacyEventRegistrantList != &UmpoLegacyEventRegistrantList )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  UmpoAllowPublishingPowerEnlightenments = 0;
  UmpoDisplayState = 0;
  UmpoOnAcPower = 1;
}

```

## disassembly

```asm
0x18000dc64  mov     [rsp+arg_0], rbx
0x18000dc69  mov     [rsp+arg_8], rdi
0x18000dc6e  push    r14
0x18000dc70  sub     rsp, 20h
0x18000dc74  mov     rcx, cs:UmpoPnpInitWork; pwk
0x18000dc7b  xor     edi, edi
0x18000dc7d  test    rcx, rcx
0x18000dc80  jz      short loc_18000DC9F
0x18000dc82  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18000dc85  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000dc8b  mov     rcx, cs:UmpoPnpInitWork; pwk
0x18000dc92  call    cs:__imp_CloseThreadpoolWork
0x18000dc98  mov     cs:UmpoPnpInitWork, rdi
0x18000dc9f  mov     rcx, cs:UmpoPowerStatusChangeWorker; pwk
0x18000dca6  test    rcx, rcx
0x18000dca9  jz      short loc_18000DCCA
0x18000dcab  mov     edx, 1; fCancelPendingCallbacks
0x18000dcb0  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000dcb6  mov     rcx, cs:UmpoPowerStatusChangeWorker; pwk
0x18000dcbd  call    cs:__imp_CloseThreadpoolWork
0x18000dcc3  mov     cs:UmpoPowerStatusChangeWorker, rdi
0x18000dcca  mov     rcx, cs:UmpoGlobalUserPresenceHostStateWnfSubscription
0x18000dcd1  test    rcx, rcx
0x18000dcd4  jz      short loc_18000DCE3
0x18000dcd6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dcdc  mov     cs:UmpoGlobalUserPresenceHostStateWnfSubscription, rdi
0x18000dce3  mov     rcx, cs:UmpoBatterySaverHostStateWnfSubscription
0x18000dcea  test    rcx, rcx
0x18000dced  jz      short loc_18000DCFC
0x18000dcef  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dcf5  mov     cs:UmpoBatterySaverHostStateWnfSubscription, rdi
0x18000dcfc  mov     rcx, cs:UmpoBatteryInfoWnfSubscription
0x18000dd03  test    rcx, rcx
0x18000dd06  jz      short loc_18000DD15
0x18000dd08  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dd0e  mov     cs:UmpoBatteryInfoWnfSubscription, rdi
0x18000dd15  mov     rcx, cs:UmpoBatterySaverWnfSubscription
0x18000dd1c  test    rcx, rcx
0x18000dd1f  jz      short loc_18000DD2E
0x18000dd21  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dd27  mov     cs:UmpoBatterySaverWnfSubscription, rdi
0x18000dd2e  mov     rcx, cs:UmpoProvEngineWnfSubscription
0x18000dd35  test    rcx, rcx
0x18000dd38  jz      short loc_18000DD47
0x18000dd3a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dd40  mov     cs:UmpoProvEngineWnfSubscription, rdi
0x18000dd47  mov     rcx, cs:UmpoScmWnfSubscription
0x18000dd4e  test    rcx, rcx
0x18000dd51  jz      short loc_18000DD60
0x18000dd53  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dd59  mov     cs:UmpoScmWnfSubscription, rdi
0x18000dd60  mov     rcx, cs:UmpoEnergySaverOverrideWnfSubscription
0x18000dd67  test    rcx, rcx
0x18000dd6a  jz      short loc_18000DD79
0x18000dd6c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000dd72  mov     cs:UmpoEnergySaverOverrideWnfSubscription, rdi
0x18000dd79  call    UmpoUninitializeEffectivePowerModeCallbacks
0x18000dd7e  call    UmpoUnregisterPpmProfiles
0x18000dd83  cmp     cs:byte_180024F48, 1
0x18000dd8a  jz      short loc_18000DD91
0x18000dd8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dd91  lea     rcx, UmpoNotification; lpCriticalSection
0x18000dd98  call    cs:__imp_EnterCriticalSection
0x18000dd9e  lea     r14, UmpoLegacyEventRegistrantList
0x18000dda5  jmp     short loc_18000DDF2
0x18000dda7  mov     rcx, [rbx]
0x18000ddaa  cmp     [rcx+8], rbx
0x18000ddae  jnz     loc_18000DEA3
0x18000ddb4  mov     rax, [rbx+8]
0x18000ddb8  cmp     [rax], rbx
0x18000ddbb  jnz     loc_18000DEA3
0x18000ddc1  mov     [rax], rcx
0x18000ddc4  mov     [rcx+8], rax
0x18000ddc8  mov     r8, [rbx+20h]; P
0x18000ddcc  test    r8, r8
0x18000ddcf  jz      short loc_18000DDE0
0x18000ddd1  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000ddd8  xor     edx, edx; Flags
0x18000ddda  call    cs:__imp_RtlFreeHeap
0x18000dde0  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000dde7  mov     r8, rbx; P
0x18000ddea  xor     edx, edx; Flags
0x18000ddec  call    cs:__imp_RtlFreeHeap
0x18000ddf2  mov     rbx, cs:UmpoLegacyEventRegistrantList
0x18000ddf9  cmp     rbx, r14
0x18000ddfc  jnz     short loc_18000DDA7
0x18000ddfe  cmp     cs:byte_180024F48, 1
0x18000de05  jz      short loc_18000DE0C
0x18000de07  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000de0c  lea     rcx, UmpoNotification; lpCriticalSection
0x18000de13  call    cs:__imp_LeaveCriticalSection
0x18000de19  cmp     cs:byte_180024FA8, dil
0x18000de20  jz      short loc_18000DE36
0x18000de22  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000de29  call    cs:__imp_DeleteCriticalSection
0x18000de2f  mov     cs:byte_180024FA8, dil
0x18000de36  cmp     cs:byte_180024F48, dil
0x18000de3d  jz      short loc_18000DE53
0x18000de3f  lea     rcx, UmpoNotification; lpCriticalSection
0x18000de46  call    cs:__imp_DeleteCriticalSection
0x18000de4c  mov     cs:byte_180024F48, dil
0x18000de53  cmp     cs:byte_180024E88, dil
0x18000de5a  jz      short loc_18000DE70
0x18000de5c  lea     rcx, UmpoPowerStateNotificationLock; lpCriticalSection
0x18000de63  call    cs:__imp_DeleteCriticalSection
0x18000de69  mov     cs:byte_180024E88, dil
0x18000de70  cmp     cs:UmpoLegacyEventRegistrantList, r14
0x18000de77  jz      short loc_18000DE7E
0x18000de79  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000de7e  mov     rbx, [rsp+28h+arg_0]
0x18000de83  mov     cs:UmpoAllowPublishingPowerEnlightenments, dil
0x18000de8a  mov     cs:UmpoDisplayState, edi
0x18000de90  mov     rdi, [rsp+28h+arg_8]
0x18000de95  mov     cs:UmpoOnAcPower, 1
0x18000de9c  add     rsp, 20h
0x18000dea0  pop     r14
0x18000dea2  retn
0x18000dea3  mov     ecx, 3
0x18000dea8  int     29h; Win8: RtlFailFast(ecx)
```
