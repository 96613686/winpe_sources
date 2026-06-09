# WJRegisterCloudDomainJoinRunRecoveryMonitor

- ea: `0x18001e3bc`
- end: `0x18001e539`
- name: `WJRegisterCloudDomainJoinRunRecoveryMonitor`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012368`

## callees

- `0x18001e3bc`
- `0x18001fbd0`
- `0x1800204f6`
- `0x18002dde4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e46d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e46d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e487`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e487`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001e428`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001e428`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001e452`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001e452`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001e3fd`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001e509`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001e3fd`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001e509`

## string_xrefs

- `0x18001e44b`: `AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x.`

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
0x18001e3bc  mov     [rsp+arg_0], rbx
0x18001e3c1  push    rdi
0x18001e3c2  sub     rsp, 280h
0x18001e3c9  mov     rax, cs:__security_cookie
0x18001e3d0  xor     rax, rsp
0x18001e3d3  mov     [rsp+288h+var_18], rax
0x18001e3db  mov     ebx, 208h
0x18001e3e0  lea     rcx, [rsp+288h+var_228]; void *
0x18001e3e5  mov     r8d, ebx; Size
0x18001e3e8  xor     edx, edx; Val
0x18001e3ea  call    memset_0
0x18001e3ef  lea     rdx, aWjregisterclou; "WJRegisterCloudDomainJoinRunRecoveryMon"...
0x18001e3f6  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001e3fd  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001e404  nop     dword ptr [rax+rax+00h]
0x18001e409  mov     r9d, ebx
0x18001e40c  mov     [rsp+288h+var_268], 0
0x18001e415  lea     r8, [rsp+288h+var_228]
0x18001e41a  lea     rdx, g_szAADCloudAPPluginParamsKey; "Software\\Microsoft\\IdentityStore\\Loa"...
0x18001e421  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001e428  call    cs:__imp_GetPersistedRegistryLocationW
0x18001e42f  nop     dword ptr [rax+rax+00h]
0x18001e434  mov     ebx, eax
0x18001e436  test    eax, eax
0x18001e438  jz      short loc_18001E463
0x18001e43a  mov     r9d, eax
0x18001e43d  lea     r8, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001e444  lea     rdx, aWjregisterclou; "WJRegisterCloudDomainJoinRunRecoveryMon"...
0x18001e44b  lea     rcx, aAutojoinsvcSGe; "AutoJoinSvc/%s: GetPersistedRegistryLoc"...
0x18001e452  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001e459  nop     dword ptr [rax+rax+00h]
0x18001e45e  jmp     loc_18001E4E7
0x18001e463  lea     rdi, g_RecoveryCriticalSection
0x18001e46a  mov     rcx, rdi; lpCriticalSection
0x18001e46d  call    cs:__imp_InitializeCriticalSection
0x18001e474  nop     dword ptr [rax+rax+00h]
0x18001e479  mov     ebx, 1
0x18001e47e  mov     rcx, rdi; lpCriticalSection
0x18001e481  mov     cs:g_fRecoveryCriticalSectionInitialized, ebx
0x18001e487  call    cs:__imp_EnterCriticalSection
0x18001e48e  nop     dword ptr [rax+rax+00h]
0x18001e493  lea     rax, g_RecoveryNotification
0x18001e49a  mov     [rsp+288h+var_230], rax
0x18001e49f  lea     r8, [rsp+288h+var_228]
0x18001e4a4  lea     rax, WJComputeCloudDomainJoinRecoveryTaskState
0x18001e4ab  mov     [rsp+288h+var_238], rax
0x18001e4b0  lea     rax, aRecovery; "Recovery"
0x18001e4b7  mov     [rsp+288h+var_240], rdi
0x18001e4bc  mov     [rsp+288h+var_248], rax
0x18001e4c1  lea     rax, g_szRecoveryCheckTaskName; "Recovery-Check"
0x18001e4c8  mov     [rsp+288h+var_250], rax
0x18001e4cd  mov     [rsp+288h+var_260], ebx
0x18001e4d1  call    WJRegisterKeyNotification
0x18001e4d6  mov     rcx, rdi; lpCriticalSection
0x18001e4d9  mov     ebx, eax
0x18001e4db  call    cs:__imp_LeaveCriticalSection
0x18001e4e2  nop     dword ptr [rax+rax+00h]
0x18001e4e7  test    ebx, ebx
0x18001e4e9  jg      short loc_18001E4F0
0x18001e4eb  mov     r8d, ebx
0x18001e4ee  jmp     short loc_18001E4FB
0x18001e4f0  movzx   r8d, bx
0x18001e4f4  or      r8d, 80070000h
0x18001e4fb  lea     rdx, aWjregisterclou; "WJRegisterCloudDomainJoinRunRecoveryMon"...
0x18001e502  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001e509  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001e510  nop     dword ptr [rax+rax+00h]
0x18001e515  mov     eax, ebx
0x18001e517  mov     rcx, [rsp+288h+var_18]
0x18001e51f  xor     rcx, rsp; StackCookie
0x18001e522  call    __security_check_cookie
0x18001e527  mov     rbx, [rsp+288h+arg_0]
0x18001e52f  add     rsp, 280h
0x18001e536  pop     rdi
0x18001e537  retn
```
