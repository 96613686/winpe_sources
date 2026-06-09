# WJShutdownWorkplaceJoin

- ea: `0x18002e6ac`
- end: `0x18002e781`
- name: `WJShutdownWorkplaceJoin`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180030544`

## callees

- `0x18002d974`
- `0x18002d9dc`
- `0x18002daf0`
- `0x18002e6ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e6fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e724`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e6fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e724`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e6be`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e6be`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e775`

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
0x18002e6ac  sub     rsp, 28h
0x18002e6b0  lea     rdx, aWjshutdownwork; "WJShutdownWorkplaceJoin"
0x18002e6b7  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002e6be  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e6c5  nop     dword ptr [rax+rax+00h]
0x18002e6ca  lea     rcx, g_GlobalPolicyNotification
0x18002e6d1  call    WJFinalizeRegistryNotification
0x18002e6d6  lea     rcx, g_LocalPolicyNotification
0x18002e6dd  call    WJFinalizeRegistryNotification
0x18002e6e2  lea     rcx, g_RecoveryNotification
0x18002e6e9  call    WJFinalizeRegistryNotification
0x18002e6ee  cmp     cs:g_fAutoJoinCriticalSectionInitialized, 0
0x18002e6f5  jz      short loc_18002E714
0x18002e6f7  lea     rcx, g_AutoJoinCriticalSection; lpCriticalSection
0x18002e6fe  call    cs:__imp_DeleteCriticalSection
0x18002e705  nop     dword ptr [rax+rax+00h]
0x18002e70a  mov     cs:g_fAutoJoinCriticalSectionInitialized, 0
0x18002e714  cmp     cs:g_fRecoveryCriticalSectionInitialized, 0
0x18002e71b  jz      short loc_18002E73A
0x18002e71d  lea     rcx, g_RecoveryCriticalSection; lpCriticalSection
0x18002e724  call    cs:__imp_DeleteCriticalSection
0x18002e72b  nop     dword ptr [rax+rax+00h]
0x18002e730  mov     cs:g_fRecoveryCriticalSectionInitialized, 0
0x18002e73a  call    WJCloseAutoJoinTriggerEventTimer
0x18002e73f  lea     rcx, g_AutoJoinTaskRetryState
0x18002e746  call    WJCloseSetTaskStateRetryTimer
0x18002e74b  lea     rcx, g_DeviceUpdateTaskRetryState
0x18002e752  call    WJCloseSetTaskStateRetryTimer
0x18002e757  lea     rcx, g_RecoveryCheckTaskRetryState
0x18002e75e  call    WJCloseSetTaskStateRetryTimer
0x18002e763  lea     rdx, aWjshutdownwork; "WJShutdownWorkplaceJoin"
0x18002e76a  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002e771  add     rsp, 28h
0x18002e775  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
