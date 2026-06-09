# UserThreadCallout

- ea: `0x1400361c0`
- end: `0x140036699`
- name: `UserThreadCallout`
- size: `1241`
- prototype: `__int64 __fastcall(PETHREAD Thread, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14001bdf0`
- `0x14001c470`
- `0x140036118`
- `0x140036170`
- `0x1400361c0`
- `0x1400369ec`
- `0x140036a18`
- `0x140036aa4`
- `0x14003804c`
- `0x140072a90`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x1400b0d90`
- `0x140111998`
- `0x14013e47c`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1400362ca`
- `ntoskrnl!PsGetProcessPeb` at `0x1400362ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003631a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003649a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003631a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003649a`
- `ntoskrnl!PsGetThreadProcess` at `0x1400362af`
- `ntoskrnl!PsGetThreadProcess` at `0x1400362af`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400362e2`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400362e2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003630b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003648b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003630b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003648b`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400365b5`
- `WIN32K!W32GetUserGdiSessionState` at `0x14003662c`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400365b5`
- `WIN32K!W32GetUserGdiSessionState` at `0x14003662c`
- `WIN32K!W32GetUserSessionState` at `0x140036222`
- `WIN32K!W32GetUserSessionState` at `0x14003626a`
- `WIN32K!W32GetUserSessionState` at `0x140036283`
- `WIN32K!W32GetUserSessionState` at `0x1400362fc`
- `WIN32K!W32GetUserSessionState` at `0x1400363ab`
- `WIN32K!W32GetUserSessionState` at `0x140036434`
- `WIN32K!W32GetUserSessionState` at `0x14003647c`
- `WIN32K!W32GetUserSessionState` at `0x1400364f0`
- `WIN32K!W32GetUserSessionState` at `0x140036509`
- `WIN32K!W32GetUserSessionState` at `0x140036222`
- `WIN32K!W32GetUserSessionState` at `0x14003626a`
- `WIN32K!W32GetUserSessionState` at `0x140036283`
- `WIN32K!W32GetUserSessionState` at `0x1400362fc`
- `WIN32K!W32GetUserSessionState` at `0x1400363ab`
- `WIN32K!W32GetUserSessionState` at `0x140036434`
- `WIN32K!W32GetUserSessionState` at `0x14003647c`
- `WIN32K!W32GetUserSessionState` at `0x1400364f0`
- `WIN32K!W32GetUserSessionState` at `0x140036509`

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
  __int64 v23; // rbx
  __int64 v24; // rcx
  bool v25; // bl
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  CTouchProcessor *v30; // rcx
  bool v31; // bl
  bool v32; // si
  __int64 UserSessionState; // rax
  int v34; // r8d
  int v35; // edx
  __int64 v36; // rsi
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v38; // rcx
  __int64 ThreadWin32Thread; // rbx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rax
  _BYTE v47[8]; // [rsp+40h] [rbp-48h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v48; // [rsp+48h] [rbp-40h]

  ThreadInfo = 0;
  v3 = &WPP_RECORDER_INITIALIZED;
  v5 = 1;
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 != 1 )
      goto LABEL_19;
    v30 = WPP_GLOBAL_Control;
    v31 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v32 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v31 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, a2, &WPP_RECORDER_INITIALIZED);
      LOBYTE(v34) = v32;
      LOBYTE(v35) = v31;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v35,
        v34,
        *(_QWORD *)(UserSessionState + 69136),
        4,
        14,
        27,
        (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
    }
    v36 = W32GetUserSessionState(v30, a2, v3);
    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread();
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v36,
      (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
    if ( *(_QWORD *)CurrentThreadWin32Thread )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v38 = *(_QWORD *)CurrentThreadWin32Thread;
        *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
        goto LABEL_35;
      }
      *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
    }
    v38 = 0;
LABEL_35:
    *(_QWORD *)(v36 + 16) = v38;
    if ( v38 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext() )
    {
      DestroySharedUserCritDeferredUnlockList(v36 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v36 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v36 + 19560);
    }
    ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
    _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 1u);
    if ( !*(_DWORD *)(W32GetUserSessionState(v41, v40, v42) + 68596) || *(_DWORD *)(W32GetUserGdiSessionState() + 32) )
    {
      v46 = W32GetUserSessionState(v44, v43, v45);
      GreCleanDC(*(HDC *)(*(_QWORD *)(v46 + 56744) + 56LL));
    }
    if ( (*(_BYTE *)(ThreadWin32Thread + 1360) & 2) != 0 )
    {
      *(_DWORD *)(W32GetUserGdiSessionState() + 36) = 0;
      v47[0] = 0;
      CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v47, 0, 0x4Fu, 0);
      DispBrokerAsyncSessionStateChanged(v48);
      CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v47);
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
      (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
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
    v23 = PsGetCurrentThreadWin32Thread();
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v22,
      (struct _W32THREADNONPAGED *)v23);
    if ( *(_QWORD *)v23 )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v24 = *(_QWORD *)v23;
        *(_BYTE *)(*(_QWORD *)v23 + 1708LL) = 1;
        goto LABEL_16;
      }
      *(_DWORD *)(v23 + 24) |= 2u;
    }
    v24 = 0;
LABEL_16:
    *(_QWORD *)(v22 + 16) = v24;
    if ( v24 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext() )
    {
      DestroySharedUserCritDeferredUnlockList(v22 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v22 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v22 + 19560);
    }
    ThreadInfo = xxxCreateThreadInfo(Thread);
LABEL_18:
    UserSessionSwitchLeaveCritWithNonPaged();
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
  v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = W32GetUserSessionState(WPP_GLOBAL_Control, a2, &WPP_RECORDER_INITIALIZED);
    LOBYTE(v27) = v25;
    LOBYTE(v28) = v5;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v28,
      v27,
      *(_QWORD *)(v26 + 69136),
      4,
      14,
      28,
      (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
  }
  return ThreadInfo;
}

```

## disassembly

```asm
0x1400361c0  push    rbx
0x1400361c2  push    rbp
0x1400361c3  push    rsi
0x1400361c4  push    rdi
0x1400361c5  push    r13
0x1400361c7  push    r14
0x1400361c9  sub     rsp, 58h
0x1400361cd  xor     r14d, r14d
0x1400361d0  lea     r13, WPP_GLOBAL_Control
0x1400361d7  lea     r8, WPP_RECORDER_INITIALIZED
0x1400361de  mov     rbp, rcx
0x1400361e1  lea     rsi, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x1400361e8  lea     edi, [r14+1]
0x1400361ec  test    edx, edx
0x1400361ee  jnz     loc_1400363FE
0x1400361f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400361fb  cmp     rcx, r13
0x1400361fe  jz      short loc_14003620D
0x140036200  test    dword ptr [rcx+2Ch], 2000h
0x140036207  jnz     loc_14003666D
0x14003620d  xor     bl, bl
0x14003620f  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140036216  setnz   sil
0x14003621a  test    bl, bl
0x14003621c  jz      loc_140036549
0x140036222  call    cs:__imp_W32GetUserSessionState
0x140036229  nop     dword ptr [rax+rax+00h]
0x14003622e  lea     rcx, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x140036235  mov     r8b, sil
0x140036238  mov     [rsp+88h+var_50], rcx
0x14003623d  mov     dl, bl
0x14003623f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036246  mov     r9, [rax+10E10h]
0x14003624d  mov     [rsp+88h+var_58], 1Ah
0x140036254  mov     [rsp+88h+var_60], 0Eh
0x14003625c  mov     rcx, [rcx+18h]
0x140036260  mov     [rsp+88h+var_68], 4
0x140036265  call    WPP_RECORDER_AND_TRACE_SF_
0x14003626a  call    cs:__imp_W32GetUserSessionState
0x140036271  nop     dword ptr [rax+rax+00h]
0x140036276  cmp     [rax+0A7Ch], r14d
0x14003627d  jnz     loc_1400365AB
0x140036283  call    cs:__imp_W32GetUserSessionState
0x14003628a  nop     dword ptr [rax+rax+00h]
0x14003628f  mov     rcx, rbp
0x140036292  cmp     [rax+10B28h], r14d
0x140036299  jz      loc_140036565
0x14003629f  call    W32GetThreadWin32Thread
0x1400362a4  mov     rbx, rax
0x1400362a7  test    rax, rax
0x1400362aa  jz      short loc_1400362FC
0x1400362ac  mov     rcx, rbp; Thread
0x1400362af  call    cs:__imp_PsGetThreadProcess
0x1400362b6  nop     dword ptr [rax+rax+00h]
0x1400362bb  mov     rsi, rax
0x1400362be  test    rax, rax
0x1400362c1  jz      loc_140036603
0x1400362c7  mov     rcx, rax
0x1400362ca  call    cs:__imp_PsGetProcessPeb
0x1400362d1  nop     dword ptr [rax+rax+00h]
0x1400362d6  test    rax, rax
0x1400362d9  jz      loc_140036603
0x1400362df  mov     rcx, rsi
0x1400362e2  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1400362e9  nop     dword ptr [rax+rax+00h]
0x1400362ee  mov     rcx, rax
0x1400362f1  call    RtlGetExpWinVer
0x1400362f6  mov     [rbx+298h], eax
0x1400362fc  call    cs:__imp_W32GetUserSessionState
0x140036303  nop     dword ptr [rax+rax+00h]
0x140036308  mov     rsi, rax
0x14003630b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140036312  nop     dword ptr [rax+rax+00h]
0x140036317  mov     rbx, rax
0x14003631a  call    cs:__imp_KeEnterCriticalRegion
0x140036321  nop     dword ptr [rax+rax+00h]
0x140036326  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x140036329  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14003632c  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140036331  cmp     [rbx], r14
0x140036334  jz      loc_140036683
0x14003633a  call    IsThreadCrossSessionAttached
0x14003633f  test    eax, eax
0x140036341  jnz     loc_14003667F
0x140036347  mov     rcx, [rbx]
0x14003634a  mov     [rcx+6ACh], dil
0x140036351  mov     [rsi+10h], rcx
0x140036355  test    rcx, rcx
0x140036358  jnz     loc_140036578
0x14003635e  mov     rcx, rbp; Thread
0x140036361  call    xxxCreateThreadInfo
0x140036366  mov     r14d, eax
0x140036369  call    UserSessionSwitchLeaveCritWithNonPaged
0x14003636e  lea     r8, WPP_RECORDER_INITIALIZED
0x140036375  lea     rsi, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14003637c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036383  cmp     rcx, r13
0x140036386  jz      short loc_140036395
0x140036388  test    dword ptr [rcx+2Ch], 2000h
0x14003638f  jnz     loc_14003668A
0x140036395  xor     dil, dil
0x140036398  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14003639f  setnz   bl
0x1400363a2  test    dil, dil
0x1400363a5  jnz     short loc_1400363AB
0x1400363a7  test    bl, bl
0x1400363a9  jz      short loc_1400363ED
0x1400363ab  call    cs:__imp_W32GetUserSessionState
0x1400363b2  nop     dword ptr [rax+rax+00h]
0x1400363b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363be  mov     r8b, bl
0x1400363c1  mov     [rsp+88h+var_50], rsi
0x1400363c6  mov     dl, dil
0x1400363c9  mov     [rsp+88h+var_58], 1Ch
0x1400363d0  mov     r9, [rax+10E10h]
0x1400363d7  mov     rcx, [rcx+18h]
0x1400363db  mov     [rsp+88h+var_60], 0Eh
0x1400363e3  mov     [rsp+88h+var_68], 4
0x1400363e8  call    WPP_RECORDER_AND_TRACE_SF_
0x1400363ed  mov     eax, r14d
0x1400363f0  add     rsp, 58h
0x1400363f4  pop     r14
0x1400363f6  pop     r13
0x1400363f8  pop     rdi
0x1400363f9  pop     rsi
0x1400363fa  pop     rbp
0x1400363fb  pop     rbx
0x1400363fc  retn
0x1400363fe  cmp     edx, edi
0x140036400  jnz     loc_14003637C
0x140036406  mov     rcx, cs:WPP_GLOBAL_Control
0x14003640d  cmp     rcx, r13
0x140036410  jz      short loc_14003641F
0x140036412  test    dword ptr [rcx+2Ch], 2000h
0x140036419  jnz     loc_14003660F
0x14003641f  xor     bl, bl
0x140036421  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140036428  setnz   sil
0x14003642c  test    bl, bl
0x14003642e  jz      loc_140036557
0x140036434  call    cs:__imp_W32GetUserSessionState
0x14003643b  nop     dword ptr [rax+rax+00h]
0x140036440  lea     rcx, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x140036447  mov     r8b, sil
0x14003644a  mov     [rsp+88h+var_50], rcx
0x14003644f  mov     dl, bl
0x140036451  mov     rcx, cs:WPP_GLOBAL_Control
0x140036458  mov     r9, [rax+10E10h]
0x14003645f  mov     [rsp+88h+var_58], 1Bh
0x140036466  mov     [rsp+88h+var_60], 0Eh
0x14003646e  mov     rcx, [rcx+18h]
0x140036472  mov     [rsp+88h+var_68], 4
0x140036477  call    WPP_RECORDER_AND_TRACE_SF_
0x14003647c  call    cs:__imp_W32GetUserSessionState
0x140036483  nop     dword ptr [rax+rax+00h]
0x140036488  mov     rsi, rax
0x14003648b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140036492  nop     dword ptr [rax+rax+00h]
0x140036497  mov     rbx, rax
0x14003649a  call    cs:__imp_KeEnterCriticalRegion
0x1400364a1  nop     dword ptr [rax+rax+00h]
0x1400364a6  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400364a9  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400364ac  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400364b1  cmp     [rbx], r14
0x1400364b4  jz      loc_140036625
0x1400364ba  call    IsThreadCrossSessionAttached
0x1400364bf  test    eax, eax
0x1400364c1  jnz     loc_140036621
0x1400364c7  mov     rcx, [rbx]
0x1400364ca  mov     [rcx+6ACh], dil
0x1400364d1  mov     [rsi+10h], rcx
0x1400364d5  test    rcx, rcx
0x1400364d8  jnz     loc_1400365D0
0x1400364de  mov     rcx, rbp
0x1400364e1  call    W32GetThreadWin32Thread
0x1400364e6  mov     rbx, rax
0x1400364e9  lock or [rax+208h], edi
0x1400364f0  call    cs:__imp_W32GetUserSessionState
0x1400364f7  nop     dword ptr [rax+rax+00h]
0x1400364fc  cmp     [rax+10BF4h], r14d
0x140036503  jnz     loc_1400365B5
0x140036509  call    cs:__imp_W32GetUserSessionState
0x140036510  nop     dword ptr [rax+rax+00h]
0x140036515  mov     rcx, [rax+0DDA8h]
0x14003651c  mov     rcx, [rcx+38h]; HDC
0x140036520  call    GreCleanDC
0x140036525  test    byte ptr [rbx+550h], 2
0x14003652c  jnz     loc_14003662C
0x140036532  test    [rbx+550h], dil
0x140036539  jnz     loc_140036369
0x14003653f  call    xxxDestroyThreadInfo
0x140036544  jmp     loc_140036369
0x140036549  test    sil, sil
0x14003654c  jz      loc_14003626A
0x140036552  jmp     loc_140036222
0x140036557  test    sil, sil
0x14003655a  jnz     loc_140036434
0x140036560  jmp     loc_14003647C
0x140036565  call    W32GetThreadWin32Thread
0x14003656a  lock bts dword ptr [rax+550h], 0
0x140036573  jmp     loc_14003636E
0x140036578  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x14003657d  test    al, al
0x14003657f  jz      loc_14003635E
0x140036585  lea     rbx, [rsi+4C40h]
0x14003658c  mov     rcx, rbx
0x14003658f  call    DestroySharedUserCritDeferredUnlockList
0x140036594  lea     rcx, [rbx+38h]
0x140036598  call    DestroyDeferredUnlockObjectAssignmentList
0x14003659d  lea     rcx, [rbx+28h]
0x1400365a1  call    DestroyDeferredUnlockObjectAssignmentList
0x1400365a6  jmp     loc_14003635E
0x1400365ab  mov     eax, 0C0000001h
0x1400365b0  jmp     loc_1400363F0
0x1400365b5  call    cs:__imp_W32GetUserGdiSessionState
0x1400365bc  nop     dword ptr [rax+rax+00h]
0x1400365c1  cmp     [rax+20h], r14d
0x1400365c5  jz      loc_140036525
0x1400365cb  jmp     loc_140036509
0x1400365d0  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400365d5  test    al, al
0x1400365d7  jz      loc_1400364DE
0x1400365dd  lea     rbx, [rsi+4C40h]
0x1400365e4  mov     rcx, rbx
0x1400365e7  call    DestroySharedUserCritDeferredUnlockList
0x1400365ec  lea     rcx, [rbx+38h]
0x1400365f0  call    DestroyDeferredUnlockObjectAssignmentList
0x1400365f5  lea     rcx, [rbx+28h]
0x1400365f9  call    DestroyDeferredUnlockObjectAssignmentList
0x1400365fe  jmp     loc_1400364DE
0x140036603  mov     [rbx+298h], r14d
0x14003660a  jmp     loc_1400362FC
0x14003660f  cmp     byte ptr [rcx+29h], 4
0x140036613  jb      loc_14003641F
0x140036619  mov     bl, dil
0x14003661c  jmp     loc_140036421
0x140036621  or      dword ptr [rbx+18h], 2
0x140036625  xor     ecx, ecx
0x140036627  jmp     loc_1400364D1
0x14003662c  call    cs:__imp_W32GetUserGdiSessionState
0x140036633  nop     dword ptr [rax+rax+00h]
0x140036638  xor     r9d, r9d; unsigned int
0x14003663b  lea     rcx, [rsp+88h+var_48]; this
0x140036640  xor     edx, edx; struct _GUID *
0x140036642  mov     [rax+24h], r14d
0x140036646  lea     r8d, [r9+4Fh]; unsigned int
0x14003664a  mov     [rsp+88h+var_48], r14b
0x14003664f  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x140036654  mov     rcx, [rsp+88h+var_40]; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x140036659  call    ?DispBrokerAsyncSessionStateChanged@@YAJQEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; DispBrokerAsyncSessionStateChanged(_DXGK_DISPLAY_SCENARIO_CONTEXT * const)
0x14003665e  lea     rcx, [rsp+88h+var_48]; this
0x140036663  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x140036668  jmp     loc_140036532
0x14003666d  cmp     byte ptr [rcx+29h], 4
0x140036671  jb      loc_14003620D
0x140036677  mov     bl, dil
0x14003667a  jmp     loc_14003620F
0x14003667f  or      dword ptr [rbx+18h], 2
0x140036683  xor     ecx, ecx
0x140036685  jmp     loc_140036351
0x14003668a  cmp     byte ptr [rcx+29h], 4
0x14003668e  jnb     loc_140036398
0x140036694  jmp     loc_140036395
```
