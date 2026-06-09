# xxxSetForegroundThreadWithWindowHint(tagTHREADINFO *,tagWND *)

- ea: `0x1402715ec`
- end: `0x140271cbc`
- name: `?xxxSetForegroundThreadWithWindowHint@@YAXPEAUtagTHREADINFO@@PEAUtagWND@@@Z`
- size: `1744`
- prototype: `void __fastcall(struct tagTHREADINFO *, struct tagWND *)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400be164`
- `0x1401a8530`
- `0x140271cc4`
- `0x1402ab820`

## callees

- `0x140094860`
- `0x1400a4824`
- `0x1400c636c`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x1401ffc74`
- `0x140268ca4`
- `0x1402715ec`
- `0x14027fe2c`
- `0x1402b25cc`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140271782`
- `ntoskrnl!PsGetThreadId` at `0x1402717c1`
- `ntoskrnl!PsGetThreadId` at `0x1402718f7`
- `ntoskrnl!PsGetThreadId` at `0x140271936`
- `ntoskrnl!PsGetThreadId` at `0x140271a62`
- `ntoskrnl!PsGetThreadId` at `0x140271782`
- `ntoskrnl!PsGetThreadId` at `0x1402717c1`
- `ntoskrnl!PsGetThreadId` at `0x1402718f7`
- `ntoskrnl!PsGetThreadId` at `0x140271936`
- `ntoskrnl!PsGetThreadId` at `0x140271a62`
- `win32kbase!xxxChangeForegroundKeyboardTable` at `0x140271c3e`
- `win32kbase!xxxChangeForegroundKeyboardTable` at `0x140271c3e`
- `win32kbase!DisableDelegation` at `0x140271899`
- `win32kbase!DisableDelegation` at `0x140271899`
- `win32kbase!GetKeyboardDelegationTargetQ` at `0x140271875`
- `win32kbase!GetKeyboardDelegationTargetQ` at `0x140271875`
- `win32kbase!EtwTraceFocusChange` at `0x1402717d6`
- `win32kbase!EtwTraceFocusChange` at `0x1402717d6`
- `win32kbase!CitProcessForegroundChange` at `0x1402716e2`
- `win32kbase!CitProcessForegroundChange` at `0x1402716e2`
- `win32kbase!EtwTraceFocusedProcessChange` at `0x1402716bd`
- `win32kbase!EtwTraceFocusedProcessChange` at `0x1402716bd`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x140271701`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x14027173a`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x140271701`
- `win32kbase!?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z` at `0x14027173a`
- `win32kbase!SendMessageTo` at `0x140271a93`
- `win32kbase!SendMessageTo` at `0x140271a93`
- `WIN32K!W32GetUserSessionState` at `0x140271618`
- `WIN32K!W32GetUserSessionState` at `0x140271639`
- `WIN32K!W32GetUserSessionState` at `0x14027164e`
- `WIN32K!W32GetUserSessionState` at `0x140271684`
- `WIN32K!W32GetUserSessionState` at `0x140271699`
- `WIN32K!W32GetUserSessionState` at `0x1402716c9`
- `WIN32K!W32GetUserSessionState` at `0x14027170d`
- `WIN32K!W32GetUserSessionState` at `0x140271722`
- `WIN32K!W32GetUserSessionState` at `0x140271746`
- `WIN32K!W32GetUserSessionState` at `0x14027175b`
- `WIN32K!W32GetUserSessionState` at `0x140271796`
- `WIN32K!W32GetUserSessionState` at `0x1402717ab`
- `WIN32K!W32GetUserSessionState` at `0x1402717e2`
- `WIN32K!W32GetUserSessionState` at `0x1402717fc`
- `WIN32K!W32GetUserSessionState` at `0x140271840`
- `WIN32K!W32GetUserSessionState` at `0x140271860`
- `WIN32K!W32GetUserSessionState` at `0x14027190b`
- `WIN32K!W32GetUserSessionState` at `0x140271920`
- `WIN32K!W32GetUserSessionState` at `0x14027194a`
- `WIN32K!W32GetUserSessionState` at `0x14027199b`
- `WIN32K!W32GetUserSessionState` at `0x1402719b3`
- `WIN32K!W32GetUserSessionState` at `0x1402719d5`
- `WIN32K!W32GetUserSessionState` at `0x1402719e9`
- `WIN32K!W32GetUserSessionState` at `0x140271a16`
- `WIN32K!W32GetUserSessionState` at `0x140271a2b`
- `WIN32K!W32GetUserSessionState` at `0x140271a4c`
- `WIN32K!W32GetUserSessionState` at `0x140271aa8`
- `WIN32K!W32GetUserSessionState` at `0x140271b28`
- `WIN32K!W32GetUserSessionState` at `0x140271b76`
- `WIN32K!W32GetUserSessionState` at `0x140271b8f`
- `WIN32K!W32GetUserSessionState` at `0x140271baf`
- `WIN32K!W32GetUserSessionState` at `0x140271bc5`
- `WIN32K!W32GetUserSessionState` at `0x140271bda`
- `WIN32K!W32GetUserSessionState` at `0x140271bed`
- `WIN32K!W32GetUserSessionState` at `0x140271c1e`
- `WIN32K!W32GetUserSessionState` at `0x140271c5d`
- `WIN32K!W32GetUserSessionState` at `0x140271c7a`
- `WIN32K!W32GetUserSessionState` at `0x140271618`
- `WIN32K!W32GetUserSessionState` at `0x140271639`
- `WIN32K!W32GetUserSessionState` at `0x14027164e`
- `WIN32K!W32GetUserSessionState` at `0x140271684`
- `WIN32K!W32GetUserSessionState` at `0x140271699`
- `WIN32K!W32GetUserSessionState` at `0x1402716c9`
- `WIN32K!W32GetUserSessionState` at `0x14027170d`
- `WIN32K!W32GetUserSessionState` at `0x140271722`
- `WIN32K!W32GetUserSessionState` at `0x140271746`
- `WIN32K!W32GetUserSessionState` at `0x14027175b`
- `WIN32K!W32GetUserSessionState` at `0x140271796`
- `WIN32K!W32GetUserSessionState` at `0x1402717ab`
- `WIN32K!W32GetUserSessionState` at `0x1402717e2`
- `WIN32K!W32GetUserSessionState` at `0x1402717fc`
- `WIN32K!W32GetUserSessionState` at `0x140271840`
- `WIN32K!W32GetUserSessionState` at `0x140271860`
- `WIN32K!W32GetUserSessionState` at `0x14027190b`
- `WIN32K!W32GetUserSessionState` at `0x140271920`
- `WIN32K!W32GetUserSessionState` at `0x14027194a`
- `WIN32K!W32GetUserSessionState` at `0x14027199b`
- `WIN32K!W32GetUserSessionState` at `0x1402719b3`
- `WIN32K!W32GetUserSessionState` at `0x1402719d5`
- `WIN32K!W32GetUserSessionState` at `0x1402719e9`
- `WIN32K!W32GetUserSessionState` at `0x140271a16`
- `WIN32K!W32GetUserSessionState` at `0x140271a2b`
- `WIN32K!W32GetUserSessionState` at `0x140271a4c`
- `WIN32K!W32GetUserSessionState` at `0x140271aa8`
- `WIN32K!W32GetUserSessionState` at `0x140271b28`
- `WIN32K!W32GetUserSessionState` at `0x140271b76`
- `WIN32K!W32GetUserSessionState` at `0x140271b8f`
- `WIN32K!W32GetUserSessionState` at `0x140271baf`
- `WIN32K!W32GetUserSessionState` at `0x140271bc5`
- `WIN32K!W32GetUserSessionState` at `0x140271bda`
- `WIN32K!W32GetUserSessionState` at `0x140271bed`
- `WIN32K!W32GetUserSessionState` at `0x140271c1e`
- `WIN32K!W32GetUserSessionState` at `0x140271c5d`
- `WIN32K!W32GetUserSessionState` at `0x140271c7a`

## pseudocode

```c
void __fastcall xxxSetForegroundThreadWithWindowHint(struct tagTHREADINFO *a1, struct tagWND *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 UserSessionState; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r12
  unsigned int ThreadId; // ebx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 KeyboardDelegationTargetQ; // rax
  __int64 v31; // rcx
  struct MOVESIZEDATA *v32; // rcx
  char v33; // bl
  bool v34; // r14
  char v35; // bp
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rax
  char v39; // si
  __int64 v40; // rax
  int v41; // r8d
  int v42; // edx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  struct MOVESIZEDATA *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rax
  __int64 v53; // rsi
  __int64 ShellSpecialWindow; // rax
  char v55; // bl
  bool v56; // di
  __int64 v57; // rax
  int v58; // r8d
  int v59; // edx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rbx
  __int64 v69; // rdx
  __int64 v70; // rcx
  struct tagTHREADINFO *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // rax
  ULONG_PTR BugCheckParameter3[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v82; // [rsp+60h] [rbp-58h]

  if ( a1 == *(struct tagTHREADINFO **)(W32GetUserSessionState(a1, a2) + 18984) )
    return;
  if ( !a1 )
  {
    v6 = 0;
    goto LABEL_7;
  }
  if ( !*(_QWORD *)(W32GetUserSessionState(v5, v4) + 18984)
    || *((_QWORD *)a1 + 57) != *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v5, v4) + 18984) + 456LL) )
  {
    v6 = *(_DWORD *)(*((_QWORD *)a1 + 57) + 56LL);
LABEL_7:
    if ( *(_QWORD *)(W32GetUserSessionState(v5, v4) + 18984) )
      v9 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v8, v7) + 18984) + 456LL) + 56LL);
    else
      v9 = 0;
    EtwTraceFocusedProcessChange(v9, v6);
    UserSessionState = W32GetUserSessionState(v11, v10);
    CitProcessForegroundChange(a1, a2, *(_QWORD *)(UserSessionState + 18984));
    if ( a1 )
      ForegroundBoost::SetForegroundPriority(a1, 1, 8);
    if ( *(_QWORD *)(W32GetUserSessionState(v14, v13) + 18984) )
    {
      v15 = W32GetUserSessionState(v5, v4);
      ForegroundBoost::SetForegroundPriority(*(_QWORD *)(v15 + 18984), 0, 8);
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v5, v4) + 18984) )
  {
    v17 = *(_QWORD *)(W32GetUserSessionState(v17, v16) + 18984);
    v18 = *(_QWORD *)(v17 + 472);
  }
  else
  {
    v18 = 0;
  }
  if ( a1 )
    ThreadId = (unsigned int)PsGetThreadId(*(PETHREAD *)a1);
  else
    ThreadId = 0;
  if ( *(_QWORD *)(W32GetUserSessionState(v17, v16) + 18984) )
  {
    v22 = W32GetUserSessionState(v21, v20);
    v23 = (unsigned int)PsGetThreadId(**(PETHREAD **)(v22 + 18984));
  }
  else
  {
    v23 = 0;
  }
  EtwTraceFocusChange(v23, ThreadId);
  if ( *(_QWORD *)(W32GetUserSessionState(v25, v24) + 18984) )
  {
    if ( !a1
      || (v27 = *(_QWORD *)(W32GetUserSessionState(v27, v26) + 18984), *(_QWORD *)(v27 + 456) != *((_QWORD *)a1 + 57)) )
    {
      v28 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v27 = *(_QWORD *)(W32GetUserSessionState(0xFFFFF78000000004uLL, v26) + 18984);
      *(_DWORD *)(*(_QWORD *)(v27 + 456) + 1068LL) = v28;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v27, v26) + 18984) )
  {
    KeyboardDelegationTargetQ = GetKeyboardDelegationTargetQ();
    if ( KeyboardDelegationTargetQ )
    {
      v31 = *(_QWORD *)(KeyboardDelegationTargetQ + 120);
      if ( v31 )
        zzzDelegateInputFocusLostWindowEvent(v31, 14);
    }
    DisableDelegation();
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v33 = 0;
  }
  v34 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v33 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( a1 )
      v35 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)a1);
    else
      v35 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v32, v29) + 18984) )
    {
      v38 = W32GetUserSessionState(v37, v36);
      v39 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v38 + 18984));
    }
    else
    {
      v39 = 0;
    }
    v40 = W32GetUserSessionState(v37, v36);
    LOBYTE(v41) = v34;
    LOBYTE(v42) = v33;
    WPP_RECORDER_AND_TRACE_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v42,
      v41,
      *(_QWORD *)(v40 + 69152),
      4,
      2,
      114,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
      v39,
      v35);
  }
  *(_QWORD *)(W32GetUserSessionState(v32, v29) + 18984) = a1;
  if ( a1
    && (v43 = *(_QWORD *)(W32GetUserSessionState(v44, v43) + 63320),
        v44 = *(unsigned int *)(*((_QWORD *)a1 + 57) + 56LL),
        v44 == v43) )
  {
    v45 = W32GetUserSessionState(v44, v43);
    *(_DWORD *)(v45 + 14652) |= 2u;
  }
  else
  {
    v46 = W32GetUserSessionState(v44, v43);
    *(_DWORD *)(v46 + 14652) &= ~2u;
  }
  if ( !(unsigned int)IsCurrentSessionServiceSession() )
  {
    *(_OWORD *)BugCheckParameter3 = 0;
    v82 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v48, v47) + 18984) )
    {
      LODWORD(BugCheckParameter3[0]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v50, v49) + 18984)
                                                             + 456LL)
                                                 + 56LL);
      v52 = W32GetUserSessionState(LODWORD(BugCheckParameter3[0]), v51);
      HIDWORD(BugCheckParameter3[0]) = (unsigned int)PsGetThreadId(**(PETHREAD **)(v52 + 18984));
      if ( a2 )
        *(_QWORD *)&v82 = *(_QWORD *)a2;
      else
        *(_QWORD *)&v82 = 0;
    }
    SendMessageTo(2, BugCheckParameter3, 32);
  }
  if ( a1 )
  {
    v53 = W32GetUserSessionState(v48, v47);
    if ( *(_DWORD *)(v53 + 13992) == 1 )
    {
      ShellSpecialWindow = ShellWindowManagement::GetShellSpecialWindow(*((_QWORD *)a1 + 61), 1);
      if ( ShellSpecialWindow )
      {
        if ( *(struct tagTHREADINFO **)(ShellSpecialWindow + 16) == a1 )
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
            || (v55 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
          {
            v55 = 0;
          }
          v56 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v55 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v57 = W32GetUserSessionState(WPP_GLOBAL_Control, v47);
            LOBYTE(v58) = v56;
            LOBYTE(v59) = v55;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v59,
              v58,
              *(_QWORD *)(v57 + 69152),
              4,
              6,
              115,
              (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
          }
          *(_DWORD *)(v53 + 13992) = 2;
        }
      }
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v48, v47) + 18984) )
  {
    v63 = *(_QWORD *)(W32GetUserSessionState(v61, v60) + 18984);
    if ( *(_QWORD *)(v63 + 472) )
    {
      v65 = *(unsigned int *)(W32GetUserSessionState(v63, v62) + 66792);
      if ( (v65 & 0x80u) != 0LL
        || !*(_QWORD *)(W32GetUserSessionState(v65, v64) + 14184)
        || (v68 = *(_QWORD *)(W32GetUserSessionState(v67, v66) + 14184),
            v68 == *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v70, v69) + 18984) + 472LL)) )
      {
        v71 = PtiCurrent();
        Win32HM_LockIntoThread<1>(v71, v18, BugCheckParameter3);
        v74 = W32GetUserSessionState(v73, v72);
        xxxChangeForegroundKeyboardTable(v18, *(_QWORD *)(*(_QWORD *)(v74 + 18984) + 472LL), 0);
        Win32HMThreadLockBase<tagKL,1,0>::~Win32HMThreadLockBase<tagKL,1,0>((ULONG_PTR)BugCheckParameter3);
      }
    }
  }
  if ( !(unsigned int)Feature_AsyncKeyStateRecentDown_Removal2__private_IsEnabledDeviceUsageNoInline() )
  {
    v77 = W32GetUserSessionState(v76, v75);
    *(_OWORD *)(v77 + 14408) = 0;
    *(_OWORD *)(v77 + 14424) = 0;
    v80 = W32GetUserSessionState(v79, v78);
    ++*(_DWORD *)(*(_QWORD *)(v80 + 19704) + 6988LL);
  }
}

```

## disassembly

```asm
0x1402715ec  mov     [rsp+arg_10], rbx
0x1402715f1  push    rbp
0x1402715f2  push    rsi
0x1402715f3  push    rdi
0x1402715f4  push    r12
0x1402715f6  push    r13
0x1402715f8  push    r14
0x1402715fa  push    r15
0x1402715fc  sub     rsp, 80h
0x140271603  mov     rax, cs:__security_cookie
0x14027160a  xor     rax, rsp
0x14027160d  mov     [rsp+0B8h+var_48], rax
0x140271612  mov     r15, rdx
0x140271615  mov     rdi, rcx
0x140271618  call    cs:__imp_W32GetUserSessionState
0x14027161f  nop     dword ptr [rax+rax+00h]
0x140271624  cmp     rdi, [rax+4A28h]
0x14027162b  jz      loc_140271C93
0x140271631  xor     r13d, r13d
0x140271634  test    rdi, rdi
0x140271637  jz      short loc_140271681
0x140271639  call    cs:__imp_W32GetUserSessionState
0x140271640  nop     dword ptr [rax+rax+00h]
0x140271645  cmp     [rax+4A28h], r13
0x14027164c  jz      short loc_140271675
0x14027164e  call    cs:__imp_W32GetUserSessionState
0x140271655  nop     dword ptr [rax+rax+00h]
0x14027165a  mov     rax, [rax+4A28h]
0x140271661  mov     rax, [rax+1C8h]
0x140271668  cmp     [rdi+1C8h], rax
0x14027166f  jz      loc_140271746
0x140271675  mov     rax, [rdi+1C8h]
0x14027167c  mov     ebx, [rax+38h]
0x14027167f  jmp     short loc_140271684
0x140271681  mov     ebx, r13d
0x140271684  call    cs:__imp_W32GetUserSessionState
0x14027168b  nop     dword ptr [rax+rax+00h]
0x140271690  cmp     [rax+4A28h], r13
0x140271697  jz      short loc_1402716B8
0x140271699  call    cs:__imp_W32GetUserSessionState
0x1402716a0  nop     dword ptr [rax+rax+00h]
0x1402716a5  mov     rcx, [rax+4A28h]
0x1402716ac  mov     rax, [rcx+1C8h]
0x1402716b3  mov     ecx, [rax+38h]
0x1402716b6  jmp     short loc_1402716BB
0x1402716b8  mov     ecx, r13d
0x1402716bb  mov     edx, ebx
0x1402716bd  call    cs:__imp_EtwTraceFocusedProcessChange
0x1402716c4  nop     dword ptr [rax+rax+00h]
0x1402716c9  call    cs:__imp_W32GetUserSessionState
0x1402716d0  nop     dword ptr [rax+rax+00h]
0x1402716d5  mov     rdx, r15
0x1402716d8  mov     rcx, rdi
0x1402716db  mov     r8, [rax+4A28h]
0x1402716e2  call    cs:__imp_CitProcessForegroundChange
0x1402716e9  nop     dword ptr [rax+rax+00h]
0x1402716ee  mov     ebx, 8
0x1402716f3  test    rdi, rdi
0x1402716f6  jz      short loc_14027170D
0x1402716f8  mov     r8d, ebx
0x1402716fb  lea     edx, [rbx-7]
0x1402716fe  mov     rcx, rdi
0x140271701  call    cs:__imp_?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z; ForegroundBoost::SetForegroundPriority(tagTHREADINFO const *,ForegroundBoost::ForegroundPriorityClass,ForegroundBoost::ForegroundBoostSource)
0x140271708  nop     dword ptr [rax+rax+00h]
0x14027170d  call    cs:__imp_W32GetUserSessionState
0x140271714  nop     dword ptr [rax+rax+00h]
0x140271719  cmp     [rax+4A28h], r13
0x140271720  jz      short loc_140271746
0x140271722  call    cs:__imp_W32GetUserSessionState
0x140271729  nop     dword ptr [rax+rax+00h]
0x14027172e  mov     r8d, ebx
0x140271731  xor     edx, edx
0x140271733  mov     rcx, [rax+4A28h]
0x14027173a  call    cs:__imp_?SetForegroundPriority@ForegroundBoost@@YAXPEBUtagTHREADINFO@@W4ForegroundPriorityClass@1@W4ForegroundBoostSource@1@@Z; ForegroundBoost::SetForegroundPriority(tagTHREADINFO const *,ForegroundBoost::ForegroundPriorityClass,ForegroundBoost::ForegroundBoostSource)
0x140271741  nop     dword ptr [rax+rax+00h]
0x140271746  call    cs:__imp_W32GetUserSessionState
0x14027174d  nop     dword ptr [rax+rax+00h]
0x140271752  cmp     [rax+4A28h], r13
0x140271759  jz      short loc_140271777
0x14027175b  call    cs:__imp_W32GetUserSessionState
0x140271762  nop     dword ptr [rax+rax+00h]
0x140271767  mov     rcx, [rax+4A28h]
0x14027176e  mov     r12, [rcx+1D8h]
0x140271775  jmp     short loc_14027177A
0x140271777  mov     r12, r13
0x14027177a  test    rdi, rdi
0x14027177d  jz      short loc_140271793
0x14027177f  mov     rcx, [rdi]; Thread
0x140271782  call    cs:__imp_PsGetThreadId
0x140271789  nop     dword ptr [rax+rax+00h]
0x14027178e  mov     rbx, rax
0x140271791  jmp     short loc_140271796
0x140271793  mov     ebx, r13d
0x140271796  call    cs:__imp_W32GetUserSessionState
0x14027179d  nop     dword ptr [rax+rax+00h]
0x1402717a2  cmp     [rax+4A28h], r13
0x1402717a9  jz      short loc_1402717CF
0x1402717ab  call    cs:__imp_W32GetUserSessionState
0x1402717b2  nop     dword ptr [rax+rax+00h]
0x1402717b7  mov     rcx, [rax+4A28h]
0x1402717be  mov     rcx, [rcx]; Thread
0x1402717c1  call    cs:__imp_PsGetThreadId
0x1402717c8  nop     dword ptr [rax+rax+00h]
0x1402717cd  jmp     short loc_1402717D2
0x1402717cf  mov     eax, r13d
0x1402717d2  mov     edx, ebx
0x1402717d4  mov     ecx, eax
0x1402717d6  call    cs:__imp_EtwTraceFocusChange
0x1402717dd  nop     dword ptr [rax+rax+00h]
0x1402717e2  call    cs:__imp_W32GetUserSessionState
0x1402717e9  nop     dword ptr [rax+rax+00h]
0x1402717ee  cmp     [rax+4A28h], r13
0x1402717f5  jz      short loc_140271860
0x1402717f7  test    rdi, rdi
0x1402717fa  jz      short loc_14027181F
0x1402717fc  call    cs:__imp_W32GetUserSessionState
0x140271803  nop     dword ptr [rax+rax+00h]
0x140271808  mov     rcx, [rax+4A28h]
0x14027180f  mov     rax, [rcx+1C8h]
0x140271816  cmp     rax, [rdi+1C8h]
0x14027181d  jz      short loc_140271860
0x14027181f  mov     rcx, 0FFFFF78000000004h
0x140271829  mov     rax, 0FFFFF78000000320h
0x140271833  mov     rax, [rax]
0x140271836  mov     ebx, [rcx]
0x140271838  imul    rbx, rax
0x14027183c  shr     rbx, 18h
0x140271840  call    cs:__imp_W32GetUserSessionState
0x140271847  nop     dword ptr [rax+rax+00h]
0x14027184c  mov     rcx, [rax+4A28h]
0x140271853  mov     rax, [rcx+1C8h]
0x14027185a  mov     [rax+42Ch], ebx
0x140271860  call    cs:__imp_W32GetUserSessionState
0x140271867  nop     dword ptr [rax+rax+00h]
0x14027186c  cmp     [rax+4A28h], r13
0x140271873  jz      short loc_1402718A5
0x140271875  call    cs:__imp_GetKeyboardDelegationTargetQ
0x14027187c  nop     dword ptr [rax+rax+00h]
0x140271881  test    rax, rax
0x140271884  jz      short loc_140271899
0x140271886  mov     rcx, [rax+78h]
0x14027188a  test    rcx, rcx
0x14027188d  jz      short loc_140271899
0x14027188f  mov     edx, 0Eh
0x140271894  call    zzzDelegateInputFocusLostWindowEvent
0x140271899  call    cs:__imp_DisableDelegation
0x1402718a0  nop     dword ptr [rax+rax+00h]
0x1402718a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1402718ac  lea     rax, WPP_GLOBAL_Control
0x1402718b3  mov     ebp, 2
0x1402718b8  cmp     rcx, rax
0x1402718bb  jz      short loc_1402718CD
0x1402718bd  mov     eax, [rcx+2Ch]
0x1402718c0  test    bpl, al
0x1402718c3  jz      short loc_1402718CD
0x1402718c5  cmp     byte ptr [rcx+29h], 4
0x1402718c9  mov     bl, 1
0x1402718cb  jnb     short loc_1402718D0
0x1402718cd  mov     bl, r13b
0x1402718d0  lea     rax, WPP_RECORDER_INITIALIZED
0x1402718d7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1402718de  setnz   r14b
0x1402718e2  test    bl, bl
0x1402718e4  jnz     short loc_1402718EF
0x1402718e6  test    r14b, r14b
0x1402718e9  jz      loc_14027199B
0x1402718ef  test    rdi, rdi
0x1402718f2  jz      short loc_140271908
0x1402718f4  mov     rcx, [rdi]; Thread
0x1402718f7  call    cs:__imp_PsGetThreadId
0x1402718fe  nop     dword ptr [rax+rax+00h]
0x140271903  mov     rbp, rax
0x140271906  jmp     short loc_14027190B
0x140271908  mov     ebp, r13d
0x14027190b  call    cs:__imp_W32GetUserSessionState
0x140271912  nop     dword ptr [rax+rax+00h]
0x140271917  cmp     [rax+4A28h], r13
0x14027191e  jz      short loc_140271947
0x140271920  call    cs:__imp_W32GetUserSessionState
0x140271927  nop     dword ptr [rax+rax+00h]
0x14027192c  mov     rcx, [rax+4A28h]
0x140271933  mov     rcx, [rcx]; Thread
0x140271936  call    cs:__imp_PsGetThreadId
0x14027193d  nop     dword ptr [rax+rax+00h]
0x140271942  mov     rsi, rax
0x140271945  jmp     short loc_14027194A
0x140271947  mov     esi, r13d
0x14027194a  call    cs:__imp_W32GetUserSessionState
0x140271951  nop     dword ptr [rax+rax+00h]
0x140271956  mov     [rsp+0B8h+var_70], ebp
0x14027195a  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271961  mov     [rsp+0B8h+var_78], esi
0x140271965  mov     ebp, 2
0x14027196a  mov     [rsp+0B8h+var_80], rcx
0x14027196f  mov     r8b, r14b
0x140271972  mov     rcx, cs:WPP_GLOBAL_Control
0x140271979  mov     dl, bl
0x14027197b  mov     r9, [rax+10E20h]
0x140271982  mov     [rsp+0B8h+var_88], 72h ; 'r'
0x140271989  mov     [rsp+0B8h+var_90], ebp
0x14027198d  mov     rcx, [rcx+18h]
0x140271991  mov     [rsp+0B8h+var_98], 4
0x140271996  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14027199b  call    cs:__imp_W32GetUserSessionState
0x1402719a2  nop     dword ptr [rax+rax+00h]
0x1402719a7  mov     [rax+4A28h], rdi
0x1402719ae  test    rdi, rdi
0x1402719b1  jz      short loc_1402719E9
0x1402719b3  call    cs:__imp_W32GetUserSessionState
0x1402719ba  nop     dword ptr [rax+rax+00h]
0x1402719bf  mov     rdx, [rax+0F758h]
0x1402719c6  mov     rax, [rdi+1C8h]
0x1402719cd  mov     ecx, [rax+38h]
0x1402719d0  cmp     rcx, rdx
0x1402719d3  jnz     short loc_1402719E9
0x1402719d5  call    cs:__imp_W32GetUserSessionState
0x1402719dc  nop     dword ptr [rax+rax+00h]
0x1402719e1  or      [rax+393Ch], ebp
0x1402719e7  jmp     short loc_1402719FC
0x1402719e9  call    cs:__imp_W32GetUserSessionState
0x1402719f0  nop     dword ptr [rax+rax+00h]
0x1402719f5  and     dword ptr [rax+393Ch], 0FFFFFFFDh
0x1402719fc  call    IsCurrentSessionServiceSession
0x140271a01  test    eax, eax
0x140271a03  jnz     loc_140271A9F
0x140271a09  xorps   xmm0, xmm0
0x140271a0c  movups  xmmword ptr [rsp+0B8h+BugCheckParameter3], xmm0
0x140271a11  movups  [rsp+0B8h+var_58], xmm0
0x140271a16  call    cs:__imp_W32GetUserSessionState
0x140271a1d  nop     dword ptr [rax+rax+00h]
0x140271a22  cmp     [rax+4A28h], r13
0x140271a29  jz      short loc_140271A86
0x140271a2b  call    cs:__imp_W32GetUserSessionState
0x140271a32  nop     dword ptr [rax+rax+00h]
0x140271a37  mov     rcx, [rax+4A28h]
0x140271a3e  mov     rax, [rcx+1C8h]
0x140271a45  mov     ecx, [rax+38h]
0x140271a48  mov     dword ptr [rsp+0B8h+BugCheckParameter3], ecx
0x140271a4c  call    cs:__imp_W32GetUserSessionState
0x140271a53  nop     dword ptr [rax+rax+00h]
0x140271a58  mov     rcx, [rax+4A28h]
0x140271a5f  mov     rcx, [rcx]; Thread
0x140271a62  call    cs:__imp_PsGetThreadId
0x140271a69  nop     dword ptr [rax+rax+00h]
0x140271a6e  mov     dword ptr [rsp+0B8h+BugCheckParameter3+4], eax
0x140271a72  test    r15, r15
0x140271a75  jnz     short loc_140271A7E
0x140271a77  mov     qword ptr [rsp+0B8h+var_58], r13
0x140271a7c  jmp     short loc_140271A86
0x140271a7e  mov     rax, [r15]
0x140271a81  mov     qword ptr [rsp+0B8h+var_58], rax
0x140271a86  mov     r8d, 20h ; ' '
0x140271a8c  lea     rdx, [rsp+0B8h+BugCheckParameter3]
0x140271a91  mov     ecx, ebp
0x140271a93  call    cs:__imp_SendMessageTo
0x140271a9a  nop     dword ptr [rax+rax+00h]
0x140271a9f  test    rdi, rdi
0x140271aa2  jz      loc_140271B76
0x140271aa8  call    cs:__imp_W32GetUserSessionState
0x140271aaf  nop     dword ptr [rax+rax+00h]
0x140271ab4  mov     rsi, rax
0x140271ab7  cmp     dword ptr [rax+36A8h], 1
0x140271abe  jnz     loc_140271B76
0x140271ac4  mov     rcx, [rdi+1E8h]
0x140271acb  mov     edx, 1
0x140271ad0  call    ?GetShellSpecialWindow@ShellWindowManagement@@YAPEAUtagWND@@PEAUtagDESKTOP@@W4SHELL_SPECIAL_WINDOW@@@Z; ShellWindowManagement::GetShellSpecialWindow(tagDESKTOP *,SHELL_SPECIAL_WINDOW)
0x140271ad5  test    rax, rax
0x140271ad8  jz      loc_140271B76
0x140271ade  cmp     [rax+10h], rdi
0x140271ae2  jnz     loc_140271B76
0x140271ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x140271aef  lea     rax, WPP_GLOBAL_Control
0x140271af6  cmp     rcx, rax
0x140271af9  jz      short loc_140271B0A
0x140271afb  mov     eax, [rcx+2Ch]
0x140271afe  test    al, 20h
0x140271b00  jz      short loc_140271B0A
0x140271b02  cmp     byte ptr [rcx+29h], 4
0x140271b06  mov     bl, 1
0x140271b08  jnb     short loc_140271B0D
0x140271b0a  mov     bl, r13b
0x140271b0d  lea     rax, WPP_RECORDER_INITIALIZED
0x140271b14  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140271b1b  setnz   dil
0x140271b1f  test    bl, bl
0x140271b21  jnz     short loc_140271B28
0x140271b23  test    dil, dil
0x140271b26  jz      short loc_140271B70
0x140271b28  call    cs:__imp_W32GetUserSessionState
0x140271b2f  nop     dword ptr [rax+rax+00h]
0x140271b34  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271b3b  mov     r8b, dil
0x140271b3e  mov     [rsp+0B8h+var_80], rcx
0x140271b43  mov     dl, bl
0x140271b45  mov     rcx, cs:WPP_GLOBAL_Control
0x140271b4c  mov     r9, [rax+10E20h]
0x140271b53  mov     [rsp+0B8h+var_88], 73h ; 's'
0x140271b5a  mov     [rsp+0B8h+var_90], 6
0x140271b62  mov     rcx, [rcx+18h]
0x140271b66  mov     [rsp+0B8h+var_98], 4
  ... truncated ...
```
