# xxxSetForegroundThreadWithWindowHint(tagTHREADINFO *,tagWND *)

- ea: `0x1401eb600`
- end: `0x1401ebcd0`
- name: `?xxxSetForegroundThreadWithWindowHint@@YAXPEAUtagTHREADINFO@@PEAUtagWND@@@Z`
- size: `1744`
- prototype: `void __fastcall(struct tagTHREADINFO *, struct tagWND *)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1401aa130`
- `0x1401eb09c`
- `0x14026e0fc`
- `0x1402a93e0`

## callees

- `0x14001cb40`
- `0x140077ab8`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400eb064`
- `0x1401bac94`
- `0x1401eb600`
- `0x140265780`
- `0x14027dc6c`
- `0x1402b0c1c`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1401eb796`
- `ntoskrnl!PsGetThreadId` at `0x1401eb7d5`
- `ntoskrnl!PsGetThreadId` at `0x1401eb90b`
- `ntoskrnl!PsGetThreadId` at `0x1401eb94a`
- `ntoskrnl!PsGetThreadId` at `0x1401eba76`
- `ntoskrnl!PsGetThreadId` at `0x1401eb796`
- `ntoskrnl!PsGetThreadId` at `0x1401eb7d5`
- `ntoskrnl!PsGetThreadId` at `0x1401eb90b`
- `ntoskrnl!PsGetThreadId` at `0x1401eb94a`
- `ntoskrnl!PsGetThreadId` at `0x1401eba76`
- `win32kbase!xxxChangeForegroundKeyboardTable` at `0x1401ebc52`
- `win32kbase!xxxChangeForegroundKeyboardTable` at `0x1401ebc52`
- `win32kbase!DisableDelegation` at `0x1401eb8ad`
- `win32kbase!DisableDelegation` at `0x1401eb8ad`
- `win32kbase!GetKeyboardDelegationTargetQ` at `0x1401eb889`
- `win32kbase!GetKeyboardDelegationTargetQ` at `0x1401eb889`
- `win32kbase!EtwTraceFocusChange` at `0x1401eb7ea`
- `win32kbase!EtwTraceFocusChange` at `0x1401eb7ea`
- `win32kbase!CitProcessForegroundChange` at `0x1401eb6f6`
- `win32kbase!CitProcessForegroundChange` at `0x1401eb6f6`
- `win32kbase!EtwTraceFocusedProcessChange` at `0x1401eb6d1`
- `win32kbase!EtwTraceFocusedProcessChange` at `0x1401eb6d1`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x1401eb715`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x1401eb74e`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x1401eb715`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x1401eb74e`
- `win32kbase!SendMessageTo` at `0x1401ebaa7`
- `win32kbase!SendMessageTo` at `0x1401ebaa7`
- `WIN32K!W32GetUserSessionState` at `0x1401eb62c`
- `WIN32K!W32GetUserSessionState` at `0x1401eb64d`
- `WIN32K!W32GetUserSessionState` at `0x1401eb662`
- `WIN32K!W32GetUserSessionState` at `0x1401eb698`
- `WIN32K!W32GetUserSessionState` at `0x1401eb6ad`
- `WIN32K!W32GetUserSessionState` at `0x1401eb6dd`
- `WIN32K!W32GetUserSessionState` at `0x1401eb721`
- `WIN32K!W32GetUserSessionState` at `0x1401eb736`
- `WIN32K!W32GetUserSessionState` at `0x1401eb75a`
- `WIN32K!W32GetUserSessionState` at `0x1401eb76f`
- `WIN32K!W32GetUserSessionState` at `0x1401eb7aa`
- `WIN32K!W32GetUserSessionState` at `0x1401eb7bf`
- `WIN32K!W32GetUserSessionState` at `0x1401eb7f6`
- `WIN32K!W32GetUserSessionState` at `0x1401eb810`
- `WIN32K!W32GetUserSessionState` at `0x1401eb854`
- `WIN32K!W32GetUserSessionState` at `0x1401eb874`
- `WIN32K!W32GetUserSessionState` at `0x1401eb91f`
- `WIN32K!W32GetUserSessionState` at `0x1401eb934`
- `WIN32K!W32GetUserSessionState` at `0x1401eb95e`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9af`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9c7`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9e9`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9fd`
- `WIN32K!W32GetUserSessionState` at `0x1401eba2a`
- `WIN32K!W32GetUserSessionState` at `0x1401eba3f`
- `WIN32K!W32GetUserSessionState` at `0x1401eba60`
- `WIN32K!W32GetUserSessionState` at `0x1401ebabc`
- `WIN32K!W32GetUserSessionState` at `0x1401ebb3c`
- `WIN32K!W32GetUserSessionState` at `0x1401ebb8a`
- `WIN32K!W32GetUserSessionState` at `0x1401ebba3`
- `WIN32K!W32GetUserSessionState` at `0x1401ebbc3`
- `WIN32K!W32GetUserSessionState` at `0x1401ebbd9`
- `WIN32K!W32GetUserSessionState` at `0x1401ebbee`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc01`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc32`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc71`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc8e`
- `WIN32K!W32GetUserSessionState` at `0x1401eb62c`
- `WIN32K!W32GetUserSessionState` at `0x1401eb64d`
- `WIN32K!W32GetUserSessionState` at `0x1401eb662`
- `WIN32K!W32GetUserSessionState` at `0x1401eb698`
- `WIN32K!W32GetUserSessionState` at `0x1401eb6ad`
- `WIN32K!W32GetUserSessionState` at `0x1401eb6dd`
- `WIN32K!W32GetUserSessionState` at `0x1401eb721`
- `WIN32K!W32GetUserSessionState` at `0x1401eb736`
- `WIN32K!W32GetUserSessionState` at `0x1401eb75a`
- `WIN32K!W32GetUserSessionState` at `0x1401eb76f`
- `WIN32K!W32GetUserSessionState` at `0x1401eb7aa`
- `WIN32K!W32GetUserSessionState` at `0x1401eb7bf`
- `WIN32K!W32GetUserSessionState` at `0x1401eb7f6`
- `WIN32K!W32GetUserSessionState` at `0x1401eb810`
- `WIN32K!W32GetUserSessionState` at `0x1401eb854`
- `WIN32K!W32GetUserSessionState` at `0x1401eb874`
- `WIN32K!W32GetUserSessionState` at `0x1401eb91f`
- `WIN32K!W32GetUserSessionState` at `0x1401eb934`
- `WIN32K!W32GetUserSessionState` at `0x1401eb95e`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9af`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9c7`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9e9`
- `WIN32K!W32GetUserSessionState` at `0x1401eb9fd`
- `WIN32K!W32GetUserSessionState` at `0x1401eba2a`
- `WIN32K!W32GetUserSessionState` at `0x1401eba3f`
- `WIN32K!W32GetUserSessionState` at `0x1401eba60`
- `WIN32K!W32GetUserSessionState` at `0x1401ebabc`
- `WIN32K!W32GetUserSessionState` at `0x1401ebb3c`
- `WIN32K!W32GetUserSessionState` at `0x1401ebb8a`
- `WIN32K!W32GetUserSessionState` at `0x1401ebba3`
- `WIN32K!W32GetUserSessionState` at `0x1401ebbc3`
- `WIN32K!W32GetUserSessionState` at `0x1401ebbd9`
- `WIN32K!W32GetUserSessionState` at `0x1401ebbee`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc01`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc32`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc71`
- `WIN32K!W32GetUserSessionState` at `0x1401ebc8e`

## pseudocode

```c
void __fastcall xxxSetForegroundThreadWithWindowHint(struct tagTHREADINFO *a1, struct tagWND *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 UserSessionState; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r12
  unsigned int ThreadId; // ebx
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  __int64 KeyboardDelegationTargetQ; // rax
  __int64 v22; // rcx
  struct MOVESIZEDATA *v23; // rcx
  char v24; // bl
  bool v25; // r14
  char v26; // bp
  __int64 v27; // rcx
  __int64 v28; // rax
  char v29; // si
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  struct MOVESIZEDATA *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rsi
  __int64 ShellSpecialWindow; // rax
  char v42; // bl
  bool v43; // di
  __int64 v44; // rax
  int v45; // r8d
  int v46; // edx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rbx
  __int64 v52; // rcx
  struct tagTHREADINFO *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rax
  ULONG_PTR BugCheckParameter3[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v61; // [rsp+60h] [rbp-58h]

  if ( a1 == *(struct tagTHREADINFO **)(W32GetUserSessionState(a1) + 18984) )
    return;
  if ( !a1 )
  {
    v5 = 0;
    goto LABEL_7;
  }
  if ( !*(_QWORD *)(W32GetUserSessionState(v4) + 18984)
    || *((_QWORD *)a1 + 57) != *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v4) + 18984) + 456LL) )
  {
    v5 = *(_DWORD *)(*((_QWORD *)a1 + 57) + 56LL);
LABEL_7:
    if ( *(_QWORD *)(W32GetUserSessionState(v4) + 18984) )
      v7 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v6) + 18984) + 456LL) + 56LL);
    else
      v7 = 0;
    EtwTraceFocusedProcessChange(v7, v5);
    UserSessionState = W32GetUserSessionState(v8);
    CitProcessForegroundChange(a1, a2, *(_QWORD *)(UserSessionState + 18984));
    if ( a1 )
      ForegroundBoost::SetForegroundPriority(a1, 1, 8);
    if ( *(_QWORD *)(W32GetUserSessionState(v10) + 18984) )
    {
      v11 = W32GetUserSessionState(v4);
      ForegroundBoost::SetForegroundPriority(*(_QWORD *)(v11 + 18984), 0, 8);
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v4) + 18984) )
  {
    v12 = *(_QWORD *)(W32GetUserSessionState(v12) + 18984);
    v13 = *(_QWORD *)(v12 + 472);
  }
  else
  {
    v13 = 0;
  }
  if ( a1 )
    ThreadId = (unsigned int)PsGetThreadId(*(PETHREAD *)a1);
  else
    ThreadId = 0;
  if ( *(_QWORD *)(W32GetUserSessionState(v12) + 18984) )
  {
    v16 = W32GetUserSessionState(v15);
    v17 = (unsigned int)PsGetThreadId(**(PETHREAD **)(v16 + 18984));
  }
  else
  {
    v17 = 0;
  }
  EtwTraceFocusChange(v17, ThreadId);
  if ( *(_QWORD *)(W32GetUserSessionState(v18) + 18984) )
  {
    if ( !a1 || (v19 = *(_QWORD *)(W32GetUserSessionState(v19) + 18984), *(_QWORD *)(v19 + 456) != *((_QWORD *)a1 + 57)) )
    {
      v20 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v19 = *(_QWORD *)(W32GetUserSessionState(0xFFFFF78000000004uLL) + 18984);
      *(_DWORD *)(*(_QWORD *)(v19 + 456) + 1068LL) = v20;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v19) + 18984) )
  {
    KeyboardDelegationTargetQ = GetKeyboardDelegationTargetQ();
    if ( KeyboardDelegationTargetQ )
    {
      v22 = *(_QWORD *)(KeyboardDelegationTargetQ + 120);
      if ( v22 )
        zzzDelegateInputFocusLostWindowEvent(v22, 14);
    }
    DisableDelegation();
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v24 = 0;
  }
  v25 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v24 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( a1 )
      v26 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)a1);
    else
      v26 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v23) + 18984) )
    {
      v28 = W32GetUserSessionState(v27);
      v29 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v28 + 18984));
    }
    else
    {
      v29 = 0;
    }
    v30 = W32GetUserSessionState(v27);
    LOBYTE(v31) = v25;
    LOBYTE(v32) = v24;
    WPP_RECORDER_AND_TRACE_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v32,
      v31,
      *(_QWORD *)(v30 + 69152),
      4,
      2,
      114,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
      v29,
      v26);
  }
  *(_QWORD *)(W32GetUserSessionState(v23) + 18984) = a1;
  if ( a1
    && (v34 = W32GetUserSessionState(v33),
        v33 = *(unsigned int *)(*((_QWORD *)a1 + 57) + 56LL),
        v33 == *(_QWORD *)(v34 + 63320)) )
  {
    v35 = W32GetUserSessionState(v33);
    *(_DWORD *)(v35 + 14652) |= 2u;
  }
  else
  {
    v36 = W32GetUserSessionState(v33);
    *(_DWORD *)(v36 + 14652) &= ~2u;
  }
  if ( !(unsigned int)IsCurrentSessionServiceSession() )
  {
    *(_OWORD *)BugCheckParameter3 = 0;
    v61 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v37) + 18984) )
    {
      LODWORD(BugCheckParameter3[0]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v38) + 18984) + 456LL)
                                                 + 56LL);
      v39 = W32GetUserSessionState(LODWORD(BugCheckParameter3[0]));
      HIDWORD(BugCheckParameter3[0]) = (unsigned int)PsGetThreadId(**(PETHREAD **)(v39 + 18984));
      if ( a2 )
        *(_QWORD *)&v61 = *(_QWORD *)a2;
      else
        *(_QWORD *)&v61 = 0;
    }
    SendMessageTo(2, BugCheckParameter3, 32);
  }
  if ( a1 )
  {
    v40 = W32GetUserSessionState(v37);
    if ( *(_DWORD *)(v40 + 13992) == 1 )
    {
      ShellSpecialWindow = ShellWindowManagement::GetShellSpecialWindow(*((_QWORD *)a1 + 61), 1);
      if ( ShellSpecialWindow )
      {
        if ( *(struct tagTHREADINFO **)(ShellSpecialWindow + 16) == a1 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
            || (v42 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
          {
            v42 = 0;
          }
          v43 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v42 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v44 = W32GetUserSessionState(WPP_GLOBAL_Control);
            LOBYTE(v45) = v43;
            LOBYTE(v46) = v42;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v46,
              v45,
              *(_QWORD *)(v44 + 69152),
              4,
              6,
              115,
              (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
          }
          *(_DWORD *)(v40 + 13992) = 2;
        }
      }
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v37) + 18984) )
  {
    v48 = *(_QWORD *)(W32GetUserSessionState(v47) + 18984);
    if ( *(_QWORD *)(v48 + 472) )
    {
      v49 = *(unsigned int *)(W32GetUserSessionState(v48) + 66792);
      if ( (v49 & 0x80u) != 0LL
        || !*(_QWORD *)(W32GetUserSessionState(v49) + 14184)
        || (v51 = *(_QWORD *)(W32GetUserSessionState(v50) + 14184),
            v51 == *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v52) + 18984) + 472LL)) )
      {
        v53 = PtiCurrent();
        Win32HM_LockIntoThread<1>(v53, v13, BugCheckParameter3);
        v55 = W32GetUserSessionState(v54);
        xxxChangeForegroundKeyboardTable(v13, *(_QWORD *)(*(_QWORD *)(v55 + 18984) + 472LL), 0);
        Win32HMThreadLockBase<tagKL,1,0>::~Win32HMThreadLockBase<tagKL,1,0>((ULONG_PTR)BugCheckParameter3);
      }
    }
  }
  if ( !(unsigned int)Feature_AsyncKeyStateRecentDown_Removal2__private_IsEnabledDeviceUsageNoInline() )
  {
    v57 = W32GetUserSessionState(v56);
    *(_OWORD *)(v57 + 14408) = 0;
    *(_OWORD *)(v57 + 14424) = 0;
    v59 = W32GetUserSessionState(v58);
    ++*(_DWORD *)(*(_QWORD *)(v59 + 19704) + 6988LL);
  }
}

```

## disassembly

```asm
0x1401eb600  mov     [rsp+arg_10], rbx
0x1401eb605  push    rbp
0x1401eb606  push    rsi
0x1401eb607  push    rdi
0x1401eb608  push    r12
0x1401eb60a  push    r13
0x1401eb60c  push    r14
0x1401eb60e  push    r15
0x1401eb610  sub     rsp, 80h
0x1401eb617  mov     rax, cs:__security_cookie
0x1401eb61e  xor     rax, rsp
0x1401eb621  mov     [rsp+0B8h+var_48], rax
0x1401eb626  mov     r15, rdx
0x1401eb629  mov     rdi, rcx
0x1401eb62c  call    cs:__imp_W32GetUserSessionState
0x1401eb633  nop     dword ptr [rax+rax+00h]
0x1401eb638  cmp     rdi, [rax+4A28h]
0x1401eb63f  jz      loc_1401EBCA7
0x1401eb645  xor     r13d, r13d
0x1401eb648  test    rdi, rdi
0x1401eb64b  jz      short loc_1401EB695
0x1401eb64d  call    cs:__imp_W32GetUserSessionState
0x1401eb654  nop     dword ptr [rax+rax+00h]
0x1401eb659  cmp     [rax+4A28h], r13
0x1401eb660  jz      short loc_1401EB689
0x1401eb662  call    cs:__imp_W32GetUserSessionState
0x1401eb669  nop     dword ptr [rax+rax+00h]
0x1401eb66e  mov     rax, [rax+4A28h]
0x1401eb675  mov     rax, [rax+1C8h]
0x1401eb67c  cmp     [rdi+1C8h], rax
0x1401eb683  jz      loc_1401EB75A
0x1401eb689  mov     rax, [rdi+1C8h]
0x1401eb690  mov     ebx, [rax+38h]
0x1401eb693  jmp     short loc_1401EB698
0x1401eb695  mov     ebx, r13d
0x1401eb698  call    cs:__imp_W32GetUserSessionState
0x1401eb69f  nop     dword ptr [rax+rax+00h]
0x1401eb6a4  cmp     [rax+4A28h], r13
0x1401eb6ab  jz      short loc_1401EB6CC
0x1401eb6ad  call    cs:__imp_W32GetUserSessionState
0x1401eb6b4  nop     dword ptr [rax+rax+00h]
0x1401eb6b9  mov     rcx, [rax+4A28h]
0x1401eb6c0  mov     rax, [rcx+1C8h]
0x1401eb6c7  mov     ecx, [rax+38h]
0x1401eb6ca  jmp     short loc_1401EB6CF
0x1401eb6cc  mov     ecx, r13d
0x1401eb6cf  mov     edx, ebx
0x1401eb6d1  call    cs:__imp_EtwTraceFocusedProcessChange
0x1401eb6d8  nop     dword ptr [rax+rax+00h]
0x1401eb6dd  call    cs:__imp_W32GetUserSessionState
0x1401eb6e4  nop     dword ptr [rax+rax+00h]
0x1401eb6e9  mov     rdx, r15
0x1401eb6ec  mov     rcx, rdi
0x1401eb6ef  mov     r8, [rax+4A28h]
0x1401eb6f6  call    cs:__imp_CitProcessForegroundChange
0x1401eb6fd  nop     dword ptr [rax+rax+00h]
0x1401eb702  mov     ebx, 8
0x1401eb707  test    rdi, rdi
0x1401eb70a  jz      short loc_1401EB721
0x1401eb70c  mov     r8d, ebx
0x1401eb70f  lea     edx, [rbx-7]
0x1401eb712  mov     rcx, rdi
0x1401eb715  call    cs:__imp_?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z; ForegroundBoost::SetForegroundPriority(tagTHREADINFO const *,ForegroundBoost::ForegroundPriorityClass,ForegroundBoost::ForegroundBoostSource)
0x1401eb71c  nop     dword ptr [rax+rax+00h]
0x1401eb721  call    cs:__imp_W32GetUserSessionState
0x1401eb728  nop     dword ptr [rax+rax+00h]
0x1401eb72d  cmp     [rax+4A28h], r13
0x1401eb734  jz      short loc_1401EB75A
0x1401eb736  call    cs:__imp_W32GetUserSessionState
0x1401eb73d  nop     dword ptr [rax+rax+00h]
0x1401eb742  mov     r8d, ebx
0x1401eb745  xor     edx, edx
0x1401eb747  mov     rcx, [rax+4A28h]
0x1401eb74e  call    cs:__imp_?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z; ForegroundBoost::SetForegroundPriority(tagTHREADINFO const *,ForegroundBoost::ForegroundPriorityClass,ForegroundBoost::ForegroundBoostSource)
0x1401eb755  nop     dword ptr [rax+rax+00h]
0x1401eb75a  call    cs:__imp_W32GetUserSessionState
0x1401eb761  nop     dword ptr [rax+rax+00h]
0x1401eb766  cmp     [rax+4A28h], r13
0x1401eb76d  jz      short loc_1401EB78B
0x1401eb76f  call    cs:__imp_W32GetUserSessionState
0x1401eb776  nop     dword ptr [rax+rax+00h]
0x1401eb77b  mov     rcx, [rax+4A28h]
0x1401eb782  mov     r12, [rcx+1D8h]
0x1401eb789  jmp     short loc_1401EB78E
0x1401eb78b  mov     r12, r13
0x1401eb78e  test    rdi, rdi
0x1401eb791  jz      short loc_1401EB7A7
0x1401eb793  mov     rcx, [rdi]; Thread
0x1401eb796  call    cs:__imp_PsGetThreadId
0x1401eb79d  nop     dword ptr [rax+rax+00h]
0x1401eb7a2  mov     rbx, rax
0x1401eb7a5  jmp     short loc_1401EB7AA
0x1401eb7a7  mov     ebx, r13d
0x1401eb7aa  call    cs:__imp_W32GetUserSessionState
0x1401eb7b1  nop     dword ptr [rax+rax+00h]
0x1401eb7b6  cmp     [rax+4A28h], r13
0x1401eb7bd  jz      short loc_1401EB7E3
0x1401eb7bf  call    cs:__imp_W32GetUserSessionState
0x1401eb7c6  nop     dword ptr [rax+rax+00h]
0x1401eb7cb  mov     rcx, [rax+4A28h]
0x1401eb7d2  mov     rcx, [rcx]; Thread
0x1401eb7d5  call    cs:__imp_PsGetThreadId
0x1401eb7dc  nop     dword ptr [rax+rax+00h]
0x1401eb7e1  jmp     short loc_1401EB7E6
0x1401eb7e3  mov     eax, r13d
0x1401eb7e6  mov     edx, ebx
0x1401eb7e8  mov     ecx, eax
0x1401eb7ea  call    cs:__imp_EtwTraceFocusChange
0x1401eb7f1  nop     dword ptr [rax+rax+00h]
0x1401eb7f6  call    cs:__imp_W32GetUserSessionState
0x1401eb7fd  nop     dword ptr [rax+rax+00h]
0x1401eb802  cmp     [rax+4A28h], r13
0x1401eb809  jz      short loc_1401EB874
0x1401eb80b  test    rdi, rdi
0x1401eb80e  jz      short loc_1401EB833
0x1401eb810  call    cs:__imp_W32GetUserSessionState
0x1401eb817  nop     dword ptr [rax+rax+00h]
0x1401eb81c  mov     rcx, [rax+4A28h]
0x1401eb823  mov     rax, [rcx+1C8h]
0x1401eb82a  cmp     rax, [rdi+1C8h]
0x1401eb831  jz      short loc_1401EB874
0x1401eb833  mov     rcx, 0FFFFF78000000004h
0x1401eb83d  mov     rax, 0FFFFF78000000320h
0x1401eb847  mov     rax, [rax]
0x1401eb84a  mov     ebx, [rcx]
0x1401eb84c  imul    rbx, rax
0x1401eb850  shr     rbx, 18h
0x1401eb854  call    cs:__imp_W32GetUserSessionState
0x1401eb85b  nop     dword ptr [rax+rax+00h]
0x1401eb860  mov     rcx, [rax+4A28h]
0x1401eb867  mov     rax, [rcx+1C8h]
0x1401eb86e  mov     [rax+42Ch], ebx
0x1401eb874  call    cs:__imp_W32GetUserSessionState
0x1401eb87b  nop     dword ptr [rax+rax+00h]
0x1401eb880  cmp     [rax+4A28h], r13
0x1401eb887  jz      short loc_1401EB8B9
0x1401eb889  call    cs:__imp_GetKeyboardDelegationTargetQ
0x1401eb890  nop     dword ptr [rax+rax+00h]
0x1401eb895  test    rax, rax
0x1401eb898  jz      short loc_1401EB8AD
0x1401eb89a  mov     rcx, [rax+78h]
0x1401eb89e  test    rcx, rcx
0x1401eb8a1  jz      short loc_1401EB8AD
0x1401eb8a3  mov     edx, 0Eh
0x1401eb8a8  call    zzzDelegateInputFocusLostWindowEvent
0x1401eb8ad  call    cs:__imp_DisableDelegation
0x1401eb8b4  nop     dword ptr [rax+rax+00h]
0x1401eb8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1401eb8c0  lea     rax, WPP_GLOBAL_Control
0x1401eb8c7  mov     ebp, 2
0x1401eb8cc  cmp     rcx, rax
0x1401eb8cf  jz      short loc_1401EB8E1
0x1401eb8d1  mov     eax, [rcx+2Ch]
0x1401eb8d4  test    bpl, al
0x1401eb8d7  jz      short loc_1401EB8E1
0x1401eb8d9  cmp     byte ptr [rcx+29h], 4
0x1401eb8dd  mov     bl, 1
0x1401eb8df  jnb     short loc_1401EB8E4
0x1401eb8e1  mov     bl, r13b
0x1401eb8e4  lea     rax, WPP_RECORDER_INITIALIZED
0x1401eb8eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401eb8f2  setnz   r14b
0x1401eb8f6  test    bl, bl
0x1401eb8f8  jnz     short loc_1401EB903
0x1401eb8fa  test    r14b, r14b
0x1401eb8fd  jz      loc_1401EB9AF
0x1401eb903  test    rdi, rdi
0x1401eb906  jz      short loc_1401EB91C
0x1401eb908  mov     rcx, [rdi]; Thread
0x1401eb90b  call    cs:__imp_PsGetThreadId
0x1401eb912  nop     dword ptr [rax+rax+00h]
0x1401eb917  mov     rbp, rax
0x1401eb91a  jmp     short loc_1401EB91F
0x1401eb91c  mov     ebp, r13d
0x1401eb91f  call    cs:__imp_W32GetUserSessionState
0x1401eb926  nop     dword ptr [rax+rax+00h]
0x1401eb92b  cmp     [rax+4A28h], r13
0x1401eb932  jz      short loc_1401EB95B
0x1401eb934  call    cs:__imp_W32GetUserSessionState
0x1401eb93b  nop     dword ptr [rax+rax+00h]
0x1401eb940  mov     rcx, [rax+4A28h]
0x1401eb947  mov     rcx, [rcx]; Thread
0x1401eb94a  call    cs:__imp_PsGetThreadId
0x1401eb951  nop     dword ptr [rax+rax+00h]
0x1401eb956  mov     rsi, rax
0x1401eb959  jmp     short loc_1401EB95E
0x1401eb95b  mov     esi, r13d
0x1401eb95e  call    cs:__imp_W32GetUserSessionState
0x1401eb965  nop     dword ptr [rax+rax+00h]
0x1401eb96a  mov     [rsp+0B8h+var_70], ebp
0x1401eb96e  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1401eb975  mov     [rsp+0B8h+var_78], esi
0x1401eb979  mov     ebp, 2
0x1401eb97e  mov     [rsp+0B8h+var_80], rcx
0x1401eb983  mov     r8b, r14b
0x1401eb986  mov     rcx, cs:WPP_GLOBAL_Control
0x1401eb98d  mov     dl, bl
0x1401eb98f  mov     r9, [rax+10E20h]
0x1401eb996  mov     [rsp+0B8h+var_88], 72h ; 'r'
0x1401eb99d  mov     [rsp+0B8h+var_90], ebp
0x1401eb9a1  mov     rcx, [rcx+18h]
0x1401eb9a5  mov     [rsp+0B8h+var_98], 4
0x1401eb9aa  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1401eb9af  call    cs:__imp_W32GetUserSessionState
0x1401eb9b6  nop     dword ptr [rax+rax+00h]
0x1401eb9bb  mov     [rax+4A28h], rdi
0x1401eb9c2  test    rdi, rdi
0x1401eb9c5  jz      short loc_1401EB9FD
0x1401eb9c7  call    cs:__imp_W32GetUserSessionState
0x1401eb9ce  nop     dword ptr [rax+rax+00h]
0x1401eb9d3  mov     rdx, [rax+0F758h]
0x1401eb9da  mov     rax, [rdi+1C8h]
0x1401eb9e1  mov     ecx, [rax+38h]
0x1401eb9e4  cmp     rcx, rdx
0x1401eb9e7  jnz     short loc_1401EB9FD
0x1401eb9e9  call    cs:__imp_W32GetUserSessionState
0x1401eb9f0  nop     dword ptr [rax+rax+00h]
0x1401eb9f5  or      [rax+393Ch], ebp
0x1401eb9fb  jmp     short loc_1401EBA10
0x1401eb9fd  call    cs:__imp_W32GetUserSessionState
0x1401eba04  nop     dword ptr [rax+rax+00h]
0x1401eba09  and     dword ptr [rax+393Ch], 0FFFFFFFDh
0x1401eba10  call    IsCurrentSessionServiceSession
0x1401eba15  test    eax, eax
0x1401eba17  jnz     loc_1401EBAB3
0x1401eba1d  xorps   xmm0, xmm0
0x1401eba20  movups  xmmword ptr [rsp+0B8h+BugCheckParameter3], xmm0
0x1401eba25  movups  [rsp+0B8h+var_58], xmm0
0x1401eba2a  call    cs:__imp_W32GetUserSessionState
0x1401eba31  nop     dword ptr [rax+rax+00h]
0x1401eba36  cmp     [rax+4A28h], r13
0x1401eba3d  jz      short loc_1401EBA9A
0x1401eba3f  call    cs:__imp_W32GetUserSessionState
0x1401eba46  nop     dword ptr [rax+rax+00h]
0x1401eba4b  mov     rcx, [rax+4A28h]
0x1401eba52  mov     rax, [rcx+1C8h]
0x1401eba59  mov     ecx, [rax+38h]
0x1401eba5c  mov     dword ptr [rsp+0B8h+BugCheckParameter3], ecx
0x1401eba60  call    cs:__imp_W32GetUserSessionState
0x1401eba67  nop     dword ptr [rax+rax+00h]
0x1401eba6c  mov     rcx, [rax+4A28h]
0x1401eba73  mov     rcx, [rcx]; Thread
0x1401eba76  call    cs:__imp_PsGetThreadId
0x1401eba7d  nop     dword ptr [rax+rax+00h]
0x1401eba82  mov     dword ptr [rsp+0B8h+BugCheckParameter3+4], eax
0x1401eba86  test    r15, r15
0x1401eba89  jnz     short loc_1401EBA92
0x1401eba8b  mov     qword ptr [rsp+0B8h+var_58], r13
0x1401eba90  jmp     short loc_1401EBA9A
0x1401eba92  mov     rax, [r15]
0x1401eba95  mov     qword ptr [rsp+0B8h+var_58], rax
0x1401eba9a  mov     r8d, 20h ; ' '
0x1401ebaa0  lea     rdx, [rsp+0B8h+BugCheckParameter3]
0x1401ebaa5  mov     ecx, ebp
0x1401ebaa7  call    cs:__imp_SendMessageTo
0x1401ebaae  nop     dword ptr [rax+rax+00h]
0x1401ebab3  test    rdi, rdi
0x1401ebab6  jz      loc_1401EBB8A
0x1401ebabc  call    cs:__imp_W32GetUserSessionState
0x1401ebac3  nop     dword ptr [rax+rax+00h]
0x1401ebac8  mov     rsi, rax
0x1401ebacb  cmp     dword ptr [rax+36A8h], 1
0x1401ebad2  jnz     loc_1401EBB8A
0x1401ebad8  mov     rcx, [rdi+1E8h]
0x1401ebadf  mov     edx, 1
0x1401ebae4  call    ?GetShellSpecialWindow@ShellWindowManagement@@YAPEAUtagWND@@PEAUtagDESKTOP@@W4SHELL_SPECIAL_WINDOW@@@Z; ShellWindowManagement::GetShellSpecialWindow(tagDESKTOP *,SHELL_SPECIAL_WINDOW)
0x1401ebae9  test    rax, rax
0x1401ebaec  jz      loc_1401EBB8A
0x1401ebaf2  cmp     [rax+10h], rdi
0x1401ebaf6  jnz     loc_1401EBB8A
0x1401ebafc  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ebb03  lea     rax, WPP_GLOBAL_Control
0x1401ebb0a  cmp     rcx, rax
0x1401ebb0d  jz      short loc_1401EBB1E
0x1401ebb0f  mov     eax, [rcx+2Ch]
0x1401ebb12  test    al, 20h
0x1401ebb14  jz      short loc_1401EBB1E
0x1401ebb16  cmp     byte ptr [rcx+29h], 4
0x1401ebb1a  mov     bl, 1
0x1401ebb1c  jnb     short loc_1401EBB21
0x1401ebb1e  mov     bl, r13b
0x1401ebb21  lea     rax, WPP_RECORDER_INITIALIZED
0x1401ebb28  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401ebb2f  setnz   dil
0x1401ebb33  test    bl, bl
0x1401ebb35  jnz     short loc_1401EBB3C
0x1401ebb37  test    dil, dil
0x1401ebb3a  jz      short loc_1401EBB84
0x1401ebb3c  call    cs:__imp_W32GetUserSessionState
0x1401ebb43  nop     dword ptr [rax+rax+00h]
0x1401ebb48  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1401ebb4f  mov     r8b, dil
0x1401ebb52  mov     [rsp+0B8h+var_80], rcx
0x1401ebb57  mov     dl, bl
0x1401ebb59  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ebb60  mov     r9, [rax+10E20h]
0x1401ebb67  mov     [rsp+0B8h+var_88], 73h ; 's'
0x1401ebb6e  mov     [rsp+0B8h+var_90], 6
0x1401ebb76  mov     rcx, [rcx+18h]
0x1401ebb7a  mov     [rsp+0B8h+var_98], 4
  ... truncated ...
```
