# WscInitSystemOnBootThreadProc(void *)

- ea: `0x1800224a0`
- end: `0x18002266f`
- name: `?WscInitSystemOnBootThreadProc@@YAXPEAX@Z`
- size: `463`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002e30`
- `0x180008e48`
- `0x1800202e8`
- `0x1800224a0`
- `0x180022cb0`
- `0x18002400c`
- `0x18003d100`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180022615`
- `ntdll!RtlPublishWnfStateData` at `0x180022615`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002250e`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002250e`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18002264f`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18002264f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022658`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800224ca`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800224ca`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002252c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002252c`

## pseudocode

```c
ULONG __fastcall WscInitSystemOnBootThreadProc(PVOID Parameter)
{
  HANDLE WaitableTimerW; // rax
  void *v2; // rbx
  int v3; // edi
  DWORD v4; // eax
  struct CThirdPartyManager *v5; // rdx
  struct CWmiEventManagerAvFw *v6; // rcx
  CThirdPartyManager *v7; // rcx
  DWORD LastError; // eax
  int v9; // eax
  __int128 Handles; // [rsp+30h] [rbp-18h] BYREF
  LARGE_INTEGER DueTime; // [rsp+58h] [rbp+10h] BYREF

  DueTime.QuadPart = -600000000;
  Handles = 0;
  WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
  v2 = WaitableTimerW;
  if ( WaitableTimerW )
  {
    v3 = 0;
    *(_QWORD *)&Handles = g_hShutdownThreadNotify;
    *((_QWORD *)&Handles + 1) = WaitableTimerW;
    while ( SetWaitableTimer(v2, &DueTime, 0, 0, 0, 0) )
    {
      v4 = WaitForMultipleObjects(2u, (const HANDLE *)&Handles, 0, 0xFFFFFFFF);
      if ( v4 == -1 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
              LastError);
LABEL_18:
            v7 = WPP_GLOBAL_Control;
          }
          if ( v7 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)v7 + 2), 23, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids);
        }
        v9 = RtlPublishWnfStateData(WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION, 0, 0, 0, 0) | 0x10000000;
        if ( v9 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
            (unsigned int)v9);
        }
        CancelWaitableTimer(v2);
        break;
      }
      if ( v4 != 1 )
        goto LABEL_18;
      if ( v3 )
      {
        if ( g_dwProductStatusInitiated == 7 )
          goto LABEL_18;
        g_dwProductStatusInitiated = 7;
        CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
      }
      else
      {
        if ( (unsigned int)WscDSA_FeatureIsEnabled() )
          WscDSA_StartDefaultApplyThreadAfterReboot(v6, v5);
        else
          SetDefenderStatus((DefenderStateUtils *)1, 5u);
        v3 = 1;
      }
      if ( g_dwProductStatusInitiated == 7 )
        goto LABEL_18;
    }
    LODWORD(WaitableTimerW) = CloseHandle(v2);
  }
  return (unsigned int)WaitableTimerW;
}

```

## disassembly

```asm
0x1800224a0  mov     rax, rsp
0x1800224a3  mov     [rax+8], rbx
0x1800224a7  mov     [rax+18h], rdi
0x1800224ab  push    r14
0x1800224ad  sub     rsp, 40h
0x1800224b1  xor     r8d, r8d; lpTimerName
0x1800224b4  mov     qword ptr [rax+10h], 0FFFFFFFFDC3CBA00h
0x1800224bc  xorps   xmm0, xmm0
0x1800224bf  xor     ecx, ecx; lpTimerAttributes
0x1800224c1  movdqu  xmmword ptr [rax-18h], xmm0
0x1800224c6  lea     edx, [r8+1]; bManualReset
0x1800224ca  call    cs:__imp_CreateWaitableTimerW
0x1800224d0  mov     rbx, rax
0x1800224d3  test    rax, rax
0x1800224d6  jz      loc_18002265E
0x1800224dc  mov     rcx, cs:?g_hShutdownThreadNotify@@3PEAXEA; void * g_hShutdownThreadNotify
0x1800224e3  xor     edi, edi
0x1800224e5  mov     [rsp+48h+Handles], rcx
0x1800224ea  mov     [rsp+48h+var_10], rax
0x1800224ef  mov     [rsp+48h+fResume], 0; fResume
0x1800224f7  lea     rdx, [rsp+48h+DueTime]; lpDueTime
0x1800224fc  xor     r9d, r9d; pfnCompletionRoutine
0x1800224ff  mov     [rsp+48h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x180022508  xor     r8d, r8d; lPeriod
0x18002250b  mov     rcx, rbx; hTimer
0x18002250e  call    cs:__imp_SetWaitableTimer
0x180022514  test    eax, eax
0x180022516  jz      loc_180022655
0x18002251c  xor     r8d, r8d; bWaitAll
0x18002251f  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180022524  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180022528  lea     ecx, [r8+2]; nCount
0x18002252c  call    cs:__imp_WaitForMultipleObjects
0x180022532  lea     r14, WPP_GLOBAL_Control
0x180022539  cmp     eax, 0FFFFFFFFh
0x18002253c  jz      short loc_18002259F
0x18002253e  cmp     eax, 1
0x180022541  jnz     loc_1800225D6
0x180022547  test    edi, edi
0x180022549  jnz     short loc_18002256F
0x18002254b  call    ?WscDSA_FeatureIsEnabled@@YAHXZ; WscDSA_FeatureIsEnabled(void)
0x180022550  test    eax, eax
0x180022552  jz      short loc_18002255B
0x180022554  call    ?WscDSA_StartDefaultApplyThreadAfterReboot@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@@Z; WscDSA_StartDefaultApplyThreadAfterReboot(CWmiEventManagerAvFw *,CThirdPartyManager *)
0x180022559  jmp     short loc_180022568
0x18002255b  mov     edx, 5; unsigned int
0x180022560  lea     ecx, [rdx-4]; this
0x180022563  call    ?SetDefenderStatus@@YAJHK@Z; SetDefenderStatus(int,ulong)
0x180022568  mov     edi, 1
0x18002256d  jmp     short loc_180022590
0x18002256f  cmp     cs:?g_dwProductStatusInitiated@@3KA, 7; ulong g_dwProductStatusInitiated
0x180022576  jz      short loc_1800225D6
0x180022578  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x18002257f  xor     edx, edx; int
0x180022581  mov     cs:?g_dwProductStatusInitiated@@3KA, 7; ulong g_dwProductStatusInitiated
0x18002258b  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180022590  cmp     cs:?g_dwProductStatusInitiated@@3KA, 7; ulong g_dwProductStatusInitiated
0x180022597  jnz     loc_1800224EF
0x18002259d  jmp     short loc_1800225D6
0x18002259f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225a6  cmp     rcx, r14
0x1800225a9  jz      short loc_1800225FD
0x1800225ab  test    byte ptr [rcx+1Ch], 1
0x1800225af  jz      short loc_1800225DD
0x1800225b1  call    cs:__imp_GetLastError
0x1800225b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225be  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800225c5  mov     edx, 16h
0x1800225ca  mov     r9d, eax
0x1800225cd  mov     rcx, [rcx+10h]
0x1800225d1  call    WPP_SF_d
0x1800225d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225dd  cmp     rcx, r14
0x1800225e0  jz      short loc_1800225FD
0x1800225e2  test    byte ptr [rcx+1Ch], 10h
0x1800225e6  jz      short loc_1800225FD
0x1800225e8  mov     rcx, [rcx+10h]
0x1800225ec  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800225f3  mov     edx, 17h
0x1800225f8  call    WPP_SF_
0x1800225fd  mov     rcx, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x180022604  xor     r9d, r9d
0x180022607  xor     r8d, r8d
0x18002260a  mov     [rsp+48h+lpArgToCompletionRoutine], 0
0x180022613  xor     edx, edx
0x180022615  call    cs:__imp_RtlPublishWnfStateData
0x18002261b  or      eax, 10000000h
0x180022620  jge     short loc_18002264C
0x180022622  mov     rcx, cs:WPP_GLOBAL_Control
0x180022629  cmp     rcx, r14
0x18002262c  jz      short loc_18002264C
0x18002262e  test    byte ptr [rcx+1Ch], 1
0x180022632  jz      short loc_18002264C
0x180022634  mov     rcx, [rcx+10h]
0x180022638  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18002263f  mov     edx, 18h
0x180022644  mov     r9d, eax
0x180022647  call    WPP_SF_d
0x18002264c  mov     rcx, rbx; hTimer
0x18002264f  call    cs:__imp_CancelWaitableTimer
0x180022655  mov     rcx, rbx; hObject
0x180022658  call    cs:__imp_CloseHandle
0x18002265e  mov     rbx, [rsp+48h+arg_0]
0x180022663  mov     rdi, [rsp+48h+arg_10]
0x180022668  add     rsp, 40h
0x18002266c  pop     r14
0x18002266e  retn
```
