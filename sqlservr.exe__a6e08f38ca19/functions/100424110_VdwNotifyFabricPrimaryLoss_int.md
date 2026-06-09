# VdwNotifyFabricPrimaryLoss(int)

- ea: `0x100424110`
- end: `0x1004244df`
- name: `?VdwNotifyFabricPrimaryLoss@@YAXH@Z`
- size: `975`
- prototype: `void __fastcall(int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x10040a080`
- `0x100423fb0`
- `0x100424080`
- `0x100424110`
- `0x1004406a0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1004241e5`
- `KERNEL32!SetEvent` at `0x1004241e5`
- `KERNEL32!HeapFree` at `0x1004242fa`
- `KERNEL32!HeapFree` at `0x1004243ae`
- `KERNEL32!HeapFree` at `0x1004243ea`
- `KERNEL32!HeapFree` at `0x1004242fa`
- `KERNEL32!HeapFree` at `0x1004243ae`
- `KERNEL32!HeapFree` at `0x1004243ea`
- `KERNEL32!GetProcessHeap` at `0x1004242ec`
- `KERNEL32!GetProcessHeap` at `0x1004243a0`
- `KERNEL32!GetProcessHeap` at `0x1004243dc`
- `KERNEL32!GetProcessHeap` at `0x1004242ec`
- `KERNEL32!GetProcessHeap` at `0x1004243a0`
- `KERNEL32!GetProcessHeap` at `0x1004243dc`
- `sqlmin!?FireXEventForPlatformCallback@@YAXPEB_WH0H0H@Z` at `0x100424156`
- `sqlmin!?FireXEventForPlatformCallback@@YAXPEB_WH0H0H@Z` at `0x1004244ca`
- `sqlmin!?FireXEventForPlatformCallback@@YAXPEB_WH0H0H@Z` at `0x100424156`
- `sqlmin!?FireXEventForPlatformCallback@@YAXPEB_WH0H0H@Z` at `0x1004244ca`
- `sqlmin!?DeactivationDetection@DynamicDeactivationTask@@SA?AW4DetectionRunStatus@@PEAVDBTABLE@@@Z` at `0x100424286`
- `sqlmin!?DeactivationDetection@DynamicDeactivationTask@@SA?AW4DetectionRunStatus@@PEAVDBTABLE@@@Z` at `0x100424286`
- `sqlmin!GetXdbServerGlobals` at `0x100424177`
- `sqlmin!GetXdbServerGlobals` at `0x10042423e`
- `sqlmin!GetXdbServerGlobals` at `0x100424412`
- `sqlmin!GetXdbServerGlobals` at `0x100424436`
- `sqlmin!GetXdbServerGlobals` at `0x100424177`
- `sqlmin!GetXdbServerGlobals` at `0x10042423e`
- `sqlmin!GetXdbServerGlobals` at `0x100424412`
- `sqlmin!GetXdbServerGlobals` at `0x100424436`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100424270`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100424270`
- `sqlmin!?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z` at `0x1004241c2`
- `sqlmin!?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z` at `0x1004241c2`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100424279`
- `sqldk!?SetShutdownOption@@YAXW4ShutdownOption@@K@Z` at `0x100424453`
- `sqldk!?SetShutdownOption@@YAXW4ShutdownOption@@K@Z` at `0x100424453`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10042449c`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10042449c`
- `hostregdll!HostReg_ReadConfigurationSetting` at `0x1004242b5`
- `hostregdll!HostReg_ReadConfigurationSetting` at `0x1004242b5`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x10042419b`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100424262`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x10042419b`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100424262`
- `hostregdll!HostReg_SpAlterXDBConfigHelper` at `0x100424348`
- `hostregdll!HostReg_SpAlterXDBConfigHelper` at `0x100424348`
- `RgThinClient!RgClient_WriteETWTrace` at `0x1004241fc`
- `RgThinClient!RgClient_WriteETWTrace` at `0x10042421d`
- `RgThinClient!RgClient_WriteETWTrace` at `0x1004242dc`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100424391`
- `RgThinClient!RgClient_WriteETWTrace` at `0x1004243c7`
- `RgThinClient!RgClient_WriteETWTrace` at `0x1004241fc`
- `RgThinClient!RgClient_WriteETWTrace` at `0x10042421d`
- `RgThinClient!RgClient_WriteETWTrace` at `0x1004242dc`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100424391`
- `RgThinClient!RgClient_WriteETWTrace` at `0x1004243c7`
- `sqlfabric!SpAlterXDBConfigHelper` at `0x100424328`
- `sqlfabric!SpAlterXDBConfigHelper` at `0x100424328`

## string_xrefs

- `0x100424194`: `SQL.Config`
- `0x1004241bb`: `SQL.Config`
- `0x10042425b`: `SQL.Config`
- `0x1004242ae`: `SQL.Config`
- `0x100424321`: `SQL.Config`
- `0x100424341`: `SQL.Config`
- `0x10042436e`: `SQL.Config`
- `0x100424216`: `Failed to create and signal the starting notify primary loss event.`
- `0x10042418d`: `VdwBackendFailoverCommunicationEnabled`
- `0x100424254`: `VdwFrontendFailoverCommunicationEnabled`
- `0x1004242d5`: `Failed to read config FrontendFailoverActivityDetectionIntervalMin.`
- `0x10042438a`: `Failed to update dynamic deactivation interval.`
- `0x1004243c0`: `Updated dynamic deactivation interval.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VdwNotifyFabricPrimaryLoss(int a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // edi
  __int64 v5; // rdx
  DWORD NotifyPrimaryLossTimeoutInSeconds; // eax
  unsigned __int16 MasterDbId; // ax
  __int64 v8; // rax
  DWORD v9; // esi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  int v15; // esi
  const wchar_t *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  HANDLE v19; // rax
  HANDLE v20; // rax
  int v21; // [rsp+20h] [rbp-78h]
  int v22; // [rsp+38h] [rbp-60h] BYREF
  __int64 v23; // [rsp+40h] [rbp-58h]
  __int64 v24; // [rsp+48h] [rbp-50h]
  __int64 v25; // [rsp+50h] [rbp-48h]
  __int64 v26; // [rsp+58h] [rbp-40h]
  int v27; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+18h]
  HANDLE hEvent; // [rsp+B8h] [rbp+20h]

  FireXEventForPlatformCallback(
    L"notify_primary_loss",
    20,
    L"Started",
    8,
    L"Entering VdwNotifyFabricPrimaryLoss callback.",
    46);
  v4 = 1;
  if ( *((_DWORD *)qword_10049F360 + 3626)
    && *(_BYTE *)(GetXdbServerGlobals(v3, v2) + 12011)
    && (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"VdwBackendFailoverCommunicationEnabled", 0) )
  {
    hEvent = StartUp::ReadEventNameAndCreateNodeLevelEventIfXdbInstance(
               L"SQL.Config",
               L"SQL",
               L"NotifyPrimaryLossStartEventName",
               1,
               0);
    if ( hEvent && SetEvent(hEvent) )
    {
      LOBYTE(v5) = 4;
      RgClient_WriteETWTrace(L"The starting notify primary loss event signalled.", v5, 1);
      NotifyPrimaryLossTimeoutInSeconds = getNotifyPrimaryLossTimeoutInSeconds();
      waitOnNotifyPrimaryLossEndEvent(NotifyPrimaryLossTimeoutInSeconds);
    }
    else
    {
      LOBYTE(v5) = 2;
      RgClient_WriteETWTrace(L"Failed to create and signal the starting notify primary loss event.", v5, 1);
    }
  }
  if ( *((_DWORD *)qword_10049F360 + 3626)
    && *(_BYTE *)(GetXdbServerGlobals(v3, v2) + 12010)
    && (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"VdwFrontendFailoverCommunicationEnabled", 0) )
  {
    MasterDbId = GetMasterDbId();
    v8 = g_dbtableFactory[4](MasterDbId);
    v9 = 0;
    if ( (unsigned int)DynamicDeactivationTask::DeactivationDetection(v8) != 9 )
    {
      v10 = HostReg_ReadConfigurationSetting(
              L"SQL.Config",
              L"SQL",
              L"FrontendFailoverActivityDetectionIntervalMin",
              &v27);
      v13 = (void *)v10;
      v28 = v10;
      if ( v27 < 0 )
      {
        LOBYTE(v12) = 1;
        LOBYTE(v11) = 2;
        RgClient_WriteETWTrace(L"Failed to read config FrontendFailoverActivityDetectionIntervalMin.", v11, v12);
        if ( v13 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v13);
          v28 = 0;
        }
        goto LABEL_25;
      }
      v15 = SpAlterXDBConfigHelper(L"SQL.Config", L"RgSettings", L"DynamicDeactivationIntervalMin", v10);
      if ( !v15 )
        v15 = HostReg_SpAlterXDBConfigHelper(L"SQL.Config", L"RgSettings", L"DynamicDeactivationIntervalMin", v13);
      v16 = L"Failed";
      if ( !v15 )
        v16 = L"Succeeded";
      SOSLogToErrorLog(
        L"%ls applying override for package='%ls', section='%ls', setting='%ls' to value='%ls'.",
        v16,
        L"SQL.Config",
        L"RgSettings",
        L"DynamicDeactivationIntervalMin",
        v13,
        -2);
      LOBYTE(v18) = 1;
      if ( v15 < 0 )
      {
        LOBYTE(v17) = 2;
        RgClient_WriteETWTrace(L"Failed to update dynamic deactivation interval.", v17, v18);
        if ( v13 )
        {
          _mm_lfence();
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v13);
          v28 = 0;
        }
        goto LABEL_25;
      }
      LOBYTE(v17) = 4;
      RgClient_WriteETWTrace(L"Updated dynamic deactivation interval.", v17, v18);
      v9 = getNotifyPrimaryLossTimeoutInSeconds();
      if ( v13 )
      {
        _mm_lfence();
        v20 = GetProcessHeap();
        HeapFree(v20, 0, v13);
        v28 = 0;
      }
    }
    waitOnNotifyPrimaryLossEndEvent(v9);
  }
LABEL_25:
  if ( !a1 )
  {
    if ( *((_DWORD *)qword_10049F360 + 3626) && *(_BYTE *)(GetXdbServerGlobals(v3, v2) + 12010) )
    {
      v4 = 5;
    }
    else if ( !*((_DWORD *)qword_10049F360 + 3626) || (v4 = 4, !*(_BYTE *)(GetXdbServerGlobals(v3, v2) + 12011)) )
    {
      v4 = 2;
    }
  }
  SetShutdownOption(v4, 0);
  EventManualInternal<SuspendQueueSLock>::Signal(&off_1004A08D8, 0);
  v22 = 4194555;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  LOBYTE(v21) = 1;
  WaitableBase::Wait(&off_1004A0908, 0xFFFFFFFFLL, &v22, 0, v21);
  FireXEventForPlatformCallback(
    L"notify_primary_loss",
    20,
    L"Succeeded",
    10,
    L"Exiting VdwNotifyFabricPrimaryLoss callback.",
    45);
}

```

## disassembly

```asm
0x100424110  push    rbx
0x100424112  push    rbp
0x100424113  push    rsi
0x100424114  push    rdi
0x100424115  push    r12
0x100424117  push    r14
0x100424119  push    r15
0x10042411b  sub     rsp, 60h
0x10042411f  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x100424128  mov     ebp, ecx
0x10042412a  mov     dword ptr [rsp+98h+var_70], 2Eh ; '.'
0x100424132  lea     rax, aEnteringVdwnot; "Entering VdwNotifyFabricPrimaryLoss cal"...
0x100424139  mov     [rsp+98h+var_78], rax
0x10042413e  mov     r9d, 8
0x100424144  lea     r8, aStarted; "Started"
0x10042414b  lea     edx, [r9+0Ch]
0x10042414f  lea     rcx, aNotifyPrimaryL; "notify_primary_loss"
0x100424156  call    cs:__imp_?FireXEventForPlatformCallback@@YAXPEB_WH0H0H@Z; FireXEventForPlatformCallback(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)
0x10042415c  xor     r14d, r14d
0x10042415f  lea     edi, [r14+1]
0x100424163  mov     rax, cs:qword_10049F360
0x10042416a  cmp     [rax+38A8h], r14d
0x100424171  jz      loc_100424223
0x100424177  call    cs:__imp_GetXdbServerGlobals
0x10042417d  cmp     [rax+2EEBh], r14b
0x100424184  jz      loc_100424223
0x10042418a  xor     r8d, r8d
0x10042418d  lea     rdx, aVdwbackendfail; "VdwBackendFailoverCommunicationEnabled"
0x100424194  lea     rcx, aSqlConfig; "SQL.Config"
0x10042419b  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x1004241a1  test    al, al
0x1004241a3  jz      short loc_100424223
0x1004241a5  mov     dword ptr [rsp+98h+var_78], r14d
0x1004241aa  mov     r9d, edi
0x1004241ad  lea     r8, aNotifyprimaryl; "NotifyPrimaryLossStartEventName"
0x1004241b4  lea     rdx, aSql; "SQL"
0x1004241bb  lea     rcx, aSqlConfig; "SQL.Config"
0x1004241c2  call    cs:__imp_?ReadEventNameAndCreateNodeLevelEventIfXdbInstance@StartUp@@SAREAXPEB_W00HH@Z; StartUp::ReadEventNameAndCreateNodeLevelEventIfXdbInstance(wchar_t const *,wchar_t const *,wchar_t const *,int,int)
0x1004241c8  mov     [rsp+98h+hEvent], rax
0x1004241d0  mov     rax, [rsp+98h+hEvent]
0x1004241d8  test    rax, rax
0x1004241db  jz      short loc_100424210
0x1004241dd  mov     rcx, [rsp+98h+hEvent]; hEvent
0x1004241e5  call    cs:__imp_SetEvent
0x1004241eb  test    eax, eax
0x1004241ed  jz      short loc_100424210
0x1004241ef  movzx   r8d, dil
0x1004241f3  mov     dl, 4
0x1004241f5  lea     rcx, aTheStartingNot; "The starting notify primary loss event "...
0x1004241fc  call    cs:__imp_RgClient_WriteETWTrace
0x100424202  call    ?getNotifyPrimaryLossTimeoutInSeconds@@YAKXZ; getNotifyPrimaryLossTimeoutInSeconds(void)
0x100424207  mov     ecx, eax; dwMilliseconds
0x100424209  call    ?waitOnNotifyPrimaryLossEndEvent@@YA_NK@Z; waitOnNotifyPrimaryLossEndEvent(ulong)
0x10042420e  jmp     short loc_100424223
0x100424210  movzx   r8d, dil
0x100424214  mov     dl, 2
0x100424216  lea     rcx, aFailedToCreate; "Failed to create and signal the startin"...
0x10042421d  call    cs:__imp_RgClient_WriteETWTrace
0x100424223  lea     r12, aSucceeded; "Succeeded"
0x10042422a  mov     rax, cs:qword_10049F360
0x100424231  cmp     [rax+38A8h], r14d
0x100424238  jz      loc_1004243FF
0x10042423e  call    cs:__imp_GetXdbServerGlobals
0x100424244  cmp     [rax+2EEAh], r14b
0x10042424b  jz      loc_1004243FF
0x100424251  xor     r8d, r8d
0x100424254  lea     rdx, aVdwfrontendfai; "VdwFrontendFailoverCommunicationEnabled"
0x10042425b  lea     rcx, aSqlConfig; "SQL.Config"
0x100424262  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100424268  test    al, al
0x10042426a  jz      loc_1004243FF
0x100424270  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x100424276  movzx   ecx, ax
0x100424279  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x100424280  call    qword ptr [rax+20h]
0x100424283  mov     rcx, rax
0x100424286  call    cs:__imp_?DeactivationDetection@DynamicDeactivationTask@@SA?AW4DetectionRunStatus@@PEAVDBTABLE@@@Z; DynamicDeactivationTask::DeactivationDetection(DBTABLE *)
0x10042428c  mov     esi, r14d
0x10042428f  cmp     eax, 9
0x100424292  jz      loc_1004243F8
0x100424298  lea     r9, [rsp+98h+arg_8]
0x1004242a0  lea     r8, aFrontendfailov; "FrontendFailoverActivityDetectionInterv"...
0x1004242a7  lea     rdx, aSql; "SQL"
0x1004242ae  lea     rcx, aSqlConfig; "SQL.Config"
0x1004242b5  call    cs:__imp_HostReg_ReadConfigurationSetting
0x1004242bb  mov     rbx, rax
0x1004242be  mov     [rsp+98h+arg_10], rax
0x1004242c6  cmp     [rsp+98h+arg_8], 0
0x1004242ce  jge     short loc_10042430D
0x1004242d0  mov     r8b, 1
0x1004242d3  mov     dl, 2
0x1004242d5  lea     rcx, aFailedToReadCo; "Failed to read config FrontendFailoverA"...
0x1004242dc  call    cs:__imp_RgClient_WriteETWTrace
0x1004242e2  nop
0x1004242e3  test    rbx, rbx
0x1004242e6  jz      loc_1004243FF
0x1004242ec  call    cs:__imp_GetProcessHeap
0x1004242f2  mov     rcx, rax; hHeap
0x1004242f5  mov     r8, rbx; lpMem
0x1004242f8  xor     edx, edx; dwFlags
0x1004242fa  call    cs:__imp_HeapFree
0x100424300  mov     [rsp+98h+arg_10], r14
0x100424308  jmp     loc_1004243FF
0x10042430d  mov     r9, rbx
0x100424310  lea     r15, aDynamicdeactiv; "DynamicDeactivationIntervalMin"
0x100424317  mov     r8, r15
0x10042431a  lea     rdx, aRgsettings; "RgSettings"
0x100424321  lea     rcx, aSqlConfig; "SQL.Config"
0x100424328  call    cs:__imp_SpAlterXDBConfigHelper
0x10042432e  mov     esi, eax
0x100424330  test    eax, eax
0x100424332  jnz     short loc_100424350
0x100424334  mov     r9, rbx
0x100424337  mov     r8, r15
0x10042433a  lea     rdx, aRgsettings; "RgSettings"
0x100424341  lea     rcx, aSqlConfig; "SQL.Config"
0x100424348  call    cs:__imp_HostReg_SpAlterXDBConfigHelper
0x10042434e  mov     esi, eax
0x100424350  lea     rdx, aFailed; "Failed"
0x100424357  test    esi, esi
0x100424359  cmovz   rdx, r12
0x10042435d  mov     [rsp+98h+var_70], rbx
0x100424362  mov     [rsp+98h+var_78], r15
0x100424367  lea     r9, aRgsettings; "RgSettings"
0x10042436e  lea     r8, aSqlConfig; "SQL.Config"
0x100424375  lea     rcx, aLsApplyingOver; "%ls applying override for package='%ls'"...
0x10042437c  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x100424381  mov     r8b, 1
0x100424384  test    esi, esi
0x100424386  jns     short loc_1004243BE
0x100424388  mov     dl, 2
0x10042438a  lea     rcx, aFailedToUpdate; "Failed to update dynamic deactivation i"...
0x100424391  call    cs:__imp_RgClient_WriteETWTrace
0x100424397  nop
0x100424398  test    rbx, rbx
0x10042439b  jz      short loc_1004243FF
0x10042439d  lfence
0x1004243a0  call    cs:__imp_GetProcessHeap
0x1004243a6  mov     rcx, rax; hHeap
0x1004243a9  mov     r8, rbx; lpMem
0x1004243ac  xor     edx, edx; dwFlags
0x1004243ae  call    cs:__imp_HeapFree
0x1004243b4  mov     [rsp+98h+arg_10], r14
0x1004243bc  jmp     short loc_1004243FF
0x1004243be  mov     dl, 4
0x1004243c0  lea     rcx, aUpdatedDynamic; "Updated dynamic deactivation interval."
0x1004243c7  call    cs:__imp_RgClient_WriteETWTrace
0x1004243cd  call    ?getNotifyPrimaryLossTimeoutInSeconds@@YAKXZ; getNotifyPrimaryLossTimeoutInSeconds(void)
0x1004243d2  mov     esi, eax
0x1004243d4  test    rbx, rbx
0x1004243d7  jz      short loc_1004243F8
0x1004243d9  lfence
0x1004243dc  call    cs:__imp_GetProcessHeap
0x1004243e2  mov     rcx, rax; hHeap
0x1004243e5  mov     r8, rbx; lpMem
0x1004243e8  xor     edx, edx; dwFlags
0x1004243ea  call    cs:__imp_HeapFree
0x1004243f0  mov     [rsp+98h+arg_10], r14
0x1004243f8  mov     ecx, esi; dwMilliseconds
0x1004243fa  call    ?waitOnNotifyPrimaryLossEndEvent@@YA_NK@Z; waitOnNotifyPrimaryLossEndEvent(ulong)
0x1004243ff  test    ebp, ebp
0x100424401  jnz     short loc_10042444F
0x100424403  mov     rax, cs:qword_10049F360
0x10042440a  cmp     [rax+38A8h], ebp
0x100424410  jz      short loc_100424426
0x100424412  call    cs:__imp_GetXdbServerGlobals
0x100424418  cmp     [rax+2EEAh], bpl
0x10042441f  jz      short loc_100424426
0x100424421  lea     edi, [rbp+5]
0x100424424  jmp     short loc_10042444F
0x100424426  mov     rax, cs:qword_10049F360
0x10042442d  cmp     dword ptr [rax+38A8h], 0
0x100424434  jz      short loc_10042444A
0x100424436  call    cs:__imp_GetXdbServerGlobals
0x10042443c  cmp     byte ptr [rax+2EEBh], 0
0x100424443  mov     edi, 4
0x100424448  jnz     short loc_10042444F
0x10042444a  mov     edi, 2
0x10042444f  xor     edx, edx
0x100424451  mov     ecx, edi
0x100424453  call    cs:__imp_?SetShutdownOption@@YAXW4ShutdownOption@@K@Z; SetShutdownOption(ShutdownOption,ulong)
0x100424459  xor     edx, edx
0x10042445b  lea     rcx, off_1004A08D8
0x100424462  call    ?Signal@?$EventManualInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventManualInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100424467  mov     [rsp+98h+var_60], 4000FBh
0x10042446f  mov     [rsp+98h+var_58], r14
0x100424474  mov     [rsp+98h+var_48], r14
0x100424479  mov     [rsp+98h+var_50], r14
0x10042447e  mov     [rsp+98h+var_40], r14
0x100424483  mov     byte ptr [rsp+98h+var_78], 1
0x100424488  xor     r9d, r9d
0x10042448b  lea     r8, [rsp+98h+var_60]
0x100424490  mov     edx, 0FFFFFFFFh
0x100424495  lea     rcx, off_1004A0908
0x10042449c  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x1004244a2  mov     dword ptr [rsp+98h+var_70], 2Dh ; '-'
0x1004244aa  lea     rax, aExitingVdwnoti; "Exiting VdwNotifyFabricPrimaryLoss call"...
0x1004244b1  mov     [rsp+98h+var_78], rax
0x1004244b6  mov     r9d, 0Ah
0x1004244bc  mov     r8, r12
0x1004244bf  lea     edx, [r9+0Ah]
0x1004244c3  lea     rcx, aNotifyPrimaryL; "notify_primary_loss"
0x1004244ca  call    cs:__imp_?FireXEventForPlatformCallback@@YAXPEB_WH0H0H@Z; FireXEventForPlatformCallback(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)
0x1004244d0  add     rsp, 60h
0x1004244d4  pop     r15
0x1004244d6  pop     r14
0x1004244d8  pop     r12
0x1004244da  pop     rdi
0x1004244db  pop     rsi
0x1004244dc  pop     rbp
0x1004244dd  pop     rbx
0x1004244de  retn
```
