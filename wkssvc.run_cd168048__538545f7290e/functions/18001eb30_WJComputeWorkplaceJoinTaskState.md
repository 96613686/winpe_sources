# WJComputeWorkplaceJoinTaskState

- ea: `0x18001eb30`
- end: `0x18001ef04`
- name: `WJComputeWorkplaceJoinTaskState`
- size: `980`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001eb30`
- `0x18002d908`
- `0x18002d974`
- `0x18002d9dc`
- `0x18002dc00`
- `0x18002e16c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ec72`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ecf4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ec72`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ecf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebea`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001eb7e`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001eba6`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001eb7e`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001eba6`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ec05`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ecae`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001edb2`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ee27`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ee6b`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001eec8`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ec05`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ecae`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001edb2`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ee27`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ee6b`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001eec8`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001eb66`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ebc5`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ec31`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ed25`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ed6e`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ee45`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ee94`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001eee1`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001eb66`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ebc5`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ec31`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ed25`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ed6e`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ee45`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ee94`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001eee1`
- `dsreg!DsrIsDeviceJoined` at `0x18001ee08`
- `dsreg!DsrIsDeviceJoined` at `0x18001ee08`
- `USERENV!EnterCriticalPolicySection` at `0x18001ebd6`
- `USERENV!EnterCriticalPolicySection` at `0x18001ebd6`

## string_xrefs

- `0x18001ec97`: `AutoJoinSvc/%s: Failed to read AutoWorkplaceJoin registry value for global policy ("%s\%s@%s") with status 0x%08x.`
- `0x18001ee61`: `AutoJoinSvc/%s: Failed to create thread-pool timer to write the auto join trigger event. Status 0x%08x.`
- `0x18001ed15`: `AutoJoinSvc/%s: Failed to read AutoWorkplaceJoin registry value for local policy ("%s\%s@%s") with status 0x%08x.`
- `0x18001eb4d`: `WJComputeWorkplaceJoinTaskState`
- `0x18001ee3e`: `AutoJoinSvc/%s: Machine is already joined to Microsoft Entra.`
- `0x18001eec1`: `AutoJoinSvc/%s: Failed to determine status of automatic join task "%s\%s" with status 0x%08x.`

## pseudocode

```c
__int64 WJComputeWorkplaceJoinTaskState()
{
  HANDLE v0; // rsi
  __int64 LastError; // rbx
  LSTATUS ValueW; // eax
  WCHAR *v3; // r9
  const wchar_t *v4; // rcx
  LSTATUS v5; // eax
  WCHAR *v6; // r9
  const wchar_t *v7; // rcx
  unsigned __int16 v8; // di
  int IsDeviceJoined; // eax
  unsigned int v10; // eax
  int v11; // edi
  LPDWORD pdwType; // [rsp+20h] [rbp-20h]
  PVOID pvData; // [rsp+28h] [rbp-18h]
  unsigned int v15; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF
  int v17; // [rsp+80h] [rbp+40h] BYREF

  pcbData = 4;
  v15 = 0;
  v17 = 0;
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJComputeWorkplaceJoinTaskState");
  if ( pti && !IsThreadpoolTimerSet(pti) )
    WJCloseSetTaskStateRetryTimer(g_AutoJoinTaskRetryState);
  if ( g_AutoJoinTriggerEventTimer && !IsThreadpoolTimerSet(g_AutoJoinTriggerEventTimer) )
    WJCloseAutoJoinTriggerEventTimer();
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Trying to lock machine group policy...",
    L"WJComputeWorkplaceJoinTaskState");
  v0 = EnterCriticalPolicySection(1);
  if ( !v0 )
  {
    LastError = GetLastError();
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to lock machine group policy with error 0x%08x.",
      L"WJComputeWorkplaceJoinTaskState",
      LastError);
LABEL_9:
    if ( (int)LastError <= 0 )
      goto LABEL_40;
    LODWORD(LastError) = (unsigned __int16)LastError;
    goto LABEL_11;
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Machine group policy successfully locked",
    L"WJComputeWorkplaceJoinTaskState");
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             g_szGlobalWorkplaceJoinKey,
             g_szAutoWorkplaceJoinValue,
             0x10u,
             0,
             &v15,
             &pcbData);
  LODWORD(LastError) = ValueW;
  if ( !ValueW )
  {
    v6 = g_szGlobalWorkplaceJoinKey;
    v7 = L"AutoJoinSvc/%s: Global policy (\"%s\\%s@%s\") found with value %d.";
    goto LABEL_22;
  }
  if ( ValueW != 2 )
  {
    v3 = g_szGlobalWorkplaceJoinKey;
    v4 = L"AutoJoinSvc/%s: Failed to read AutoWorkplaceJoin registry value for global policy (\"%s\\%s@%s\") with status 0x%08x.";
LABEL_15:
    LODWORD(pvData) = LastError;
    DsrWriteAutoJoinSvcAdminEvent(
      v4,
      L"WJComputeWorkplaceJoinTaskState",
      L"HKEY_LOCAL_MACHINE",
      v3,
      g_szAutoWorkplaceJoinValue,
      pvData);
    goto LABEL_9;
  }
  pcbData = 4;
  v5 = RegGetValueW(HKEY_LOCAL_MACHINE, g_szLocalWorkplaceJoinKey, g_szAutoWorkplaceJoinValue, 0x10u, 0, &v15, &pcbData);
  LODWORD(LastError) = v5;
  if ( !v5 )
  {
    v6 = g_szLocalWorkplaceJoinKey;
    v7 = L"AutoJoinSvc/%s: Local policy (\"%s\\%s@%s\") found with value %d.";
LABEL_22:
    LODWORD(pvData) = v15;
    DsrWriteAutoJoinSvcDebugEvent(
      v7,
      L"WJComputeWorkplaceJoinTaskState",
      L"HKEY_LOCAL_MACHINE",
      v6,
      g_szAutoWorkplaceJoinValue,
      pvData);
    goto LABEL_23;
  }
  if ( v5 != 2 )
  {
    v3 = g_szLocalWorkplaceJoinKey;
    v4 = L"AutoJoinSvc/%s: Failed to read AutoWorkplaceJoin registry value for local policy (\"%s\\%s@%s\") with status 0x%08x.";
    goto LABEL_15;
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Global and Local policies are not present.",
    L"WJComputeWorkplaceJoinTaskState");
  v15 = 1;
LABEL_23:
  LeaveMachineCriticalPolicySection(v0);
  v0 = 0;
  if ( dword_18005094C == 2105040038 )
  {
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Auto join policy value is %d.",
      L"WJComputeWorkplaceJoinTaskState",
      v15);
  }
  else
  {
    if ( dword_18005094C == v15 )
    {
      LODWORD(LastError) = 0;
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Auto join policy remains unchanged. Value %d.",
        L"WJComputeWorkplaceJoinTaskState");
      goto LABEL_40;
    }
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Auto join policy changed to value %d.",
      L"WJComputeWorkplaceJoinTaskState",
      v15);
  }
  dword_18005094C = v15;
  if ( v15 == 1 )
    v8 = -1;
  else
    v8 = 0;
  WJCloseAutoJoinTriggerEventTimer();
  LODWORD(LastError) = WJSetScheduledTaskState(
                         g_szTaskFolder,
                         g_szAutomaticDeviceJoinTaskName,
                         v8,
                         g_AutoJoinTaskRetryState);
  if ( !v8 )
    goto LABEL_40;
  IsDeviceJoined = DsrIsDeviceJoined(&v17, 0);
  LODWORD(LastError) = IsDeviceJoined;
  if ( IsDeviceJoined >= 0 )
  {
    if ( v17 )
    {
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Machine is already joined to Microsoft Entra.",
        L"WJComputeWorkplaceJoinTaskState");
    }
    else
    {
      v10 = WJOpenAutoJoinTriggerEventTimer();
      v11 = v10;
      if ( v10 )
      {
        DsrWriteAutoJoinSvcAdminEvent(
          L"AutoJoinSvc/%s: Failed to create thread-pool timer to write the auto join trigger event. Status 0x%08x.",
          L"WJComputeWorkplaceJoinTaskState",
          v10);
        if ( v11 > 0 )
        {
          LODWORD(LastError) = (unsigned __int16)v11;
LABEL_11:
          LODWORD(LastError) = LastError | 0x80070000;
          goto LABEL_40;
        }
        LODWORD(LastError) = v11;
      }
    }
  }
  else
  {
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to determine if machine is Microsoft Entra joined. Status 0x%08x.",
      L"WJComputeWorkplaceJoinTaskState",
      (unsigned int)IsDeviceJoined);
  }
LABEL_40:
  LeaveMachineCriticalPolicySection(v0);
  if ( (int)LastError < 0 )
  {
    LODWORD(pdwType) = LastError;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to determine status of automatic join task \"%s\\%s\" with status 0x%08x.",
      L"WJComputeWorkplaceJoinTaskState",
      g_szTaskFolder,
      g_szAutomaticDeviceJoinTaskName,
      pdwType);
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - hr: 0x%08x",
    L"WJComputeWorkplaceJoinTaskState",
    (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001eb30  mov     [rsp-28h+arg_18], rbx
0x18001eb35  push    rbp
0x18001eb36  push    rsi
0x18001eb37  push    rdi
0x18001eb38  push    r14
0x18001eb3a  push    r15
0x18001eb3c  mov     rbp, rsp
0x18001eb3f  sub     rsp, 40h
0x18001eb43  xor     r14d, r14d
0x18001eb46  mov     [rbp+arg_8], 4
0x18001eb4d  lea     r15, aWjcomputeworkp; "WJComputeWorkplaceJoinTaskState"
0x18001eb54  mov     [rbp+arg_0], r14d
0x18001eb58  mov     rdx, r15
0x18001eb5b  mov     [rbp+arg_10], r14d
0x18001eb5f  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001eb66  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001eb6d  nop     dword ptr [rax+rax+00h]
0x18001eb72  mov     rcx, cs:pti; pti
0x18001eb79  test    rcx, rcx
0x18001eb7c  jz      short loc_18001EB9A
0x18001eb7e  call    cs:__imp_IsThreadpoolTimerSet
0x18001eb85  nop     dword ptr [rax+rax+00h]
0x18001eb8a  test    eax, eax
0x18001eb8c  jnz     short loc_18001EB9A
0x18001eb8e  lea     rcx, g_AutoJoinTaskRetryState
0x18001eb95  call    WJCloseSetTaskStateRetryTimer
0x18001eb9a  mov     rcx, cs:g_AutoJoinTriggerEventTimer; pti
0x18001eba1  test    rcx, rcx
0x18001eba4  jz      short loc_18001EBBB
0x18001eba6  call    cs:__imp_IsThreadpoolTimerSet
0x18001ebad  nop     dword ptr [rax+rax+00h]
0x18001ebb2  test    eax, eax
0x18001ebb4  jnz     short loc_18001EBBB
0x18001ebb6  call    WJCloseAutoJoinTriggerEventTimer
0x18001ebbb  mov     rdx, r15
0x18001ebbe  lea     rcx, aAutojoinsvcSTr; "AutoJoinSvc/%s: Trying to lock machine "...
0x18001ebc5  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ebcc  nop     dword ptr [rax+rax+00h]
0x18001ebd1  mov     ecx, 1; bMachine
0x18001ebd6  call    cs:__imp_EnterCriticalPolicySection
0x18001ebdd  nop     dword ptr [rax+rax+00h]
0x18001ebe2  mov     rsi, rax
0x18001ebe5  test    rax, rax
0x18001ebe8  jnz     short loc_18001EC27
0x18001ebea  call    cs:__imp_GetLastError
0x18001ebf1  nop     dword ptr [rax+rax+00h]
0x18001ebf6  mov     rdx, r15
0x18001ebf9  lea     rcx, aAutojoinsvcSFa_10; "AutoJoinSvc/%s: Failed to lock machine "...
0x18001ec00  mov     r8d, eax
0x18001ec03  mov     ebx, eax
0x18001ec05  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ec0c  nop     dword ptr [rax+rax+00h]
0x18001ec11  test    ebx, ebx
0x18001ec13  jle     loc_18001EEA0
0x18001ec19  movzx   ebx, bx
0x18001ec1c  or      ebx, 80070000h
0x18001ec22  jmp     loc_18001EEA0
0x18001ec27  mov     rdx, r15
0x18001ec2a  lea     rcx, aAutojoinsvcSMa_0; "AutoJoinSvc/%s: Machine group policy su"...
0x18001ec31  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ec38  nop     dword ptr [rax+rax+00h]
0x18001ec3d  lea     rax, [rbp+arg_8]
0x18001ec41  mov     r9d, 10h; dwFlags
0x18001ec47  mov     [rsp+40h+pcbData], rax; pcbData
0x18001ec4c  lea     rdi, g_szAutoWorkplaceJoinValue; "autoWorkplaceJoin"
0x18001ec53  lea     rax, [rbp+arg_0]
0x18001ec57  mov     r8, rdi; lpValue
0x18001ec5a  mov     [rsp+40h+pvData], rax; pvData
0x18001ec5f  lea     rdx, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001ec66  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ec6d  mov     [rsp+40h+pdwType], r14; pdwType
0x18001ec72  call    cs:__imp_RegGetValueW
0x18001ec79  nop     dword ptr [rax+rax+00h]
0x18001ec7e  mov     ebx, eax
0x18001ec80  test    eax, eax
0x18001ec82  jz      loc_18001ED4A
0x18001ec88  cmp     eax, 2
0x18001ec8b  jz      short loc_18001ECBF
0x18001ec8d  lea     r9, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001ec94  mov     rdx, r15
0x18001ec97  lea     rcx, aAutojoinsvcSFa_15; "AutoJoinSvc/%s: Failed to read AutoWork"...
0x18001ec9e  mov     dword ptr [rsp+40h+pvData], ebx
0x18001eca2  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001eca9  mov     [rsp+40h+pdwType], rdi
0x18001ecae  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ecb5  nop     dword ptr [rax+rax+00h]
0x18001ecba  jmp     loc_18001EC11
0x18001ecbf  lea     rax, [rbp+arg_8]
0x18001ecc3  mov     [rbp+arg_8], 4
0x18001ecca  mov     [rsp+40h+pcbData], rax; pcbData
0x18001eccf  lea     rdx, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001ecd6  lea     rax, [rbp+arg_0]
0x18001ecda  mov     r9d, 10h; dwFlags
0x18001ece0  mov     [rsp+40h+pvData], rax; pvData
0x18001ece5  mov     r8, rdi; lpValue
0x18001ece8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ecef  mov     [rsp+40h+pdwType], r14; pdwType
0x18001ecf4  call    cs:__imp_RegGetValueW
0x18001ecfb  nop     dword ptr [rax+rax+00h]
0x18001ed00  mov     ebx, eax
0x18001ed02  test    eax, eax
0x18001ed04  jz      short loc_18001ED3A
0x18001ed06  mov     rdx, r15
0x18001ed09  cmp     eax, 2
0x18001ed0c  jz      short loc_18001ED1E
0x18001ed0e  lea     r9, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001ed15  lea     rcx, aAutojoinsvcSFa_8; "AutoJoinSvc/%s: Failed to read AutoWork"...
0x18001ed1c  jmp     short loc_18001EC9E
0x18001ed1e  lea     rcx, aAutojoinsvcSGl_0; "AutoJoinSvc/%s: Global and Local polici"...
0x18001ed25  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ed2c  nop     dword ptr [rax+rax+00h]
0x18001ed31  mov     [rbp+arg_0], 1
0x18001ed38  jmp     short loc_18001ED7A
0x18001ed3a  lea     r9, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001ed41  lea     rcx, aAutojoinsvcSLo; "AutoJoinSvc/%s: Local policy (\"%s\\%s@"...
0x18001ed48  jmp     short loc_18001ED58
0x18001ed4a  lea     r9, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001ed51  lea     rcx, aAutojoinsvcSGl; "AutoJoinSvc/%s: Global policy (\"%s\\%s"...
0x18001ed58  mov     eax, [rbp+arg_0]
0x18001ed5b  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001ed62  mov     dword ptr [rsp+40h+pvData], eax
0x18001ed66  mov     rdx, r15
0x18001ed69  mov     [rsp+40h+pdwType], rdi
0x18001ed6e  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ed75  nop     dword ptr [rax+rax+00h]
0x18001ed7a  mov     rcx, rsi
0x18001ed7d  call    LeaveMachineCriticalPolicySection
0x18001ed82  mov     eax, cs:dword_18005094C
0x18001ed88  mov     rsi, r14
0x18001ed8b  mov     r8d, [rbp+arg_0]
0x18001ed8f  cmp     eax, 7D785CA6h
0x18001ed94  jnz     short loc_18001ED9F
0x18001ed96  lea     rcx, aAutojoinsvcSAu_1; "AutoJoinSvc/%s: Auto join policy value "...
0x18001ed9d  jmp     short loc_18001EDAF
0x18001ed9f  cmp     eax, r8d
0x18001eda2  jz      loc_18001EE87
0x18001eda8  lea     rcx, aAutojoinsvcSAu; "AutoJoinSvc/%s: Auto join policy change"...
0x18001edaf  mov     rdx, r15
0x18001edb2  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001edb9  nop     dword ptr [rax+rax+00h]
0x18001edbe  mov     eax, [rbp+arg_0]
0x18001edc1  mov     cs:dword_18005094C, eax
0x18001edc7  cmp     eax, 1
0x18001edca  jnz     short loc_18001EDD1
0x18001edcc  or      edi, 0FFFFFFFFh
0x18001edcf  jmp     short loc_18001EDD4
0x18001edd1  mov     edi, r14d
0x18001edd4  call    WJCloseAutoJoinTriggerEventTimer
0x18001edd9  lea     r9, g_AutoJoinTaskRetryState
0x18001ede0  movzx   r8d, di
0x18001ede4  lea     rdx, g_szAutomaticDeviceJoinTaskName; "Automatic-Device-Join"
0x18001edeb  lea     rcx, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001edf2  call    WJSetScheduledTaskState
0x18001edf7  mov     ebx, eax
0x18001edf9  test    di, di
0x18001edfc  jz      loc_18001EEA0
0x18001ee02  xor     edx, edx
0x18001ee04  lea     rcx, [rbp+arg_10]
0x18001ee08  call    cs:__imp_DsrIsDeviceJoined
0x18001ee0f  nop     dword ptr [rax+rax+00h]
0x18001ee14  mov     ebx, eax
0x18001ee16  test    eax, eax
0x18001ee18  jns     short loc_18001EE35
0x18001ee1a  mov     r8d, eax
0x18001ee1d  lea     rcx, aAutojoinsvcSFa_11; "AutoJoinSvc/%s: Failed to determine if "...
0x18001ee24  mov     rdx, r15
0x18001ee27  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ee2e  nop     dword ptr [rax+rax+00h]
0x18001ee33  jmp     short loc_18001EEA0
0x18001ee35  cmp     [rbp+arg_10], r14d
0x18001ee39  jz      short loc_18001EE53
0x18001ee3b  mov     rdx, r15
0x18001ee3e  lea     rcx, aAutojoinsvcSMa; "AutoJoinSvc/%s: Machine is already join"...
0x18001ee45  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ee4c  nop     dword ptr [rax+rax+00h]
0x18001ee51  jmp     short loc_18001EEA0
0x18001ee53  call    WJOpenAutoJoinTriggerEventTimer
0x18001ee58  mov     edi, eax
0x18001ee5a  test    eax, eax
0x18001ee5c  jz      short loc_18001EEA0
0x18001ee5e  mov     r8d, eax
0x18001ee61  lea     rcx, aAutojoinsvcSFa_16; "AutoJoinSvc/%s: Failed to create thread"...
0x18001ee68  mov     rdx, r15
0x18001ee6b  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ee72  nop     dword ptr [rax+rax+00h]
0x18001ee77  test    edi, edi
0x18001ee79  jg      short loc_18001EE7F
0x18001ee7b  mov     ebx, edi
0x18001ee7d  jmp     short loc_18001EEA0
0x18001ee7f  movzx   ebx, di
0x18001ee82  jmp     loc_18001EC1C
0x18001ee87  mov     rdx, r15
0x18001ee8a  lea     rcx, aAutojoinsvcSAu_0; "AutoJoinSvc/%s: Auto join policy remain"...
0x18001ee91  mov     ebx, r14d
0x18001ee94  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ee9b  nop     dword ptr [rax+rax+00h]
0x18001eea0  mov     rcx, rsi
0x18001eea3  call    LeaveMachineCriticalPolicySection
0x18001eea8  test    ebx, ebx
0x18001eeaa  jns     short loc_18001EED4
0x18001eeac  lea     r9, g_szAutomaticDeviceJoinTaskName; "Automatic-Device-Join"
0x18001eeb3  mov     dword ptr [rsp+40h+pdwType], ebx
0x18001eeb7  lea     r8, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001eebe  mov     rdx, r15
0x18001eec1  lea     rcx, aAutojoinsvcSFa_22; "AutoJoinSvc/%s: Failed to determine sta"...
0x18001eec8  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001eecf  nop     dword ptr [rax+rax+00h]
0x18001eed4  mov     r8d, ebx
0x18001eed7  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001eede  mov     rdx, r15
0x18001eee1  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001eee8  nop     dword ptr [rax+rax+00h]
0x18001eeed  mov     eax, ebx
0x18001eeef  mov     rbx, [rsp+40h+arg_18]
0x18001eef7  add     rsp, 40h
0x18001eefb  pop     r15
0x18001eefd  pop     r14
0x18001eeff  pop     rdi
0x18001ef00  pop     rsi
0x18001ef01  pop     rbp
0x18001ef02  retn
```
