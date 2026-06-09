# WJComputeCloudDomainJoinRecoveryTaskState

- ea: `0x18001f3f0`
- end: `0x18001f63b`
- name: `WJComputeCloudDomainJoinRecoveryTaskState`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001f3f0`
- `0x18001fbd0`
- `0x1800204f6`
- `0x18002d9dc`
- `0x18002e16c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f515`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f515`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001f463`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001f463`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001f49e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001f49e`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f4cf`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f547`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f594`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f5f7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f4cf`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f547`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f594`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f5f7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f44b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f610`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f44b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f610`

## string_xrefs

- `0x18001f4c8`: `AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x\n`
- `0x18001f43a`: `WJComputeCloudDomainJoinRecoveryTaskState`
- `0x18001f540`: `AutoJoinSvc/%s: Failed to read AAD CloudAP plugin registry value "%s\%s@%s" with status 0x%08x.`
- `0x18001f58d`: `AutoJoinSvc/%s: AAD CloudAP plugin registry value ("%s\%s@%s"): 0x%08x.\n`
- `0x18001f5f0`: `AutoJoinSvc/%s: Failed to compute recovery task ("%s\%s") state with status 0x%08x.`

## pseudocode

```c
__int64 WJComputeCloudDomainJoinRecoveryTaskState()
{
  int PersistedRegistryLocationW; // eax
  unsigned int v1; // ebx
  LSTATUS ValueW; // eax
  int v3; // eax
  unsigned __int16 v4; // ax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  pcbData[0] = 4;
  memset_0(SubKey, 0, 0x208u);
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJComputeCloudDomainJoinRecoveryTaskState");
  if ( qword_1800513B0 && !IsThreadpoolTimerSet(qword_1800513B0) )
    WJCloseSetTaskStateRetryTimer(g_RecoveryCheckTaskRetryState);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreLoadParametersAad",
                                 g_szAADCloudAPPluginParamsKey,
                                 SubKey,
                                 520,
                                 0);
  v1 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v1 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x\n",
      L"WJComputeCloudDomainJoinRecoveryTaskState",
      L"IDStoreLoadParametersAad",
      v1);
    goto LABEL_17;
  }
  v1 = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, g_szAADRunRecoveryValue, 0x10u, 0, &v8, pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    LODWORD(pvData) = ValueW;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to read AAD CloudAP plugin registry value \"%s\\%s@%s\" with status 0x%08x.",
      L"WJComputeCloudDomainJoinRecoveryTaskState",
      L"HKEY_LOCAL_MACHINE",
      SubKey,
      g_szAADRunRecoveryValue,
      pvData);
    v3 = -1;
    v8 = -1;
  }
  else
  {
    v3 = v8;
  }
  if ( v3 != -1 && dword_180050A50 != v3 )
  {
    LODWORD(pvData) = v3;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: AAD CloudAP plugin registry value (\"%s\\%s@%s\"): 0x%08x.\n",
      L"WJComputeCloudDomainJoinRecoveryTaskState",
      L"HKEY_LOCAL_MACHINE",
      SubKey,
      g_szAADRunRecoveryValue,
      pvData);
    if ( v8 )
      v4 = -1;
    else
      v4 = 0;
    v1 = WJSetScheduledTaskState(g_szTaskFolder, g_szRecoveryCheckTaskName, v4, g_RecoveryCheckTaskRetryState);
    dword_180050A50 = v8;
LABEL_17:
    if ( (v1 & 0x80000000) != 0 )
    {
      LODWORD(pdwType) = v1;
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to compute recovery task (\"%s\\%s\") state with status 0x%08x.",
        L"WJComputeCloudDomainJoinRecoveryTaskState",
        g_szTaskFolder,
        g_szRecoveryCheckTaskName,
        pdwType);
    }
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - hr: 0x%08x",
    L"WJComputeCloudDomainJoinRecoveryTaskState",
    v1);
  return v1;
}

```

## disassembly

```asm
0x18001f3f0  push    rbp
0x18001f3f2  push    rbx
0x18001f3f3  push    rsi
0x18001f3f4  push    r15
0x18001f3f6  lea     rbp, [rsp-178h]
0x18001f3fe  sub     rsp, 278h
0x18001f405  mov     rax, cs:__security_cookie
0x18001f40c  xor     rax, rsp
0x18001f40f  mov     [rbp+190h+var_30], rax
0x18001f416  mov     ebx, 208h
0x18001f41b  mov     [rsp+290h+var_250], 0
0x18001f423  mov     r8d, ebx; Size
0x18001f426  mov     [rsp+290h+var_24C], 4
0x18001f42e  xor     edx, edx; Val
0x18001f430  lea     rcx, [rsp+290h+SubKey]; void *
0x18001f435  call    memset_0
0x18001f43a  lea     rsi, aWjcomputecloud; "WJComputeCloudDomainJoinRecoveryTaskSta"...
0x18001f441  mov     rdx, rsi
0x18001f444  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001f44b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f452  nop     dword ptr [rax+rax+00h]
0x18001f457  mov     rcx, cs:qword_1800513B0; pti
0x18001f45e  test    rcx, rcx
0x18001f461  jz      short loc_18001F47F
0x18001f463  call    cs:__imp_IsThreadpoolTimerSet
0x18001f46a  nop     dword ptr [rax+rax+00h]
0x18001f46f  test    eax, eax
0x18001f471  jnz     short loc_18001F47F
0x18001f473  lea     rcx, g_RecoveryCheckTaskRetryState
0x18001f47a  call    WJCloseSetTaskStateRetryTimer
0x18001f47f  mov     r9d, ebx
0x18001f482  mov     [rsp+290h+pdwType], 0
0x18001f48b  lea     r8, [rsp+290h+SubKey]
0x18001f490  lea     rdx, g_szAADCloudAPPluginParamsKey; "Software\\Microsoft\\IdentityStore\\Loa"...
0x18001f497  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001f49e  call    cs:__imp_GetPersistedRegistryLocationW
0x18001f4a5  nop     dword ptr [rax+rax+00h]
0x18001f4aa  mov     ebx, eax
0x18001f4ac  test    eax, eax
0x18001f4ae  jz      short loc_18001F4E0
0x18001f4b0  jle     short loc_18001F4BB
0x18001f4b2  movzx   ebx, ax
0x18001f4b5  or      ebx, 80070000h
0x18001f4bb  mov     r9d, ebx
0x18001f4be  lea     r8, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001f4c5  mov     rdx, rsi
0x18001f4c8  lea     rcx, aAutojoinsvcSGe_0; "AutoJoinSvc/%s: GetPersistedRegistryLoc"...
0x18001f4cf  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001f4d6  nop     dword ptr [rax+rax+00h]
0x18001f4db  jmp     loc_18001F5D7
0x18001f4e0  xor     ebx, ebx
0x18001f4e2  lea     rax, [rsp+290h+var_24C]
0x18001f4e7  mov     [rsp+290h+pcbData], rax; pcbData
0x18001f4ec  lea     r15, g_szAADRunRecoveryValue; "RunRecovery"
0x18001f4f3  lea     rax, [rsp+290h+var_250]
0x18001f4f8  mov     r8, r15; lpValue
0x18001f4fb  mov     [rsp+290h+pvData], rax; pvData
0x18001f500  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18001f505  lea     r9d, [rbx+10h]; dwFlags
0x18001f509  mov     [rsp+290h+pdwType], rbx; pdwType
0x18001f50e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f515  call    cs:__imp_RegGetValueW
0x18001f51c  nop     dword ptr [rax+rax+00h]
0x18001f521  test    eax, 0FFFFFFFDh
0x18001f526  jz      short loc_18001F55C
0x18001f528  mov     dword ptr [rsp+290h+pvData], eax
0x18001f52c  lea     r9, [rsp+290h+SubKey]
0x18001f531  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001f538  mov     [rsp+290h+pdwType], r15
0x18001f53d  mov     rdx, rsi
0x18001f540  lea     rcx, aAutojoinsvcSFa_3; "AutoJoinSvc/%s: Failed to read AAD Clou"...
0x18001f547  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001f54e  nop     dword ptr [rax+rax+00h]
0x18001f553  or      eax, 0FFFFFFFFh
0x18001f556  mov     [rsp+290h+var_250], eax
0x18001f55a  jmp     short loc_18001F560
0x18001f55c  mov     eax, [rsp+290h+var_250]
0x18001f560  cmp     eax, 0FFFFFFFFh
0x18001f563  jz      loc_18001F603
0x18001f569  cmp     cs:dword_180050A50, eax
0x18001f56f  jz      loc_18001F603
0x18001f575  mov     dword ptr [rsp+290h+pvData], eax
0x18001f579  lea     r9, [rsp+290h+SubKey]
0x18001f57e  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001f585  mov     [rsp+290h+pdwType], r15
0x18001f58a  mov     rdx, rsi
0x18001f58d  lea     rcx, aAutojoinsvcSAa; "AutoJoinSvc/%s: AAD CloudAP plugin regi"...
0x18001f594  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001f59b  nop     dword ptr [rax+rax+00h]
0x18001f5a0  cmp     [rsp+290h+var_250], ebx
0x18001f5a4  jz      short loc_18001F5AB
0x18001f5a6  or      eax, 0FFFFFFFFh
0x18001f5a9  jmp     short loc_18001F5AD
0x18001f5ab  xor     eax, eax
0x18001f5ad  lea     r9, g_RecoveryCheckTaskRetryState
0x18001f5b4  movzx   r8d, ax
0x18001f5b8  lea     rdx, g_szRecoveryCheckTaskName; "Recovery-Check"
0x18001f5bf  lea     rcx, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001f5c6  call    WJSetScheduledTaskState
0x18001f5cb  mov     ecx, [rsp+290h+var_250]
0x18001f5cf  mov     ebx, eax
0x18001f5d1  mov     cs:dword_180050A50, ecx
0x18001f5d7  test    ebx, ebx
0x18001f5d9  jns     short loc_18001F603
0x18001f5db  lea     r9, g_szRecoveryCheckTaskName; "Recovery-Check"
0x18001f5e2  mov     dword ptr [rsp+290h+pdwType], ebx
0x18001f5e6  lea     r8, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001f5ed  mov     rdx, rsi
0x18001f5f0  lea     rcx, aAutojoinsvcSFa_6; "AutoJoinSvc/%s: Failed to compute recov"...
0x18001f5f7  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001f5fe  nop     dword ptr [rax+rax+00h]
0x18001f603  mov     r8d, ebx
0x18001f606  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001f60d  mov     rdx, rsi
0x18001f610  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f617  nop     dword ptr [rax+rax+00h]
0x18001f61c  mov     eax, ebx
0x18001f61e  mov     rcx, [rbp+190h+var_30]
0x18001f625  xor     rcx, rsp; StackCookie
0x18001f628  call    __security_check_cookie
0x18001f62d  add     rsp, 278h
0x18001f634  pop     r15
0x18001f636  pop     rsi
0x18001f637  pop     rbx
0x18001f638  pop     rbp
0x18001f639  retn
```
