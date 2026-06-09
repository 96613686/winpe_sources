# InitiateShutdown(_ETHREAD *,ulong *)

- ea: `0x14027ef2c`
- end: `0x14027f582`
- name: `?InitiateShutdown@@YAJPEAU_ETHREAD@@PEAK@Z`
- size: `1622`
- prototype: `__int64 __fastcall(PETHREAD Thread, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140034240`

## callees

- `0x140007b44`
- `0x140008690`
- `0x140034c9c`
- `0x1400eb064`
- `0x1402612f0`
- `0x14027ef2c`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14027f50a`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14027f50a`
- `ntoskrnl!PsGetThreadProcess` at `0x14027ef99`
- `ntoskrnl!PsGetThreadProcess` at `0x14027ef99`
- `ntoskrnl!PsGetThreadProcessId` at `0x14027efe7`
- `ntoskrnl!PsGetThreadProcessId` at `0x14027f45f`
- `ntoskrnl!PsGetThreadProcessId` at `0x14027efe7`
- `ntoskrnl!PsGetThreadProcessId` at `0x14027f45f`
- `ntoskrnl!PsGetThreadId` at `0x14027f22c`
- `ntoskrnl!PsGetThreadId` at `0x14027f22c`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x14027f0ec`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x14027f0ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14027f3f2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14027f4d0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14027f3f2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14027f4d0`
- `ntoskrnl!PsGetProcessId` at `0x14027f056`
- `ntoskrnl!PsGetProcessId` at `0x14027f144`
- `ntoskrnl!PsGetProcessId` at `0x14027f2e6`
- `ntoskrnl!PsGetProcessId` at `0x14027f056`
- `ntoskrnl!PsGetProcessId` at `0x14027f144`
- `ntoskrnl!PsGetProcessId` at `0x14027f2e6`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14027efa8`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14027efa8`
- `win32kbase!LockObjectAssignment` at `0x14027f542`
- `win32kbase!LockObjectAssignment` at `0x14027f542`
- `win32kbase!GetProcessLuid` at `0x14027ef66`
- `win32kbase!GetProcessLuid` at `0x14027ef66`
- `win32kbase!IsPrivileged` at `0x14027f1d0`
- `win32kbase!IsPrivileged` at `0x14027f1d0`
- `win32kbase!luidSystem` at `0x14027ef72`
- `WIN32K!W32GetUserSessionState` at `0x14027efd1`
- `WIN32K!W32GetUserSessionState` at `0x14027f065`
- `WIN32K!W32GetUserSessionState` at `0x14027f153`
- `WIN32K!W32GetUserSessionState` at `0x14027f23b`
- `WIN32K!W32GetUserSessionState` at `0x14027f2f5`
- `WIN32K!W32GetUserSessionState` at `0x14027f352`
- `WIN32K!W32GetUserSessionState` at `0x14027f36b`
- `WIN32K!W32GetUserSessionState` at `0x14027f389`
- `WIN32K!W32GetUserSessionState` at `0x14027f3a7`
- `WIN32K!W32GetUserSessionState` at `0x14027f3ba`
- `WIN32K!W32GetUserSessionState` at `0x14027f3cf`
- `WIN32K!W32GetUserSessionState` at `0x14027f401`
- `WIN32K!W32GetUserSessionState` at `0x14027f41a`
- `WIN32K!W32GetUserSessionState` at `0x14027f449`
- `WIN32K!W32GetUserSessionState` at `0x14027f4be`
- `WIN32K!W32GetUserSessionState` at `0x14027f4df`
- `WIN32K!W32GetUserSessionState` at `0x14027f4f1`
- `WIN32K!W32GetUserSessionState` at `0x14027f519`
- `WIN32K!W32GetUserSessionState` at `0x14027f52c`
- `WIN32K!W32GetUserSessionState` at `0x14027f560`
- `WIN32K!W32GetUserSessionState` at `0x14027efd1`
- `WIN32K!W32GetUserSessionState` at `0x14027f065`
- `WIN32K!W32GetUserSessionState` at `0x14027f153`
- `WIN32K!W32GetUserSessionState` at `0x14027f23b`
- `WIN32K!W32GetUserSessionState` at `0x14027f2f5`
- `WIN32K!W32GetUserSessionState` at `0x14027f352`
- `WIN32K!W32GetUserSessionState` at `0x14027f36b`
- `WIN32K!W32GetUserSessionState` at `0x14027f389`
- `WIN32K!W32GetUserSessionState` at `0x14027f3a7`
- `WIN32K!W32GetUserSessionState` at `0x14027f3ba`
- `WIN32K!W32GetUserSessionState` at `0x14027f3cf`
- `WIN32K!W32GetUserSessionState` at `0x14027f401`
- `WIN32K!W32GetUserSessionState` at `0x14027f41a`
- `WIN32K!W32GetUserSessionState` at `0x14027f449`
- `WIN32K!W32GetUserSessionState` at `0x14027f4be`
- `WIN32K!W32GetUserSessionState` at `0x14027f4df`
- `WIN32K!W32GetUserSessionState` at `0x14027f4f1`
- `WIN32K!W32GetUserSessionState` at `0x14027f519`
- `WIN32K!W32GetUserSessionState` at `0x14027f52c`
- `WIN32K!W32GetUserSessionState` at `0x14027f560`

## pseudocode

```c
__int64 __fastcall InitiateShutdown(PETHREAD Thread, unsigned int *a2)
{
  int v4; // edi
  unsigned int v5; // edi
  PEPROCESS ThreadProcess; // rax
  _QWORD *ProcessWin32Process; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  _QWORD *v12; // r14
  __int64 v13; // r13
  HANDLE v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  char v19; // si
  bool v20; // di
  char ProcessId; // bl
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 UserSessionState; // rax
  int v27; // r8d
  int v28; // edx
  bool v30; // di
  char v31; // bl
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rax
  int v37; // r8d
  int v38; // edx
  PEPROCESS v39; // rcx
  bool v40; // r12
  int v41; // edi
  char ThreadId; // bl
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rax
  int v48; // r8d
  int v49; // edx
  bool v50; // di
  char v51; // bl
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rax
  int v57; // r8d
  int v58; // edx
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  char v72; // r14
  unsigned int CurrentThreadId; // ebx
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  HANDLE v82; // rbx
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 ThreadWin32Thread; // rbx
  int v88; // edi
  unsigned int v89; // ebx
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // r9
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rax
  __int64 CurrentThreadProcessId; // rbx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // r8
  __int64 v107; // r9
  __int64 v108; // rax
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 v113; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v114[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v115; // [rsp+60h] [rbp-20h]
  int v116; // [rsp+68h] [rbp-18h]

  v113 = 0;
  GetProcessLuid(Thread, &v113);
  v4 = *a2;
  if ( v113 == __PAIR64__(luidSystem[1], luidSystem[0]) )
    v5 = v4 | 0x100;
  else
    v5 = v4 & 0xFFFFFEFF;
  ThreadProcess = PsGetThreadProcess(Thread);
  ProcessWin32Process = (_QWORD *)PsGetProcessWin32Process(ThreadProcess);
  v12 = ProcessWin32Process;
  if ( !ProcessWin32Process || !*ProcessWin32Process )
    return 3221225480LL;
  v13 = ProcessWin32Process[82];
  v14 = *(HANDLE *)(W32GetUserSessionState(v9, v8, v10, v11) + 63312);
  v19 = 1;
  if ( PsGetThreadProcessId(Thread) == v14 )
    goto LABEL_44;
  v5 &= ~0x200u;
  *a2 = v5;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v19 = 0;
    }
    v20 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v19 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)*v12);
      UserSessionState = W32GetUserSessionState(v23, v22, v24, v25);
      LOBYTE(v27) = v20;
      LOBYTE(v28) = v19;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v28,
        v27,
        *(_QWORD *)(UserSessionState + 69152),
        3,
        11,
        10,
        (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
        ProcessId);
    }
    return 3221225480LL;
  }
  if ( !RtlAreAllAccessesGranted(*((_DWORD *)v12 + 168), 0x40u) )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v19 = 0;
    }
    v30 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v19 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v31 = (unsigned __int8)PsGetProcessId((PEPROCESS)*v12);
      v36 = W32GetUserSessionState(v33, v32, v34, v35);
      LOBYTE(v37) = v30;
      LOBYTE(v38) = v19;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v38,
        v37,
        *(_QWORD *)(v36 + 69152),
        3,
        11,
        11,
        (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
        v31);
    }
    return 3221225506LL;
  }
  if ( (v5 & 1) != 0 )
  {
    v39 = (PEPROCESS)*v12;
    v114[0] = 1;
    v116 = 0;
    v114[1] = 1;
    v115 = 19;
    if ( !(unsigned __int8)IsPrivileged(v39, Thread, v114) )
    {
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v19 = 0;
      }
      v40 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v19 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v41 = *((_DWORD *)v12 + 14);
        ThreadId = (unsigned __int8)PsGetThreadId(Thread);
        v47 = W32GetUserSessionState(v44, v43, v45, v46);
        LOBYTE(v48) = v40;
        LOBYTE(v49) = v19;
        WPP_RECORDER_AND_TRACE_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v49,
          v48,
          *(_QWORD *)(v47 + 69152),
          3,
          11,
          12,
          (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
          ThreadId,
          v41);
      }
      return 3221225569LL;
    }
LABEL_44:
    if ( *(_DWORD *)(W32GetUserSessionState(v16, v15, v17, v18) + 63240) )
    {
      v64 = *(_QWORD *)(W32GetUserSessionState(v60, v59, v61, v62) + 63280);
      if ( (_DWORD)v113 != *(_DWORD *)(v64 + 144)
        || (v64 = *(_QWORD *)(W32GetUserSessionState(v64, v63, v65, v66) + 63280),
            HIDWORD(v113) != *(_DWORD *)(v64 + 148)) )
      {
        v67 = *(_QWORD *)(W32GetUserSessionState(v64, v63, v65, v66) + 63272);
        if ( v67 != *(_QWORD *)(W32GetUserSessionState(v69, v68, v70, v71) + 63312) )
          return 3221226029LL;
      }
      v72 = v5 & ~(unsigned __int8)*(_DWORD *)(W32GetUserSessionState(v64, v63, v65, v66) + 63268) & 7;
      if ( v72 )
      {
        CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
        if ( CurrentThreadId != *(_DWORD *)(W32GetUserSessionState(v75, v74, v76, v77) + 63240) )
        {
          if ( (v5 & 1) == 0 && v13 != *(_QWORD *)(W32GetUserSessionState(v79, v78, v80, v81) + 63280) )
            return 2147483665LL;
          if ( (v72 & 4) != 0 )
            return 3221226029LL;
        }
      }
      return 259;
    }
    v82 = *(HANDLE *)(W32GetUserSessionState(v60, v59, v61, v62) + 63312);
    if ( PsGetThreadProcessId(Thread) != v82 )
    {
      ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
      if ( (v5 & 0x8000) != 0 )
      {
        v5 &= ~0x8000u;
        *a2 = v5;
      }
      if ( (unsigned int)NotifyLogon(v5) )
        return 259;
      if ( ThreadWin32Thread && *(_DWORD *)(ThreadWin32Thread + 932) )
        return 3221225688LL;
    }
    v88 = v5 | 0x200;
    *a2 = v88;
    *(_DWORD *)(W32GetUserSessionState(v84, v83, v85, v86) + 63268) = v88;
    v89 = (unsigned int)PsGetCurrentThreadId();
    *(_DWORD *)(W32GetUserSessionState(v91, v90, v92, v93) + 63240) = v89;
    v98 = W32GetUserSessionState(v95, v94, v96, v97);
    *(_DWORD *)(*(_QWORD *)(v98 + 19704) + 2236LL) |= 1u;
    CurrentThreadProcessId = PsGetCurrentThreadProcessId();
    *(_QWORD *)(W32GetUserSessionState(v101, v100, v102, v103) + 63272) = CurrentThreadProcessId;
    v108 = W32GetUserSessionState(v105, v104, v106, v107);
    LockObjectAssignment(v108 + 63280, v13);
    LODWORD(CurrentThreadProcessId) = *(_DWORD *)(v13 + 32);
    *(_QWORD *)(v13 + 144) = v113;
    *(_DWORD *)(W32GetUserSessionState(v110, v109, v111, v112) + 63264) = CurrentThreadProcessId & 3;
    *(_DWORD *)(v13 + 32) |= 0xAu;
    return 0;
  }
  if ( (*(_DWORD *)(v13 + 32) & 4) == 0 )
    goto LABEL_44;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
  {
    v19 = 0;
  }
  v50 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v19 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v51 = (unsigned __int8)PsGetProcessId((PEPROCESS)*v12);
    v56 = W32GetUserSessionState(v53, v52, v54, v55);
    LOBYTE(v57) = v50;
    LOBYTE(v58) = v19;
    WPP_RECORDER_AND_TRACE_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v58,
      v57,
      *(_QWORD *)(v56 + 69152),
      3,
      11,
      13,
      (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
      v51,
      v13);
  }
  return 3221225488LL;
}

```

## disassembly

```asm
0x14027ef2c  mov     [rsp-38h+arg_10], rbx
0x14027ef31  push    rbp
0x14027ef32  push    rsi
0x14027ef33  push    rdi
0x14027ef34  push    r12
0x14027ef36  push    r13
0x14027ef38  push    r14
0x14027ef3a  push    r15
0x14027ef3c  mov     rbp, rsp
0x14027ef3f  sub     rsp, 80h
0x14027ef46  mov     rax, cs:__security_cookie
0x14027ef4d  xor     rax, rsp
0x14027ef50  mov     [rbp+var_10], rax
0x14027ef54  mov     r12, rdx
0x14027ef57  mov     [rbp+var_30], 0
0x14027ef5f  lea     rdx, [rbp+var_30]
0x14027ef63  mov     r15, rcx
0x14027ef66  call    cs:__imp_GetProcessLuid
0x14027ef6d  nop     dword ptr [rax+rax+00h]
0x14027ef72  mov     rax, cs:__imp_luidSystem
0x14027ef79  mov     edi, [r12]
0x14027ef7d  mov     ecx, [rax]
0x14027ef7f  cmp     dword ptr [rbp+var_30], ecx
0x14027ef82  jnz     short loc_14027EF92
0x14027ef84  mov     ecx, [rax+4]
0x14027ef87  cmp     dword ptr [rbp+var_30+4], ecx
0x14027ef8a  jnz     short loc_14027EF92
0x14027ef8c  bts     edi, 8
0x14027ef90  jmp     short loc_14027EF96
0x14027ef92  btr     edi, 8
0x14027ef96  mov     rcx, r15; Thread
0x14027ef99  call    cs:__imp_PsGetThreadProcess
0x14027efa0  nop     dword ptr [rax+rax+00h]
0x14027efa5  mov     rcx, rax
0x14027efa8  call    cs:__imp_PsGetProcessWin32Process
0x14027efaf  nop     dword ptr [rax+rax+00h]
0x14027efb4  mov     r14, rax
0x14027efb7  test    rax, rax
0x14027efba  jz      loc_14027F0B3
0x14027efc0  cmp     qword ptr [rax], 0
0x14027efc4  jz      loc_14027F0B3
0x14027efca  mov     r13, [rax+290h]
0x14027efd1  call    cs:__imp_W32GetUserSessionState
0x14027efd8  nop     dword ptr [rax+rax+00h]
0x14027efdd  mov     rcx, r15; Thread
0x14027efe0  mov     rbx, [rax+0F750h]
0x14027efe7  call    cs:__imp_PsGetThreadProcessId
0x14027efee  nop     dword ptr [rax+rax+00h]
0x14027eff3  mov     esi, 1
0x14027eff8  cmp     rax, rbx
0x14027effb  jz      loc_14027F352
0x14027f001  btr     edi, 9
0x14027f005  mov     [r12], edi
0x14027f009  test    r13, r13
0x14027f00c  jnz     loc_14027F0E0
0x14027f012  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f019  lea     rax, WPP_GLOBAL_Control
0x14027f020  cmp     rcx, rax
0x14027f023  jz      short loc_14027F034
0x14027f025  test    dword ptr [rcx+2Ch], 400h
0x14027f02c  jz      short loc_14027F034
0x14027f02e  cmp     byte ptr [rcx+29h], 3
0x14027f032  jnb     short loc_14027F037
0x14027f034  xor     sil, sil
0x14027f037  lea     rax, WPP_RECORDER_INITIALIZED
0x14027f03e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027f045  setnz   dil
0x14027f049  test    sil, sil
0x14027f04c  jnz     short loc_14027F053
0x14027f04e  test    dil, dil
0x14027f051  jz      short loc_14027F0B3
0x14027f053  mov     rcx, [r14]; Process
0x14027f056  call    cs:__imp_PsGetProcessId
0x14027f05d  nop     dword ptr [rax+rax+00h]
0x14027f062  mov     rbx, rax
0x14027f065  call    cs:__imp_W32GetUserSessionState
0x14027f06c  nop     dword ptr [rax+rax+00h]
0x14027f071  mov     [rsp+80h+var_40], rbx
0x14027f076  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x14027f07d  mov     [rsp+80h+var_48], rcx
0x14027f082  mov     r8b, dil
0x14027f085  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f08c  mov     dl, sil
0x14027f08f  mov     r9, [rax+10E20h]
0x14027f096  mov     [rsp+80h+var_50], 0Ah
0x14027f09d  mov     [rsp+80h+var_58], 0Bh
0x14027f0a5  mov     rcx, [rcx+18h]
0x14027f0a9  mov     [rsp+80h+var_60], 3
0x14027f0ae  call    WPP_RECORDER_AND_TRACE_SF_q
0x14027f0b3  mov     eax, 0C0000008h
0x14027f0b8  mov     rcx, [rbp+var_10]
0x14027f0bc  xor     rcx, rsp; StackCookie
0x14027f0bf  call    __security_check_cookie
0x14027f0c4  mov     rbx, [rsp+80h+arg_10]
0x14027f0cc  add     rsp, 80h
0x14027f0d3  pop     r15
0x14027f0d5  pop     r14
0x14027f0d7  pop     r13
0x14027f0d9  pop     r12
0x14027f0db  pop     rdi
0x14027f0dc  pop     rsi
0x14027f0dd  pop     rbp
0x14027f0de  retn
0x14027f0e0  mov     ecx, [r14+2A0h]; GrantedAccess
0x14027f0e7  mov     edx, 40h ; '@'; DesiredAccess
0x14027f0ec  call    cs:__imp_RtlAreAllAccessesGranted
0x14027f0f3  nop     dword ptr [rax+rax+00h]
0x14027f0f8  test    al, al
0x14027f0fa  jnz     loc_14027F1AA
0x14027f100  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f107  lea     rax, WPP_GLOBAL_Control
0x14027f10e  cmp     rcx, rax
0x14027f111  jz      short loc_14027F122
0x14027f113  test    dword ptr [rcx+2Ch], 400h
0x14027f11a  jz      short loc_14027F122
0x14027f11c  cmp     byte ptr [rcx+29h], 3
0x14027f120  jnb     short loc_14027F125
0x14027f122  xor     sil, sil
0x14027f125  lea     rax, WPP_RECORDER_INITIALIZED
0x14027f12c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027f133  setnz   dil
0x14027f137  test    sil, sil
0x14027f13a  jnz     short loc_14027F141
0x14027f13c  test    dil, dil
0x14027f13f  jz      short loc_14027F1A0
0x14027f141  mov     rcx, [r14]; Process
0x14027f144  call    cs:__imp_PsGetProcessId
0x14027f14b  nop     dword ptr [rax+rax+00h]
0x14027f150  mov     rbx, rax
0x14027f153  call    cs:__imp_W32GetUserSessionState
0x14027f15a  nop     dword ptr [rax+rax+00h]
0x14027f15f  mov     [rsp+80h+var_40], rbx
0x14027f164  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x14027f16b  mov     [rsp+80h+var_48], rcx
0x14027f170  mov     r8b, dil
0x14027f173  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f17a  mov     dl, sil
0x14027f17d  mov     r9, [rax+10E20h]
0x14027f184  mov     eax, 0Bh
0x14027f189  mov     [rsp+80h+var_50], ax
0x14027f18e  mov     [rsp+80h+var_58], eax
0x14027f192  mov     rcx, [rcx+18h]
0x14027f196  mov     [rsp+80h+var_60], 3
0x14027f19b  call    WPP_RECORDER_AND_TRACE_SF_q
0x14027f1a0  mov     eax, 0C0000022h
0x14027f1a5  jmp     loc_14027F0B8
0x14027f1aa  test    sil, dil
0x14027f1ad  jz      loc_14027F296
0x14027f1b3  mov     rcx, [r14]
0x14027f1b6  lea     r8, [rbp+var_28]
0x14027f1ba  xor     eax, eax
0x14027f1bc  mov     [rbp+var_28], esi
0x14027f1bf  mov     rdx, r15
0x14027f1c2  mov     [rbp+var_18], eax
0x14027f1c5  mov     [rbp+var_24], esi
0x14027f1c8  mov     [rbp+var_20], 13h
0x14027f1d0  call    cs:__imp_IsPrivileged
0x14027f1d7  nop     dword ptr [rax+rax+00h]
0x14027f1dc  test    al, al
0x14027f1de  jnz     loc_14027F352
0x14027f1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f1eb  lea     rax, WPP_GLOBAL_Control
0x14027f1f2  cmp     rcx, rax
0x14027f1f5  jz      short loc_14027F206
0x14027f1f7  test    dword ptr [rcx+2Ch], 400h
0x14027f1fe  jz      short loc_14027F206
0x14027f200  cmp     byte ptr [rcx+29h], 3
0x14027f204  jnb     short loc_14027F209
0x14027f206  xor     sil, sil
0x14027f209  lea     rax, WPP_RECORDER_INITIALIZED
0x14027f210  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027f217  setnz   r12b
0x14027f21b  test    sil, sil
0x14027f21e  jnz     short loc_14027F225
0x14027f220  test    r12b, r12b
0x14027f223  jz      short loc_14027F28C
0x14027f225  mov     edi, [r14+38h]
0x14027f229  mov     rcx, r15; Thread
0x14027f22c  call    cs:__imp_PsGetThreadId
0x14027f233  nop     dword ptr [rax+rax+00h]
0x14027f238  mov     rbx, rax
0x14027f23b  call    cs:__imp_W32GetUserSessionState
0x14027f242  nop     dword ptr [rax+rax+00h]
0x14027f247  mov     dword ptr [rsp+80h+var_38], edi
0x14027f24b  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x14027f252  mov     dword ptr [rsp+80h+var_40], ebx
0x14027f256  mov     r8b, r12b
0x14027f259  mov     [rsp+80h+var_48], rcx
0x14027f25e  mov     dl, sil
0x14027f261  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f268  mov     r9, [rax+10E20h]
0x14027f26f  mov     [rsp+80h+var_50], 0Ch
0x14027f276  mov     [rsp+80h+var_58], 0Bh
0x14027f27e  mov     rcx, [rcx+18h]
0x14027f282  mov     [rsp+80h+var_60], 3
0x14027f287  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14027f28c  mov     eax, 0C0000061h
0x14027f291  jmp     loc_14027F0B8
0x14027f296  mov     eax, [r13+20h]
0x14027f29a  test    al, 4
0x14027f29c  jz      loc_14027F352
0x14027f2a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f2a9  lea     rax, WPP_GLOBAL_Control
0x14027f2b0  cmp     rcx, rax
0x14027f2b3  jz      short loc_14027F2C4
0x14027f2b5  test    dword ptr [rcx+2Ch], 400h
0x14027f2bc  jz      short loc_14027F2C4
0x14027f2be  cmp     byte ptr [rcx+29h], 3
0x14027f2c2  jnb     short loc_14027F2C7
0x14027f2c4  xor     sil, sil
0x14027f2c7  lea     rax, WPP_RECORDER_INITIALIZED
0x14027f2ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027f2d5  setnz   dil
0x14027f2d9  test    sil, sil
0x14027f2dc  jnz     short loc_14027F2E3
0x14027f2de  test    dil, dil
0x14027f2e1  jz      short loc_14027F348
0x14027f2e3  mov     rcx, [r14]; Process
0x14027f2e6  call    cs:__imp_PsGetProcessId
0x14027f2ed  nop     dword ptr [rax+rax+00h]
0x14027f2f2  mov     rbx, rax
0x14027f2f5  call    cs:__imp_W32GetUserSessionState
0x14027f2fc  nop     dword ptr [rax+rax+00h]
0x14027f301  mov     [rsp+80h+var_38], r13
0x14027f306  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x14027f30d  mov     [rsp+80h+var_40], rbx
0x14027f312  mov     r8b, dil
0x14027f315  mov     [rsp+80h+var_48], rcx
0x14027f31a  mov     dl, sil
0x14027f31d  mov     rcx, cs:WPP_GLOBAL_Control
0x14027f324  mov     r9, [rax+10E20h]
0x14027f32b  mov     [rsp+80h+var_50], 0Dh
0x14027f332  mov     [rsp+80h+var_58], 0Bh
0x14027f33a  mov     rcx, [rcx+18h]
0x14027f33e  mov     [rsp+80h+var_60], 3
0x14027f343  call    WPP_RECORDER_AND_TRACE_SF_qq
0x14027f348  mov     eax, 0C0000010h
0x14027f34d  jmp     loc_14027F0B8
0x14027f352  call    cs:__imp_W32GetUserSessionState
0x14027f359  nop     dword ptr [rax+rax+00h]
0x14027f35e  cmp     dword ptr [rax+0F708h], 0
0x14027f365  jz      loc_14027F449
0x14027f36b  call    cs:__imp_W32GetUserSessionState
0x14027f372  nop     dword ptr [rax+rax+00h]
0x14027f377  mov     rcx, [rax+0F730h]
0x14027f37e  mov     eax, [rcx+90h]
0x14027f384  cmp     dword ptr [rbp+var_30], eax
0x14027f387  jnz     short loc_14027F3A7
0x14027f389  call    cs:__imp_W32GetUserSessionState
0x14027f390  nop     dword ptr [rax+rax+00h]
0x14027f395  mov     rcx, [rax+0F730h]
0x14027f39c  mov     eax, [rcx+94h]
0x14027f3a2  cmp     dword ptr [rbp+var_30+4], eax
0x14027f3a5  jz      short loc_14027F3CF
0x14027f3a7  call    cs:__imp_W32GetUserSessionState
0x14027f3ae  nop     dword ptr [rax+rax+00h]
0x14027f3b3  mov     rbx, [rax+0F728h]
0x14027f3ba  call    cs:__imp_W32GetUserSessionState
0x14027f3c1  nop     dword ptr [rax+rax+00h]
0x14027f3c6  cmp     rbx, [rax+0F750h]
0x14027f3cd  jnz     short loc_14027F43F
0x14027f3cf  call    cs:__imp_W32GetUserSessionState
0x14027f3d6  nop     dword ptr [rax+rax+00h]
0x14027f3db  mov     r14d, [rax+0F724h]
0x14027f3e2  not     r14d
0x14027f3e5  and     r14d, edi
0x14027f3e8  and     r14d, 7
0x14027f3ec  jz      loc_14027F494
0x14027f3f2  call    cs:__imp_PsGetCurrentThreadId
0x14027f3f9  nop     dword ptr [rax+rax+00h]
0x14027f3fe  mov     rbx, rax
0x14027f401  call    cs:__imp_W32GetUserSessionState
0x14027f408  nop     dword ptr [rax+rax+00h]
0x14027f40d  cmp     ebx, [rax+0F708h]
0x14027f413  jz      short loc_14027F494
0x14027f415  test    sil, dil
0x14027f418  jnz     short loc_14027F439
0x14027f41a  call    cs:__imp_W32GetUserSessionState
0x14027f421  nop     dword ptr [rax+rax+00h]
0x14027f426  cmp     r13, [rax+0F730h]
0x14027f42d  jz      short loc_14027F439
0x14027f42f  mov     eax, 80000011h
0x14027f434  jmp     loc_14027F0B8
0x14027f439  test    r14b, 4
0x14027f43d  jz      short loc_14027F494
0x14027f43f  mov     eax, 0C000022Dh
0x14027f444  jmp     loc_14027F0B8
0x14027f449  call    cs:__imp_W32GetUserSessionState
0x14027f450  nop     dword ptr [rax+rax+00h]
0x14027f455  mov     rcx, r15; Thread
0x14027f458  mov     rbx, [rax+0F750h]
0x14027f45f  call    cs:__imp_PsGetThreadProcessId
0x14027f466  nop     dword ptr [rax+rax+00h]
0x14027f46b  cmp     rax, rbx
0x14027f46e  jz      short loc_14027F4B6
0x14027f470  mov     rcx, r15
0x14027f473  call    W32GetThreadWin32Thread
0x14027f478  mov     rbx, rax
0x14027f47b  bt      edi, 0Fh
0x14027f47f  jnb     short loc_14027F489
  ... truncated ...
```
