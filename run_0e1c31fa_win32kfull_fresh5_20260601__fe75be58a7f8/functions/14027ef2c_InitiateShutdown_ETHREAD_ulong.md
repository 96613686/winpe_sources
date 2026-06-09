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
  __int64 v8; // rcx
  _QWORD *v9; // r14
  __int64 v10; // r13
  HANDLE v11; // rbx
  __int64 v12; // rcx
  char v13; // si
  bool v14; // di
  char ProcessId; // bl
  __int64 v16; // rcx
  __int64 UserSessionState; // rax
  int v18; // r8d
  int v19; // edx
  bool v21; // di
  char v22; // bl
  __int64 v23; // rcx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx
  PEPROCESS v27; // rcx
  bool v28; // r12
  int v29; // edi
  char ThreadId; // bl
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  bool v35; // di
  char v36; // bl
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // r8d
  int v40; // edx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rbx
  __int64 v44; // rcx
  char v45; // r14
  unsigned int CurrentThreadId; // ebx
  __int64 v47; // rcx
  __int64 v48; // rcx
  HANDLE v49; // rbx
  __int64 v50; // rcx
  __int64 ThreadWin32Thread; // rbx
  int v52; // edi
  unsigned int v53; // ebx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 CurrentThreadProcessId; // rbx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v63[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v64; // [rsp+60h] [rbp-20h]
  int v65; // [rsp+68h] [rbp-18h]

  v62 = 0;
  GetProcessLuid(Thread, &v62);
  v4 = *a2;
  if ( v62 == __PAIR64__(luidSystem[1], luidSystem[0]) )
    v5 = v4 | 0x100;
  else
    v5 = v4 & 0xFFFFFEFF;
  ThreadProcess = PsGetThreadProcess(Thread);
  ProcessWin32Process = (_QWORD *)PsGetProcessWin32Process(ThreadProcess);
  v9 = ProcessWin32Process;
  if ( !ProcessWin32Process || !*ProcessWin32Process )
    return 3221225480LL;
  v10 = ProcessWin32Process[82];
  v11 = *(HANDLE *)(W32GetUserSessionState(v8) + 63312);
  v13 = 1;
  if ( PsGetThreadProcessId(Thread) == v11 )
    goto LABEL_44;
  v5 &= ~0x200u;
  *a2 = v5;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v13 = 0;
    }
    v14 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v13 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)*v9);
      UserSessionState = W32GetUserSessionState(v16);
      LOBYTE(v18) = v14;
      LOBYTE(v19) = v13;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v19,
        v18,
        *(_QWORD *)(UserSessionState + 69152),
        3,
        11,
        10,
        (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
        ProcessId);
    }
    return 3221225480LL;
  }
  if ( !RtlAreAllAccessesGranted(*((_DWORD *)v9 + 168), 0x40u) )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v13 = 0;
    }
    v21 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v13 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v22 = (unsigned __int8)PsGetProcessId((PEPROCESS)*v9);
      v24 = W32GetUserSessionState(v23);
      LOBYTE(v25) = v21;
      LOBYTE(v26) = v13;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
        v25,
        *(_QWORD *)(v24 + 69152),
        3,
        11,
        11,
        (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
        v22);
    }
    return 3221225506LL;
  }
  if ( (v5 & 1) != 0 )
  {
    v27 = (PEPROCESS)*v9;
    v63[0] = 1;
    v65 = 0;
    v63[1] = 1;
    v64 = 19;
    if ( !(unsigned __int8)IsPrivileged(v27, Thread, v63) )
    {
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v13 = 0;
      }
      v28 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v13 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v29 = *((_DWORD *)v9 + 14);
        ThreadId = (unsigned __int8)PsGetThreadId(Thread);
        v32 = W32GetUserSessionState(v31);
        LOBYTE(v33) = v28;
        LOBYTE(v34) = v13;
        WPP_RECORDER_AND_TRACE_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v34,
          v33,
          *(_QWORD *)(v32 + 69152),
          3,
          11,
          12,
          (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
          ThreadId,
          v29);
      }
      return 3221225569LL;
    }
LABEL_44:
    if ( *(_DWORD *)(W32GetUserSessionState(v12) + 63240) )
    {
      v42 = *(_QWORD *)(W32GetUserSessionState(v41) + 63280);
      if ( (_DWORD)v62 != *(_DWORD *)(v42 + 144)
        || (v42 = *(_QWORD *)(W32GetUserSessionState(v42) + 63280), HIDWORD(v62) != *(_DWORD *)(v42 + 148)) )
      {
        v43 = *(_QWORD *)(W32GetUserSessionState(v42) + 63272);
        if ( v43 != *(_QWORD *)(W32GetUserSessionState(v44) + 63312) )
          return 3221226029LL;
      }
      v45 = v5 & ~(unsigned __int8)*(_DWORD *)(W32GetUserSessionState(v42) + 63268) & 7;
      if ( v45 )
      {
        CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
        if ( CurrentThreadId != *(_DWORD *)(W32GetUserSessionState(v47) + 63240) )
        {
          if ( (v5 & 1) == 0 && v10 != *(_QWORD *)(W32GetUserSessionState(v48) + 63280) )
            return 2147483665LL;
          if ( (v45 & 4) != 0 )
            return 3221226029LL;
        }
      }
      return 259;
    }
    v49 = *(HANDLE *)(W32GetUserSessionState(v41) + 63312);
    if ( PsGetThreadProcessId(Thread) != v49 )
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
    v52 = v5 | 0x200;
    *a2 = v52;
    *(_DWORD *)(W32GetUserSessionState(v50) + 63268) = v52;
    v53 = (unsigned int)PsGetCurrentThreadId();
    *(_DWORD *)(W32GetUserSessionState(v54) + 63240) = v53;
    v56 = W32GetUserSessionState(v55);
    *(_DWORD *)(*(_QWORD *)(v56 + 19704) + 2236LL) |= 1u;
    CurrentThreadProcessId = PsGetCurrentThreadProcessId();
    *(_QWORD *)(W32GetUserSessionState(v58) + 63272) = CurrentThreadProcessId;
    v60 = W32GetUserSessionState(v59);
    LockObjectAssignment(v60 + 63280, v10);
    LODWORD(CurrentThreadProcessId) = *(_DWORD *)(v10 + 32);
    *(_QWORD *)(v10 + 144) = v62;
    *(_DWORD *)(W32GetUserSessionState(v61) + 63264) = CurrentThreadProcessId & 3;
    *(_DWORD *)(v10 + 32) |= 0xAu;
    return 0;
  }
  if ( (*(_DWORD *)(v10 + 32) & 4) == 0 )
    goto LABEL_44;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
  {
    v13 = 0;
  }
  v35 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v13 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v36 = (unsigned __int8)PsGetProcessId((PEPROCESS)*v9);
    v38 = W32GetUserSessionState(v37);
    LOBYTE(v39) = v35;
    LOBYTE(v40) = v13;
    WPP_RECORDER_AND_TRACE_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v40,
      v39,
      *(_QWORD *)(v38 + 69152),
      3,
      11,
      13,
      (__int64)WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids,
      v36,
      v10);
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
