# WJComputeWorkplaceJoinTaskState

- ea: `0x18001d4c0`
- end: `0x18001d815`
- name: `WJComputeWorkplaceJoinTaskState`
- size: `853`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001d4c0`
- `0x18002b2f0`
- `0x18002b344`
- `0x18002b39c`
- `0x18002b560`
- `0x18002ba14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d5d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d648`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d5d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d55c`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001d508`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001d52a`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001d508`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001d52a`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d571`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d608`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d6f4`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d75d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d795`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d7e6`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d571`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d608`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d6f4`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d75d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d795`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001d7e6`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d4f6`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d543`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d597`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d673`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d6b6`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d775`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d7b8`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d7f9`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d4f6`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d543`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d597`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d673`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d6b6`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d775`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d7b8`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d7f9`
- `dsreg!DsrIsDeviceJoined` at `0x18001d744`
- `dsreg!DsrIsDeviceJoined` at `0x18001d744`
- `USERENV!EnterCriticalPolicySection` at `0x18001d54e`
- `USERENV!EnterCriticalPolicySection` at `0x18001d54e`

## string_xrefs

- `0x18001d5f1`: `AutoJoinSvc/%s: Failed to read AutoWorkplaceJoin registry value for global policy ("%s\%s@%s") with status 0x%08x.`
- `0x18001d78b`: `AutoJoinSvc/%s: Failed to create thread-pool timer to write the auto join trigger event. Status 0x%08x.`
- `0x18001d663`: `AutoJoinSvc/%s: Failed to read AutoWorkplaceJoin registry value for local policy ("%s\%s@%s") with status 0x%08x.`
- `0x18001d4dd`: `WJComputeWorkplaceJoinTaskState`
- `0x18001d76e`: `AutoJoinSvc/%s: Machine is already joined to Microsoft Entra.`
- `0x18001d7df`: `AutoJoinSvc/%s: Failed to determine status of automatic join task "%s\%s" with status 0x%08x.`

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
  __int16 v8; // di
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
  if ( dword_18004D94C == 2105040038 )
  {
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Auto join policy value is %d.",
      L"WJComputeWorkplaceJoinTaskState",
      v15);
  }
  else
  {
    if ( dword_18004D94C == v15 )
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
  dword_18004D94C = v15;
  if ( v15 == 1 )
    v8 = -1;
  else
    v8 = 0;
  WJCloseAutoJoinTriggerEventTimer();
  LODWORD(LastError) = WJSetScheduledTaskState(g_szTaskFolder, g_szAutomaticDeviceJoinTaskName);
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
0x18001d4c0  mov     [rsp-28h+arg_18], rbx
0x18001d4c5  push    rbp
0x18001d4c6  push    rsi
0x18001d4c7  push    rdi
0x18001d4c8  push    r14
0x18001d4ca  push    r15
0x18001d4cc  mov     rbp, rsp
0x18001d4cf  sub     rsp, 40h
0x18001d4d3  xor     r14d, r14d
0x18001d4d6  mov     [rbp+arg_8], 4
0x18001d4dd  lea     r15, aWjcomputeworkp; "WJComputeWorkplaceJoinTaskState"
0x18001d4e4  mov     [rbp+arg_0], r14d
0x18001d4e8  mov     rdx, r15
0x18001d4eb  mov     [rbp+arg_10], r14d
0x18001d4ef  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001d4f6  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d4fc  mov     rcx, cs:pti; pti
0x18001d503  test    rcx, rcx
0x18001d506  jz      short loc_18001D51E
0x18001d508  call    cs:__imp_IsThreadpoolTimerSet
0x18001d50e  test    eax, eax
0x18001d510  jnz     short loc_18001D51E
0x18001d512  lea     rcx, g_AutoJoinTaskRetryState
0x18001d519  call    WJCloseSetTaskStateRetryTimer
0x18001d51e  mov     rcx, cs:g_AutoJoinTriggerEventTimer; pti
0x18001d525  test    rcx, rcx
0x18001d528  jz      short loc_18001D539
0x18001d52a  call    cs:__imp_IsThreadpoolTimerSet
0x18001d530  test    eax, eax
0x18001d532  jnz     short loc_18001D539
0x18001d534  call    WJCloseAutoJoinTriggerEventTimer
0x18001d539  mov     rdx, r15
0x18001d53c  lea     rcx, aAutojoinsvcSTr; "AutoJoinSvc/%s: Trying to lock machine "...
0x18001d543  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d549  mov     ecx, 1; bMachine
0x18001d54e  call    cs:__imp_EnterCriticalPolicySection
0x18001d554  mov     rsi, rax
0x18001d557  test    rax, rax
0x18001d55a  jnz     short loc_18001D58D
0x18001d55c  call    cs:__imp_GetLastError
0x18001d562  mov     rdx, r15
0x18001d565  lea     rcx, aAutojoinsvcSFa_10; "AutoJoinSvc/%s: Failed to lock machine "...
0x18001d56c  mov     r8d, eax
0x18001d56f  mov     ebx, eax
0x18001d571  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001d577  test    ebx, ebx
0x18001d579  jle     loc_18001D7BE
0x18001d57f  movzx   ebx, bx
0x18001d582  or      ebx, 80070000h
0x18001d588  jmp     loc_18001D7BE
0x18001d58d  mov     rdx, r15
0x18001d590  lea     rcx, aAutojoinsvcSMa_0; "AutoJoinSvc/%s: Machine group policy su"...
0x18001d597  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d59d  lea     rax, [rbp+arg_8]
0x18001d5a1  mov     r9d, 10h; dwFlags
0x18001d5a7  mov     [rsp+40h+pcbData], rax; pcbData
0x18001d5ac  lea     rdi, g_szAutoWorkplaceJoinValue; "autoWorkplaceJoin"
0x18001d5b3  lea     rax, [rbp+arg_0]
0x18001d5b7  mov     r8, rdi; lpValue
0x18001d5ba  mov     [rsp+40h+pvData], rax; pvData
0x18001d5bf  lea     rdx, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001d5c6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001d5cd  mov     [rsp+40h+pdwType], r14; pdwType
0x18001d5d2  call    cs:__imp_RegGetValueW
0x18001d5d8  mov     ebx, eax
0x18001d5da  test    eax, eax
0x18001d5dc  jz      loc_18001D692
0x18001d5e2  cmp     eax, 2
0x18001d5e5  jz      short loc_18001D613
0x18001d5e7  lea     r9, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001d5ee  mov     rdx, r15
0x18001d5f1  lea     rcx, aAutojoinsvcSFa_15; "AutoJoinSvc/%s: Failed to read AutoWork"...
0x18001d5f8  mov     dword ptr [rsp+40h+pvData], ebx
0x18001d5fc  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001d603  mov     [rsp+40h+pdwType], rdi
0x18001d608  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001d60e  jmp     loc_18001D577
0x18001d613  lea     rax, [rbp+arg_8]
0x18001d617  mov     [rbp+arg_8], 4
0x18001d61e  mov     [rsp+40h+pcbData], rax; pcbData
0x18001d623  lea     rdx, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001d62a  lea     rax, [rbp+arg_0]
0x18001d62e  mov     r9d, 10h; dwFlags
0x18001d634  mov     [rsp+40h+pvData], rax; pvData
0x18001d639  mov     r8, rdi; lpValue
0x18001d63c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001d643  mov     [rsp+40h+pdwType], r14; pdwType
0x18001d648  call    cs:__imp_RegGetValueW
0x18001d64e  mov     ebx, eax
0x18001d650  test    eax, eax
0x18001d652  jz      short loc_18001D682
0x18001d654  mov     rdx, r15
0x18001d657  cmp     eax, 2
0x18001d65a  jz      short loc_18001D66C
0x18001d65c  lea     r9, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001d663  lea     rcx, aAutojoinsvcSFa_8; "AutoJoinSvc/%s: Failed to read AutoWork"...
0x18001d66a  jmp     short loc_18001D5F8
0x18001d66c  lea     rcx, aAutojoinsvcSGl_0; "AutoJoinSvc/%s: Global and Local polici"...
0x18001d673  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d679  mov     [rbp+arg_0], 1
0x18001d680  jmp     short loc_18001D6BC
0x18001d682  lea     r9, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001d689  lea     rcx, aAutojoinsvcSLo; "AutoJoinSvc/%s: Local policy (\"%s\\%s@"...
0x18001d690  jmp     short loc_18001D6A0
0x18001d692  lea     r9, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001d699  lea     rcx, aAutojoinsvcSGl; "AutoJoinSvc/%s: Global policy (\"%s\\%s"...
0x18001d6a0  mov     eax, [rbp+arg_0]
0x18001d6a3  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001d6aa  mov     dword ptr [rsp+40h+pvData], eax
0x18001d6ae  mov     rdx, r15
0x18001d6b1  mov     [rsp+40h+pdwType], rdi
0x18001d6b6  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d6bc  mov     rcx, rsi
0x18001d6bf  call    LeaveMachineCriticalPolicySection
0x18001d6c4  mov     eax, cs:dword_18004D94C
0x18001d6ca  mov     rsi, r14
0x18001d6cd  mov     r8d, [rbp+arg_0]
0x18001d6d1  cmp     eax, 7D785CA6h
0x18001d6d6  jnz     short loc_18001D6E1
0x18001d6d8  lea     rcx, aAutojoinsvcSAu_1; "AutoJoinSvc/%s: Auto join policy value "...
0x18001d6df  jmp     short loc_18001D6F1
0x18001d6e1  cmp     eax, r8d
0x18001d6e4  jz      loc_18001D7AB
0x18001d6ea  lea     rcx, aAutojoinsvcSAu; "AutoJoinSvc/%s: Auto join policy change"...
0x18001d6f1  mov     rdx, r15
0x18001d6f4  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001d6fa  mov     eax, [rbp+arg_0]
0x18001d6fd  mov     cs:dword_18004D94C, eax
0x18001d703  cmp     eax, 1
0x18001d706  jnz     short loc_18001D70D
0x18001d708  or      edi, 0FFFFFFFFh
0x18001d70b  jmp     short loc_18001D710
0x18001d70d  mov     edi, r14d
0x18001d710  call    WJCloseAutoJoinTriggerEventTimer
0x18001d715  lea     r9, g_AutoJoinTaskRetryState
0x18001d71c  movzx   r8d, di
0x18001d720  lea     rdx, g_szAutomaticDeviceJoinTaskName; "Automatic-Device-Join"
0x18001d727  lea     rcx, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001d72e  call    WJSetScheduledTaskState
0x18001d733  mov     ebx, eax
0x18001d735  test    di, di
0x18001d738  jz      loc_18001D7BE
0x18001d73e  xor     edx, edx
0x18001d740  lea     rcx, [rbp+arg_10]
0x18001d744  call    cs:__imp_DsrIsDeviceJoined
0x18001d74a  mov     ebx, eax
0x18001d74c  test    eax, eax
0x18001d74e  jns     short loc_18001D765
0x18001d750  mov     r8d, eax
0x18001d753  lea     rcx, aAutojoinsvcSFa_11; "AutoJoinSvc/%s: Failed to determine if "...
0x18001d75a  mov     rdx, r15
0x18001d75d  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001d763  jmp     short loc_18001D7BE
0x18001d765  cmp     [rbp+arg_10], r14d
0x18001d769  jz      short loc_18001D77D
0x18001d76b  mov     rdx, r15
0x18001d76e  lea     rcx, aAutojoinsvcSMa; "AutoJoinSvc/%s: Machine is already join"...
0x18001d775  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d77b  jmp     short loc_18001D7BE
0x18001d77d  call    WJOpenAutoJoinTriggerEventTimer
0x18001d782  mov     edi, eax
0x18001d784  test    eax, eax
0x18001d786  jz      short loc_18001D7BE
0x18001d788  mov     r8d, eax
0x18001d78b  lea     rcx, aAutojoinsvcSFa_16; "AutoJoinSvc/%s: Failed to create thread"...
0x18001d792  mov     rdx, r15
0x18001d795  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001d79b  test    edi, edi
0x18001d79d  jg      short loc_18001D7A3
0x18001d79f  mov     ebx, edi
0x18001d7a1  jmp     short loc_18001D7BE
0x18001d7a3  movzx   ebx, di
0x18001d7a6  jmp     loc_18001D582
0x18001d7ab  mov     rdx, r15
0x18001d7ae  lea     rcx, aAutojoinsvcSAu_0; "AutoJoinSvc/%s: Auto join policy remain"...
0x18001d7b5  mov     ebx, r14d
0x18001d7b8  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d7be  mov     rcx, rsi
0x18001d7c1  call    LeaveMachineCriticalPolicySection
0x18001d7c6  test    ebx, ebx
0x18001d7c8  jns     short loc_18001D7EC
0x18001d7ca  lea     r9, g_szAutomaticDeviceJoinTaskName; "Automatic-Device-Join"
0x18001d7d1  mov     dword ptr [rsp+40h+pdwType], ebx
0x18001d7d5  lea     r8, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001d7dc  mov     rdx, r15
0x18001d7df  lea     rcx, aAutojoinsvcSFa_22; "AutoJoinSvc/%s: Failed to determine sta"...
0x18001d7e6  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001d7ec  mov     r8d, ebx
0x18001d7ef  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001d7f6  mov     rdx, r15
0x18001d7f9  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d7ff  mov     eax, ebx
0x18001d801  mov     rbx, [rsp+40h+arg_18]
0x18001d809  add     rsp, 40h
0x18001d80d  pop     r15
0x18001d80f  pop     r14
0x18001d811  pop     rdi
0x18001d812  pop     rsi
0x18001d813  pop     rbp
0x18001d814  retn
```
