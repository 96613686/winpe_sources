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
void __fastcall xxxSetForegroundThreadWithWindowHint(
        struct tagTHREADINFO *a1,
        struct tagWND *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 UserSessionState; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r12
  unsigned int ThreadId; // ebx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rax
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  unsigned __int64 v46; // rbx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 KeyboardDelegationTargetQ; // rax
  __int64 v51; // rcx
  struct MOVESIZEDATA *v52; // rcx
  char v53; // bl
  bool v54; // r14
  char v55; // bp
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // rax
  char v61; // si
  __int64 v62; // rax
  int v63; // r8d
  int v64; // edx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdx
  struct MOVESIZEDATA *v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // rax
  __int64 v83; // rsi
  __int64 ShellSpecialWindow; // rax
  char v85; // bl
  bool v86; // di
  __int64 v87; // rax
  int v88; // r8d
  int v89; // edx
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // r9
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rbx
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // r9
  struct tagTHREADINFO *v111; // rax
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rax
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // rax
  ULONG_PTR BugCheckParameter3[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v128; // [rsp+60h] [rbp-58h]

  if ( a1 == *(struct tagTHREADINFO **)(W32GetUserSessionState(a1, a2, a3, a4) + 18984) )
    return;
  if ( !a1 )
  {
    v10 = 0;
    goto LABEL_7;
  }
  if ( !*(_QWORD *)(W32GetUserSessionState(v7, v6, v8, v9) + 18984)
    || *((_QWORD *)a1 + 57) != *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v7, v6, v8, v9) + 18984) + 456LL) )
  {
    v10 = *(_DWORD *)(*((_QWORD *)a1 + 57) + 56LL);
LABEL_7:
    if ( *(_QWORD *)(W32GetUserSessionState(v7, v6, v8, v9) + 18984) )
      v15 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v12, v11, v13, v14) + 18984) + 456LL) + 56LL);
    else
      v15 = 0;
    EtwTraceFocusedProcessChange(v15, v10);
    UserSessionState = W32GetUserSessionState(v17, v16, v18, v19);
    CitProcessForegroundChange(a1, a2, *(_QWORD *)(UserSessionState + 18984));
    if ( a1 )
      ForegroundBoost::SetForegroundPriority(a1, 1, 8);
    if ( *(_QWORD *)(W32GetUserSessionState(v22, v21, v23, v24) + 18984) )
    {
      v25 = W32GetUserSessionState(v7, v6, v8, v9);
      ForegroundBoost::SetForegroundPriority(*(_QWORD *)(v25 + 18984), 0, 8);
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v7, v6, v8, v9) + 18984) )
  {
    v27 = *(_QWORD *)(W32GetUserSessionState(v27, v26, v28, v29) + 18984);
    v30 = *(_QWORD *)(v27 + 472);
  }
  else
  {
    v30 = 0;
  }
  if ( a1 )
    ThreadId = (unsigned int)PsGetThreadId(*(PETHREAD *)a1);
  else
    ThreadId = 0;
  if ( *(_QWORD *)(W32GetUserSessionState(v27, v26, v28, v29) + 18984) )
  {
    v36 = W32GetUserSessionState(v33, v32, v34, v35);
    v37 = (unsigned int)PsGetThreadId(**(PETHREAD **)(v36 + 18984));
  }
  else
  {
    v37 = 0;
  }
  EtwTraceFocusChange(v37, ThreadId);
  if ( *(_QWORD *)(W32GetUserSessionState(v39, v38, v40, v41) + 18984) )
  {
    if ( !a1
      || (v43 = *(_QWORD *)(W32GetUserSessionState(v43, v42, v44, v45) + 18984),
          *(_QWORD *)(v43 + 456) != *((_QWORD *)a1 + 57)) )
    {
      v46 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v43 = *(_QWORD *)(W32GetUserSessionState(0xFFFFF78000000004uLL, v42, v44, v45) + 18984);
      *(_DWORD *)(*(_QWORD *)(v43 + 456) + 1068LL) = v46;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v43, v42, v44, v45) + 18984) )
  {
    KeyboardDelegationTargetQ = GetKeyboardDelegationTargetQ();
    if ( KeyboardDelegationTargetQ )
    {
      v51 = *(_QWORD *)(KeyboardDelegationTargetQ + 120);
      if ( v51 )
        zzzDelegateInputFocusLostWindowEvent(v51, 14);
    }
    DisableDelegation();
  }
  v52 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v53 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v53 = 0;
  }
  v54 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v53 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( a1 )
      v55 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)a1);
    else
      v55 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v52, v47, v48, v49) + 18984) )
    {
      v60 = W32GetUserSessionState(v57, v56, v58, v59);
      v61 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v60 + 18984));
    }
    else
    {
      v61 = 0;
    }
    v62 = W32GetUserSessionState(v57, v56, v58, v59);
    LOBYTE(v63) = v54;
    LOBYTE(v64) = v53;
    WPP_RECORDER_AND_TRACE_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v64,
      v63,
      *(_QWORD *)(v62 + 69152),
      4,
      2,
      114,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
      v61,
      v55);
  }
  *(_QWORD *)(W32GetUserSessionState(v52, v47, v48, v49) + 18984) = a1;
  if ( a1
    && (v65 = *(_QWORD *)(W32GetUserSessionState(v66, v65, v67, v68) + 63320),
        v66 = *(unsigned int *)(*((_QWORD *)a1 + 57) + 56LL),
        v66 == v65) )
  {
    v69 = W32GetUserSessionState(v66, v65, v67, v68);
    *(_DWORD *)(v69 + 14652) |= 2u;
  }
  else
  {
    v70 = W32GetUserSessionState(v66, v65, v67, v68);
    *(_DWORD *)(v70 + 14652) &= ~2u;
  }
  if ( !(unsigned int)IsCurrentSessionServiceSession() )
  {
    *(_OWORD *)BugCheckParameter3 = 0;
    v128 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v72, v71, v73, v74) + 18984) )
    {
      LODWORD(BugCheckParameter3[0]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v76, v75, v77, v78)
                                                                         + 18984)
                                                             + 456LL)
                                                 + 56LL);
      v82 = W32GetUserSessionState(LODWORD(BugCheckParameter3[0]), v79, v80, v81);
      HIDWORD(BugCheckParameter3[0]) = (unsigned int)PsGetThreadId(**(PETHREAD **)(v82 + 18984));
      if ( a2 )
        *(_QWORD *)&v128 = *(_QWORD *)a2;
      else
        *(_QWORD *)&v128 = 0;
    }
    SendMessageTo(2, BugCheckParameter3, 32);
  }
  if ( a1 )
  {
    v83 = W32GetUserSessionState(v72, v71, v73, v74);
    if ( *(_DWORD *)(v83 + 13992) == 1 )
    {
      ShellSpecialWindow = ShellWindowManagement::GetShellSpecialWindow(*((_QWORD *)a1 + 61), 1);
      if ( ShellSpecialWindow )
      {
        if ( *(struct tagTHREADINFO **)(ShellSpecialWindow + 16) == a1 )
        {
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
            || (v85 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
          {
            v85 = 0;
          }
          v86 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v85 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v87 = W32GetUserSessionState(WPP_GLOBAL_Control, v71, v73, v74);
            LOBYTE(v88) = v86;
            LOBYTE(v89) = v85;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v89,
              v88,
              *(_QWORD *)(v87 + 69152),
              4,
              6,
              115,
              (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
          }
          *(_DWORD *)(v83 + 13992) = 2;
        }
      }
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v72, v71, v73, v74) + 18984) )
  {
    v95 = *(_QWORD *)(W32GetUserSessionState(v91, v90, v92, v93) + 18984);
    if ( *(_QWORD *)(v95 + 472) )
    {
      v99 = *(unsigned int *)(W32GetUserSessionState(v95, v94, v96, v97) + 66792);
      if ( (v99 & 0x80u) != 0LL
        || !*(_QWORD *)(W32GetUserSessionState(v99, v98, v100, v101) + 14184)
        || (v106 = *(_QWORD *)(W32GetUserSessionState(v103, v102, v104, v105) + 14184),
            v106 == *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v108, v107, v109, v110) + 18984) + 472LL)) )
      {
        v111 = PtiCurrent();
        Win32HM_LockIntoThread<1>(v111, v30, BugCheckParameter3);
        v116 = W32GetUserSessionState(v113, v112, v114, v115);
        xxxChangeForegroundKeyboardTable(v30, *(_QWORD *)(*(_QWORD *)(v116 + 18984) + 472LL), 0);
        Win32HMThreadLockBase<tagKL,1,0>::~Win32HMThreadLockBase<tagKL,1,0>((ULONG_PTR)BugCheckParameter3);
      }
    }
  }
  if ( !(unsigned int)Feature_AsyncKeyStateRecentDown_Removal2__private_IsEnabledDeviceUsageNoInline() )
  {
    v121 = W32GetUserSessionState(v118, v117, v119, v120);
    *(_OWORD *)(v121 + 14408) = 0;
    *(_OWORD *)(v121 + 14424) = 0;
    v126 = W32GetUserSessionState(v123, v122, v124, v125);
    ++*(_DWORD *)(*(_QWORD *)(v126 + 19704) + 6988LL);
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
