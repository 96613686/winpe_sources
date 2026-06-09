# WJRegisterCloudDomainJoinRunRecoveryMonitor

- ea: `0x18001cdcc`
- end: `0x18001cf1b`
- name: `WJRegisterCloudDomainJoinRunRecoveryMonitor`
- size: `335`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011438`

## callees

- `0x18001cdcc`
- `0x18001e420`
- `0x18001ed46`
- `0x18002b6fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ceca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ceca`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ce68`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ce68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce7c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001ce32`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001ce32`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ce56`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ce56`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ce0d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001cef2`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ce0d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001cef2`

## string_xrefs

- `0x18001ce4f`: `AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x.`

## pseudocode

```c
__int64 WJRegisterCloudDomainJoinRunRecoveryMonitor()
{
  unsigned int PersistedRegistryLocationW; // eax
  int v1; // ebx
  __int64 v2; // rdx
  struct _FILETIME v3; // rcx
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v7; // [rsp+20h] [rbp-268h]
  __int64 v8; // [rsp+30h] [rbp-258h]
  WCHAR v9[264]; // [rsp+60h] [rbp-228h] BYREF

  memset_0(v9, 0, 0x208u);
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJRegisterCloudDomainJoinRunRecoveryMonitor");
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreLoadParametersAad",
                                 g_szAADCloudAPPluginParamsKey,
                                 v9,
                                 520,
                                 0);
  v1 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x.",
      L"WJRegisterCloudDomainJoinRunRecoveryMonitor",
      L"IDStoreLoadParametersAad",
      PersistedRegistryLocationW);
  }
  else
  {
    InitializeCriticalSection(&g_RecoveryCriticalSection);
    g_fRecoveryCriticalSectionInitialized = 1;
    EnterCriticalSection(&g_RecoveryCriticalSection);
    v1 = WJRegisterKeyNotification(
           v3,
           v2,
           v9,
           v4,
           v7,
           1,
           v8,
           (__int64)g_szRecoveryCheckTaskName,
           (HKEY)L"Recovery",
           (HKEY)&g_RecoveryCriticalSection,
           (HKEY)WJComputeCloudDomainJoinRecoveryTaskState,
           g_RecoveryNotification);
    LeaveCriticalSection(&g_RecoveryCriticalSection);
  }
  if ( v1 > 0 )
    v5 = (unsigned __int16)v1 | 0x80070000;
  else
    v5 = (unsigned int)v1;
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - hr: 0x%08x",
    L"WJRegisterCloudDomainJoinRunRecoveryMonitor",
    v5);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001cdcc  mov     [rsp+arg_0], rbx
0x18001cdd1  push    rdi
0x18001cdd2  sub     rsp, 280h
0x18001cdd9  mov     rax, cs:__security_cookie
0x18001cde0  xor     rax, rsp
0x18001cde3  mov     [rsp+288h+var_18], rax
0x18001cdeb  mov     ebx, 208h
0x18001cdf0  lea     rcx, [rsp+288h+var_228]; void *
0x18001cdf5  mov     r8d, ebx; Size
0x18001cdf8  xor     edx, edx; Val
0x18001cdfa  call    memset_0
0x18001cdff  lea     rdx, aWjregisterclou; "WJRegisterCloudDomainJoinRunRecoveryMon"...
0x18001ce06  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001ce0d  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ce13  mov     r9d, ebx
0x18001ce16  mov     [rsp+288h+var_268], 0
0x18001ce1f  lea     r8, [rsp+288h+var_228]
0x18001ce24  lea     rdx, g_szAADCloudAPPluginParamsKey; "Software\\Microsoft\\IdentityStore\\Loa"...
0x18001ce2b  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001ce32  call    cs:__imp_GetPersistedRegistryLocationW
0x18001ce38  mov     ebx, eax
0x18001ce3a  test    eax, eax
0x18001ce3c  jz      short loc_18001CE5E
0x18001ce3e  mov     r9d, eax
0x18001ce41  lea     r8, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001ce48  lea     rdx, aWjregisterclou; "WJRegisterCloudDomainJoinRunRecoveryMon"...
0x18001ce4f  lea     rcx, aAutojoinsvcSGe; "AutoJoinSvc/%s: GetPersistedRegistryLoc"...
0x18001ce56  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ce5c  jmp     short loc_18001CED0
0x18001ce5e  lea     rdi, g_RecoveryCriticalSection
0x18001ce65  mov     rcx, rdi; lpCriticalSection
0x18001ce68  call    cs:__imp_InitializeCriticalSection
0x18001ce6e  mov     ebx, 1
0x18001ce73  mov     rcx, rdi; lpCriticalSection
0x18001ce76  mov     cs:g_fRecoveryCriticalSectionInitialized, ebx
0x18001ce7c  call    cs:__imp_EnterCriticalSection
0x18001ce82  lea     rax, g_RecoveryNotification
0x18001ce89  mov     [rsp+288h+var_230], rax
0x18001ce8e  lea     r8, [rsp+288h+var_228]
0x18001ce93  lea     rax, WJComputeCloudDomainJoinRecoveryTaskState
0x18001ce9a  mov     [rsp+288h+var_238], rax
0x18001ce9f  lea     rax, aRecovery; "Recovery"
0x18001cea6  mov     [rsp+288h+var_240], rdi
0x18001ceab  mov     [rsp+288h+var_248], rax
0x18001ceb0  lea     rax, g_szRecoveryCheckTaskName; "Recovery-Check"
0x18001ceb7  mov     [rsp+288h+var_250], rax
0x18001cebc  mov     [rsp+288h+var_260], ebx
0x18001cec0  call    WJRegisterKeyNotification
0x18001cec5  mov     rcx, rdi; lpCriticalSection
0x18001cec8  mov     ebx, eax
0x18001ceca  call    cs:__imp_LeaveCriticalSection
0x18001ced0  test    ebx, ebx
0x18001ced2  jg      short loc_18001CED9
0x18001ced4  mov     r8d, ebx
0x18001ced7  jmp     short loc_18001CEE4
0x18001ced9  movzx   r8d, bx
0x18001cedd  or      r8d, 80070000h
0x18001cee4  lea     rdx, aWjregisterclou; "WJRegisterCloudDomainJoinRunRecoveryMon"...
0x18001ceeb  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001cef2  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001cef8  mov     eax, ebx
0x18001cefa  mov     rcx, [rsp+288h+var_18]
0x18001cf02  xor     rcx, rsp; StackCookie
0x18001cf05  call    __security_check_cookie
0x18001cf0a  mov     rbx, [rsp+288h+arg_0]
0x18001cf12  add     rsp, 280h
0x18001cf19  pop     rdi
0x18001cf1a  retn
```
