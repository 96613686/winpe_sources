# WJShutdownWorkplaceJoin

- ea: `0x18002bed8`
- end: `0x18002bf96`
- name: `WJShutdownWorkplaceJoin`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002db4c`

## callees

- `0x18002b344`
- `0x18002b39c`
- `0x18002b484`
- `0x18002bed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bf24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bf44`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bf24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bf44`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002beea`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002beea`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bf8f`

## pseudocode

```c
__int64 WJShutdownWorkplaceJoin()
{
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJShutdownWorkplaceJoin");
  WJFinalizeRegistryNotification((__int64)g_GlobalPolicyNotification);
  WJFinalizeRegistryNotification((__int64)g_LocalPolicyNotification);
  WJFinalizeRegistryNotification((__int64)g_RecoveryNotification);
  if ( g_fAutoJoinCriticalSectionInitialized )
  {
    DeleteCriticalSection(&g_AutoJoinCriticalSection);
    g_fAutoJoinCriticalSectionInitialized = 0;
  }
  if ( g_fRecoveryCriticalSectionInitialized )
  {
    DeleteCriticalSection(&g_RecoveryCriticalSection);
    g_fRecoveryCriticalSectionInitialized = 0;
  }
  WJCloseAutoJoinTriggerEventTimer();
  WJCloseSetTaskStateRetryTimer(g_AutoJoinTaskRetryState);
  WJCloseSetTaskStateRetryTimer(g_DeviceUpdateTaskRetryState);
  WJCloseSetTaskStateRetryTimer(g_RecoveryCheckTaskRetryState);
  return DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished", L"WJShutdownWorkplaceJoin");
}

```

## disassembly

```asm
0x18002bed8  sub     rsp, 28h
0x18002bedc  lea     rdx, aWjshutdownwork; "WJShutdownWorkplaceJoin"
0x18002bee3  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002beea  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002bef0  lea     rcx, g_GlobalPolicyNotification
0x18002bef7  call    WJFinalizeRegistryNotification
0x18002befc  lea     rcx, g_LocalPolicyNotification
0x18002bf03  call    WJFinalizeRegistryNotification
0x18002bf08  lea     rcx, g_RecoveryNotification
0x18002bf0f  call    WJFinalizeRegistryNotification
0x18002bf14  cmp     cs:g_fAutoJoinCriticalSectionInitialized, 0
0x18002bf1b  jz      short loc_18002BF34
0x18002bf1d  lea     rcx, g_AutoJoinCriticalSection; lpCriticalSection
0x18002bf24  call    cs:__imp_DeleteCriticalSection
0x18002bf2a  mov     cs:g_fAutoJoinCriticalSectionInitialized, 0
0x18002bf34  cmp     cs:g_fRecoveryCriticalSectionInitialized, 0
0x18002bf3b  jz      short loc_18002BF54
0x18002bf3d  lea     rcx, g_RecoveryCriticalSection; lpCriticalSection
0x18002bf44  call    cs:__imp_DeleteCriticalSection
0x18002bf4a  mov     cs:g_fRecoveryCriticalSectionInitialized, 0
0x18002bf54  call    WJCloseAutoJoinTriggerEventTimer
0x18002bf59  lea     rcx, g_AutoJoinTaskRetryState
0x18002bf60  call    WJCloseSetTaskStateRetryTimer
0x18002bf65  lea     rcx, g_DeviceUpdateTaskRetryState
0x18002bf6c  call    WJCloseSetTaskStateRetryTimer
0x18002bf71  lea     rcx, g_RecoveryCheckTaskRetryState
0x18002bf78  call    WJCloseSetTaskStateRetryTimer
0x18002bf7d  lea     rdx, aWjshutdownwork; "WJShutdownWorkplaceJoin"
0x18002bf84  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002bf8b  add     rsp, 28h
0x18002bf8f  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
