# UserThreadCallout

- ea: `0x1400d7a30`
- end: `0x1400d7f09`
- name: `UserThreadCallout`
- size: `1241`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140029710`
- `0x140029d90`
- `0x140049ec0`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400a2250`
- `0x1400d7988`
- `0x1400d79e0`
- `0x1400d7a30`
- `0x1400d825c`
- `0x1400d8288`
- `0x1400d8314`
- `0x1400d98bc`
- `0x140114808`
- `0x14014065c`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1400d7b3a`
- `ntoskrnl!PsGetProcessPeb` at `0x1400d7b3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7b8a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7d0a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7b8a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7d0a`
- `ntoskrnl!PsGetThreadProcess` at `0x1400d7b1f`
- `ntoskrnl!PsGetThreadProcess` at `0x1400d7b1f`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400d7b52`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400d7b52`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d7b7b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d7cfb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d7b7b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d7cfb`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d7e25`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d7e9c`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d7e25`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d7e9c`
- `WIN32K!W32GetUserSessionState` at `0x1400d7a92`
- `WIN32K!W32GetUserSessionState` at `0x1400d7ada`
- `WIN32K!W32GetUserSessionState` at `0x1400d7af3`
- `WIN32K!W32GetUserSessionState` at `0x1400d7b6c`
- `WIN32K!W32GetUserSessionState` at `0x1400d7c1b`
- `WIN32K!W32GetUserSessionState` at `0x1400d7ca4`
- `WIN32K!W32GetUserSessionState` at `0x1400d7cec`
- `WIN32K!W32GetUserSessionState` at `0x1400d7d60`
- `WIN32K!W32GetUserSessionState` at `0x1400d7d79`
- `WIN32K!W32GetUserSessionState` at `0x1400d7a92`
- `WIN32K!W32GetUserSessionState` at `0x1400d7ada`
- `WIN32K!W32GetUserSessionState` at `0x1400d7af3`
- `WIN32K!W32GetUserSessionState` at `0x1400d7b6c`
- `WIN32K!W32GetUserSessionState` at `0x1400d7c1b`
- `WIN32K!W32GetUserSessionState` at `0x1400d7ca4`
- `WIN32K!W32GetUserSessionState` at `0x1400d7cec`
- `WIN32K!W32GetUserSessionState` at `0x1400d7d60`
- `WIN32K!W32GetUserSessionState` at `0x1400d7d79`

## pseudocode

```c
__int64 __fastcall UserThreadCallout(PETHREAD Thread, __int64 a2)
{
  unsigned int ThreadInfo; // r14d
  _UNKNOWN **v3; // r8
  char v5; // di
  CTouchProcessor *v6; // rcx
  bool v7; // bl
  bool v8; // si
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // r8
  PEPROCESS ThreadProcess; // rax
  PEPROCESS v20; // rsi
  __int64 ProcessSectionBaseAddress; // rax
  __int64 v22; // rsi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  bool v30; // bl
  __int64 v31; // rax
  int v32; // r8d
  int v33; // edx
  CTouchProcessor *v35; // rcx
  bool v36; // bl
  bool v37; // si
  __int64 UserSessionState; // rax
  int v39; // r8d
  int v40; // edx
  __int64 v41; // rsi
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v47; // rcx
  __int64 ThreadWin32Thread; // rbx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rax
  _BYTE v55[8]; // [rsp+40h] [rbp-48h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v56; // [rsp+48h] [rbp-40h]

  ThreadInfo = 0;
  v3 = &WPP_RECORDER_INITIALIZED;
  v5 = 1;
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 != 1 )
      goto LABEL_19;
    v35 = WPP_GLOBAL_Control;
    v36 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v37 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, a2, &WPP_RECORDER_INITIALIZED);
      LOBYTE(v39) = v37;
      LOBYTE(v40) = v36;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v40,
        v39,
        *(_QWORD *)(UserSessionState + 69136),
        4,
        14,
        27,
        (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids);
    }
    v41 = W32GetUserSessionState(v35, a2, v3);
    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v43, v42, v44, v45);
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v41,
      (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
    if ( *(_QWORD *)CurrentThreadWin32Thread )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v47 = *(_QWORD *)CurrentThreadWin32Thread;
        *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
        goto LABEL_35;
      }
      *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
    }
    v47 = 0;
LABEL_35:
    *(_QWORD *)(v41 + 16) = v47;
    if ( v47 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v47) )
    {
      DestroySharedUserCritDeferredUnlockList(v41 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v41 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v41 + 19560);
    }
    ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
    _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 1u);
    if ( !*(_DWORD *)(W32GetUserSessionState(v50, v49, v51) + 68596) || *(_DWORD *)(W32GetUserGdiSessionState() + 32) )
    {
      v54 = W32GetUserSessionState(v29, v52, v53);
      GreCleanDC(*(HDC *)(*(_QWORD *)(v54 + 56744) + 56LL));
    }
    if ( (*(_BYTE *)(ThreadWin32Thread + 1360) & 2) != 0 )
    {
      *(_DWORD *)(W32GetUserGdiSessionState() + 36) = 0;
      v55[0] = 0;
      CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v55, 0, 0x4Fu, 0);
      DispBrokerAsyncSessionStateChanged(v56);
      CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v55);
    }
    if ( (*(_BYTE *)(ThreadWin32Thread + 1360) & 1) == 0 )
      xxxDestroyThreadInfo();
    goto LABEL_18;
  }
  v6 = WPP_GLOBAL_Control;
  v7 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = W32GetUserSessionState(WPP_GLOBAL_Control, a2, &WPP_RECORDER_INITIALIZED);
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v11,
      v10,
      *(_QWORD *)(v9 + 69136),
      4,
      14,
      26,
      (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids);
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v6, a2, v3) + 2684) )
    return 3221225473LL;
  if ( *(_DWORD *)(W32GetUserSessionState(v13, v12, v14) + 68392) )
  {
    v17 = W32GetThreadWin32Thread(Thread);
    if ( v17 )
    {
      ThreadProcess = PsGetThreadProcess(Thread);
      v20 = ThreadProcess;
      if ( ThreadProcess && PsGetProcessPeb(ThreadProcess) )
      {
        ProcessSectionBaseAddress = PsGetProcessSectionBaseAddress(v20);
        *(_DWORD *)(v17 + 664) = RtlGetExpWinVer(ProcessSectionBaseAddress);
      }
      else
      {
        *(_DWORD *)(v17 + 664) = 0;
      }
    }
    v22 = W32GetUserSessionState(v16, v15, v18);
    v27 = PsGetCurrentThreadWin32Thread(v24, v23, v25, v26);
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v22,
      (struct _W32THREADNONPAGED *)v27);
    if ( *(_QWORD *)v27 )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v28 = *(_QWORD *)v27;
        *(_BYTE *)(*(_QWORD *)v27 + 1708LL) = 1;
        goto LABEL_16;
      }
      *(_DWORD *)(v27 + 24) |= 2u;
    }
    v28 = 0;
LABEL_16:
    *(_QWORD *)(v22 + 16) = v28;
    if ( v28 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v28) )
    {
      DestroySharedUserCritDeferredUnlockList(v22 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v22 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v22 + 19560);
    }
    ThreadInfo = xxxCreateThreadInfo(Thread);
LABEL_18:
    UserSessionSwitchLeaveCritWithNonPaged(v29);
    goto LABEL_19;
  }
  _interlockedbittestandset((volatile signed __int32 *)(W32GetThreadWin32Thread(Thread) + 1360), 0);
LABEL_19:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v5 = 0;
  }
  v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v31 = W32GetUserSessionState(WPP_GLOBAL_Control, a2, &WPP_RECORDER_INITIALIZED);
    LOBYTE(v32) = v30;
    LOBYTE(v33) = v5;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v33,
      v32,
      *(_QWORD *)(v31 + 69136),
      4,
      14,
      28,
      (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids);
  }
  return ThreadInfo;
}

```

## disassembly

```asm
0x1400d7a30  push    rbx
0x1400d7a32  push    rbp
0x1400d7a33  push    rsi
0x1400d7a34  push    rdi
0x1400d7a35  push    r13
0x1400d7a37  push    r14
0x1400d7a39  sub     rsp, 58h
0x1400d7a3d  xor     r14d, r14d
0x1400d7a40  lea     r13, WPP_GLOBAL_Control
0x1400d7a47  lea     r8, WPP_RECORDER_INITIALIZED
0x1400d7a4e  mov     rbp, rcx
0x1400d7a51  lea     rsi, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x1400d7a58  lea     edi, [r14+1]
0x1400d7a5c  test    edx, edx
0x1400d7a5e  jnz     loc_1400D7C6E
0x1400d7a64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7a6b  cmp     rcx, r13
0x1400d7a6e  jz      short loc_1400D7A7D
0x1400d7a70  test    dword ptr [rcx+2Ch], 2000h
0x1400d7a77  jnz     loc_1400D7EDD
0x1400d7a7d  xor     bl, bl
0x1400d7a7f  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400d7a86  setnz   sil
0x1400d7a8a  test    bl, bl
0x1400d7a8c  jz      loc_1400D7DB9
0x1400d7a92  call    cs:__imp_W32GetUserSessionState
0x1400d7a99  nop     dword ptr [rax+rax+00h]
0x1400d7a9e  lea     rcx, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x1400d7aa5  mov     r8b, sil
0x1400d7aa8  mov     [rsp+88h+var_50], rcx
0x1400d7aad  mov     dl, bl
0x1400d7aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7ab6  mov     r9, [rax+10E10h]
0x1400d7abd  mov     [rsp+88h+var_58], 1Ah
0x1400d7ac4  mov     [rsp+88h+var_60], 0Eh
0x1400d7acc  mov     rcx, [rcx+18h]
0x1400d7ad0  mov     [rsp+88h+var_68], 4
0x1400d7ad5  call    WPP_RECORDER_AND_TRACE_SF_
0x1400d7ada  call    cs:__imp_W32GetUserSessionState
0x1400d7ae1  nop     dword ptr [rax+rax+00h]
0x1400d7ae6  cmp     [rax+0A7Ch], r14d
0x1400d7aed  jnz     loc_1400D7E1B
0x1400d7af3  call    cs:__imp_W32GetUserSessionState
0x1400d7afa  nop     dword ptr [rax+rax+00h]
0x1400d7aff  mov     rcx, rbp
0x1400d7b02  cmp     [rax+10B28h], r14d
0x1400d7b09  jz      loc_1400D7DD5
0x1400d7b0f  call    W32GetThreadWin32Thread
0x1400d7b14  mov     rbx, rax
0x1400d7b17  test    rax, rax
0x1400d7b1a  jz      short loc_1400D7B6C
0x1400d7b1c  mov     rcx, rbp; Thread
0x1400d7b1f  call    cs:__imp_PsGetThreadProcess
0x1400d7b26  nop     dword ptr [rax+rax+00h]
0x1400d7b2b  mov     rsi, rax
0x1400d7b2e  test    rax, rax
0x1400d7b31  jz      loc_1400D7E73
0x1400d7b37  mov     rcx, rax
0x1400d7b3a  call    cs:__imp_PsGetProcessPeb
0x1400d7b41  nop     dword ptr [rax+rax+00h]
0x1400d7b46  test    rax, rax
0x1400d7b49  jz      loc_1400D7E73
0x1400d7b4f  mov     rcx, rsi
0x1400d7b52  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1400d7b59  nop     dword ptr [rax+rax+00h]
0x1400d7b5e  mov     rcx, rax
0x1400d7b61  call    RtlGetExpWinVer
0x1400d7b66  mov     [rbx+298h], eax
0x1400d7b6c  call    cs:__imp_W32GetUserSessionState
0x1400d7b73  nop     dword ptr [rax+rax+00h]
0x1400d7b78  mov     rsi, rax
0x1400d7b7b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d7b82  nop     dword ptr [rax+rax+00h]
0x1400d7b87  mov     rbx, rax
0x1400d7b8a  call    cs:__imp_KeEnterCriticalRegion
0x1400d7b91  nop     dword ptr [rax+rax+00h]
0x1400d7b96  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400d7b99  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400d7b9c  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400d7ba1  cmp     [rbx], r14
0x1400d7ba4  jz      loc_1400D7EF3
0x1400d7baa  call    IsThreadCrossSessionAttached
0x1400d7baf  test    eax, eax
0x1400d7bb1  jnz     loc_1400D7EEF
0x1400d7bb7  mov     rcx, [rbx]
0x1400d7bba  mov     [rcx+6ACh], dil
0x1400d7bc1  mov     [rsi+10h], rcx
0x1400d7bc5  test    rcx, rcx
0x1400d7bc8  jnz     loc_1400D7DE8
0x1400d7bce  mov     rcx, rbp; Thread
0x1400d7bd1  call    xxxCreateThreadInfo
0x1400d7bd6  mov     r14d, eax
0x1400d7bd9  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400d7bde  lea     r8, WPP_RECORDER_INITIALIZED
0x1400d7be5  lea     rsi, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x1400d7bec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7bf3  cmp     rcx, r13
0x1400d7bf6  jz      short loc_1400D7C05
0x1400d7bf8  test    dword ptr [rcx+2Ch], 2000h
0x1400d7bff  jnz     loc_1400D7EFA
0x1400d7c05  xor     dil, dil
0x1400d7c08  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400d7c0f  setnz   bl
0x1400d7c12  test    dil, dil
0x1400d7c15  jnz     short loc_1400D7C1B
0x1400d7c17  test    bl, bl
0x1400d7c19  jz      short loc_1400D7C5D
0x1400d7c1b  call    cs:__imp_W32GetUserSessionState
0x1400d7c22  nop     dword ptr [rax+rax+00h]
0x1400d7c27  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7c2e  mov     r8b, bl
0x1400d7c31  mov     [rsp+88h+var_50], rsi
0x1400d7c36  mov     dl, dil
0x1400d7c39  mov     [rsp+88h+var_58], 1Ch
0x1400d7c40  mov     r9, [rax+10E10h]
0x1400d7c47  mov     rcx, [rcx+18h]
0x1400d7c4b  mov     [rsp+88h+var_60], 0Eh
0x1400d7c53  mov     [rsp+88h+var_68], 4
0x1400d7c58  call    WPP_RECORDER_AND_TRACE_SF_
0x1400d7c5d  mov     eax, r14d
0x1400d7c60  add     rsp, 58h
0x1400d7c64  pop     r14
0x1400d7c66  pop     r13
0x1400d7c68  pop     rdi
0x1400d7c69  pop     rsi
0x1400d7c6a  pop     rbp
0x1400d7c6b  pop     rbx
0x1400d7c6c  retn
0x1400d7c6e  cmp     edx, edi
0x1400d7c70  jnz     loc_1400D7BEC
0x1400d7c76  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7c7d  cmp     rcx, r13
0x1400d7c80  jz      short loc_1400D7C8F
0x1400d7c82  test    dword ptr [rcx+2Ch], 2000h
0x1400d7c89  jnz     loc_1400D7E7F
0x1400d7c8f  xor     bl, bl
0x1400d7c91  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400d7c98  setnz   sil
0x1400d7c9c  test    bl, bl
0x1400d7c9e  jz      loc_1400D7DC7
0x1400d7ca4  call    cs:__imp_W32GetUserSessionState
0x1400d7cab  nop     dword ptr [rax+rax+00h]
0x1400d7cb0  lea     rcx, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x1400d7cb7  mov     r8b, sil
0x1400d7cba  mov     [rsp+88h+var_50], rcx
0x1400d7cbf  mov     dl, bl
0x1400d7cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7cc8  mov     r9, [rax+10E10h]
0x1400d7ccf  mov     [rsp+88h+var_58], 1Bh
0x1400d7cd6  mov     [rsp+88h+var_60], 0Eh
0x1400d7cde  mov     rcx, [rcx+18h]
0x1400d7ce2  mov     [rsp+88h+var_68], 4
0x1400d7ce7  call    WPP_RECORDER_AND_TRACE_SF_
0x1400d7cec  call    cs:__imp_W32GetUserSessionState
0x1400d7cf3  nop     dword ptr [rax+rax+00h]
0x1400d7cf8  mov     rsi, rax
0x1400d7cfb  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d7d02  nop     dword ptr [rax+rax+00h]
0x1400d7d07  mov     rbx, rax
0x1400d7d0a  call    cs:__imp_KeEnterCriticalRegion
0x1400d7d11  nop     dword ptr [rax+rax+00h]
0x1400d7d16  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400d7d19  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400d7d1c  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400d7d21  cmp     [rbx], r14
0x1400d7d24  jz      loc_1400D7E95
0x1400d7d2a  call    IsThreadCrossSessionAttached
0x1400d7d2f  test    eax, eax
0x1400d7d31  jnz     loc_1400D7E91
0x1400d7d37  mov     rcx, [rbx]
0x1400d7d3a  mov     [rcx+6ACh], dil
0x1400d7d41  mov     [rsi+10h], rcx
0x1400d7d45  test    rcx, rcx
0x1400d7d48  jnz     loc_1400D7E40
0x1400d7d4e  mov     rcx, rbp
0x1400d7d51  call    W32GetThreadWin32Thread
0x1400d7d56  mov     rbx, rax
0x1400d7d59  lock or [rax+208h], edi
0x1400d7d60  call    cs:__imp_W32GetUserSessionState
0x1400d7d67  nop     dword ptr [rax+rax+00h]
0x1400d7d6c  cmp     [rax+10BF4h], r14d
0x1400d7d73  jnz     loc_1400D7E25
0x1400d7d79  call    cs:__imp_W32GetUserSessionState
0x1400d7d80  nop     dword ptr [rax+rax+00h]
0x1400d7d85  mov     rcx, [rax+0DDA8h]
0x1400d7d8c  mov     rcx, [rcx+38h]; HDC
0x1400d7d90  call    GreCleanDC
0x1400d7d95  test    byte ptr [rbx+550h], 2
0x1400d7d9c  jnz     loc_1400D7E9C
0x1400d7da2  test    [rbx+550h], dil
0x1400d7da9  jnz     loc_1400D7BD9
0x1400d7daf  call    xxxDestroyThreadInfo
0x1400d7db4  jmp     loc_1400D7BD9
0x1400d7db9  test    sil, sil
0x1400d7dbc  jz      loc_1400D7ADA
0x1400d7dc2  jmp     loc_1400D7A92
0x1400d7dc7  test    sil, sil
0x1400d7dca  jnz     loc_1400D7CA4
0x1400d7dd0  jmp     loc_1400D7CEC
0x1400d7dd5  call    W32GetThreadWin32Thread
0x1400d7dda  lock bts dword ptr [rax+550h], 0
0x1400d7de3  jmp     loc_1400D7BDE
0x1400d7de8  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400d7ded  test    al, al
0x1400d7def  jz      loc_1400D7BCE
0x1400d7df5  lea     rbx, [rsi+4C40h]
0x1400d7dfc  mov     rcx, rbx
0x1400d7dff  call    DestroySharedUserCritDeferredUnlockList
0x1400d7e04  lea     rcx, [rbx+38h]
0x1400d7e08  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d7e0d  lea     rcx, [rbx+28h]
0x1400d7e11  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d7e16  jmp     loc_1400D7BCE
0x1400d7e1b  mov     eax, 0C0000001h
0x1400d7e20  jmp     loc_1400D7C60
0x1400d7e25  call    cs:__imp_W32GetUserGdiSessionState
0x1400d7e2c  nop     dword ptr [rax+rax+00h]
0x1400d7e31  cmp     [rax+20h], r14d
0x1400d7e35  jz      loc_1400D7D95
0x1400d7e3b  jmp     loc_1400D7D79
0x1400d7e40  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400d7e45  test    al, al
0x1400d7e47  jz      loc_1400D7D4E
0x1400d7e4d  lea     rbx, [rsi+4C40h]
0x1400d7e54  mov     rcx, rbx
0x1400d7e57  call    DestroySharedUserCritDeferredUnlockList
0x1400d7e5c  lea     rcx, [rbx+38h]
0x1400d7e60  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d7e65  lea     rcx, [rbx+28h]
0x1400d7e69  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d7e6e  jmp     loc_1400D7D4E
0x1400d7e73  mov     [rbx+298h], r14d
0x1400d7e7a  jmp     loc_1400D7B6C
0x1400d7e7f  cmp     byte ptr [rcx+29h], 4
0x1400d7e83  jb      loc_1400D7C8F
0x1400d7e89  mov     bl, dil
0x1400d7e8c  jmp     loc_1400D7C91
0x1400d7e91  or      dword ptr [rbx+18h], 2
0x1400d7e95  xor     ecx, ecx
0x1400d7e97  jmp     loc_1400D7D41
0x1400d7e9c  call    cs:__imp_W32GetUserGdiSessionState
0x1400d7ea3  nop     dword ptr [rax+rax+00h]
0x1400d7ea8  xor     r9d, r9d; unsigned int
0x1400d7eab  lea     rcx, [rsp+88h+var_48]; this
0x1400d7eb0  xor     edx, edx; struct _GUID *
0x1400d7eb2  mov     [rax+24h], r14d
0x1400d7eb6  lea     r8d, [r9+4Fh]; unsigned int
0x1400d7eba  mov     [rsp+88h+var_48], r14b
0x1400d7ebf  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1400d7ec4  mov     rcx, [rsp+88h+var_40]; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x1400d7ec9  call    ?DispBrokerAsyncSessionStateChanged@@YAJQEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; DispBrokerAsyncSessionStateChanged(_DXGK_DISPLAY_SCENARIO_CONTEXT * const)
0x1400d7ece  lea     rcx, [rsp+88h+var_48]; this
0x1400d7ed3  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1400d7ed8  jmp     loc_1400D7DA2
0x1400d7edd  cmp     byte ptr [rcx+29h], 4
0x1400d7ee1  jb      loc_1400D7A7D
0x1400d7ee7  mov     bl, dil
0x1400d7eea  jmp     loc_1400D7A7F
0x1400d7eef  or      dword ptr [rbx+18h], 2
0x1400d7ef3  xor     ecx, ecx
0x1400d7ef5  jmp     loc_1400D7BC1
0x1400d7efa  cmp     byte ptr [rcx+29h], 4
0x1400d7efe  jnb     loc_1400D7C08
0x1400d7f04  jmp     loc_1400D7C05
```
