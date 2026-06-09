# InitiateShutdown(_ETHREAD *,ulong *)

- ea: `0x140281158`
- end: `0x1402817ae`
- name: `?InitiateShutdown@@YAJPEAU_ETHREAD@@PEAK@Z`
- size: `1622`
- prototype: `__int64 __fastcall(PETHREAD Thread, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14002fbc0`

## callees

- `0x14003061c`
- `0x1400c636c`
- `0x1400ca844`
- `0x1400cb390`
- `0x1402639a0`
- `0x140281158`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x140281736`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x140281736`
- `ntoskrnl!PsGetThreadProcess` at `0x1402811c5`
- `ntoskrnl!PsGetThreadProcess` at `0x1402811c5`
- `ntoskrnl!PsGetThreadProcessId` at `0x140281213`
- `ntoskrnl!PsGetThreadProcessId` at `0x14028168b`
- `ntoskrnl!PsGetThreadProcessId` at `0x140281213`
- `ntoskrnl!PsGetThreadProcessId` at `0x14028168b`
- `ntoskrnl!PsGetThreadId` at `0x140281458`
- `ntoskrnl!PsGetThreadId` at `0x140281458`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x140281318`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x140281318`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14028161e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1402816fc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14028161e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1402816fc`
- `ntoskrnl!PsGetProcessId` at `0x140281282`
- `ntoskrnl!PsGetProcessId` at `0x140281370`
- `ntoskrnl!PsGetProcessId` at `0x140281512`
- `ntoskrnl!PsGetProcessId` at `0x140281282`
- `ntoskrnl!PsGetProcessId` at `0x140281370`
- `ntoskrnl!PsGetProcessId` at `0x140281512`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1402811d4`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1402811d4`
- `win32kbase!LockObjectAssignment` at `0x14028176e`
- `win32kbase!LockObjectAssignment` at `0x14028176e`
- `win32kbase!GetProcessLuid` at `0x140281192`
- `win32kbase!GetProcessLuid` at `0x140281192`
- `win32kbase!IsPrivileged` at `0x1402813fc`
- `win32kbase!IsPrivileged` at `0x1402813fc`
- `win32kbase!luidSystem` at `0x14028119e`
- `WIN32K!W32GetUserSessionState` at `0x1402811fd`
- `WIN32K!W32GetUserSessionState` at `0x140281291`
- `WIN32K!W32GetUserSessionState` at `0x14028137f`
- `WIN32K!W32GetUserSessionState` at `0x140281467`
- `WIN32K!W32GetUserSessionState` at `0x140281521`
- `WIN32K!W32GetUserSessionState` at `0x14028157e`
- `WIN32K!W32GetUserSessionState` at `0x140281597`
- `WIN32K!W32GetUserSessionState` at `0x1402815b5`
- `WIN32K!W32GetUserSessionState` at `0x1402815d3`
- `WIN32K!W32GetUserSessionState` at `0x1402815e6`
- `WIN32K!W32GetUserSessionState` at `0x1402815fb`
- `WIN32K!W32GetUserSessionState` at `0x14028162d`
- `WIN32K!W32GetUserSessionState` at `0x140281646`
- `WIN32K!W32GetUserSessionState` at `0x140281675`
- `WIN32K!W32GetUserSessionState` at `0x1402816ea`
- `WIN32K!W32GetUserSessionState` at `0x14028170b`
- `WIN32K!W32GetUserSessionState` at `0x14028171d`
- `WIN32K!W32GetUserSessionState` at `0x140281745`
- `WIN32K!W32GetUserSessionState` at `0x140281758`
- `WIN32K!W32GetUserSessionState` at `0x14028178c`
- `WIN32K!W32GetUserSessionState` at `0x1402811fd`
- `WIN32K!W32GetUserSessionState` at `0x140281291`
- `WIN32K!W32GetUserSessionState` at `0x14028137f`
- `WIN32K!W32GetUserSessionState` at `0x140281467`
- `WIN32K!W32GetUserSessionState` at `0x140281521`
- `WIN32K!W32GetUserSessionState` at `0x14028157e`
- `WIN32K!W32GetUserSessionState` at `0x140281597`
- `WIN32K!W32GetUserSessionState` at `0x1402815b5`
- `WIN32K!W32GetUserSessionState` at `0x1402815d3`
- `WIN32K!W32GetUserSessionState` at `0x1402815e6`
- `WIN32K!W32GetUserSessionState` at `0x1402815fb`
- `WIN32K!W32GetUserSessionState` at `0x14028162d`
- `WIN32K!W32GetUserSessionState` at `0x140281646`
- `WIN32K!W32GetUserSessionState` at `0x140281675`
- `WIN32K!W32GetUserSessionState` at `0x1402816ea`
- `WIN32K!W32GetUserSessionState` at `0x14028170b`
- `WIN32K!W32GetUserSessionState` at `0x14028171d`
- `WIN32K!W32GetUserSessionState` at `0x140281745`
- `WIN32K!W32GetUserSessionState` at `0x140281758`
- `WIN32K!W32GetUserSessionState` at `0x14028178c`

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
0x140281158  mov     [rsp-38h+arg_10], rbx
0x14028115d  push    rbp
0x14028115e  push    rsi
0x14028115f  push    rdi
0x140281160  push    r12
0x140281162  push    r13
0x140281164  push    r14
0x140281166  push    r15
0x140281168  mov     rbp, rsp
0x14028116b  sub     rsp, 80h
0x140281172  mov     rax, cs:__security_cookie
0x140281179  xor     rax, rsp
0x14028117c  mov     [rbp+var_10], rax
0x140281180  mov     r12, rdx
0x140281183  mov     [rbp+var_30], 0
0x14028118b  lea     rdx, [rbp+var_30]
0x14028118f  mov     r15, rcx
0x140281192  call    cs:__imp_GetProcessLuid
0x140281199  nop     dword ptr [rax+rax+00h]
0x14028119e  mov     rax, cs:__imp_luidSystem
0x1402811a5  mov     edi, [r12]
0x1402811a9  mov     ecx, [rax]
0x1402811ab  cmp     dword ptr [rbp+var_30], ecx
0x1402811ae  jnz     short loc_1402811BE
0x1402811b0  mov     ecx, [rax+4]
0x1402811b3  cmp     dword ptr [rbp+var_30+4], ecx
0x1402811b6  jnz     short loc_1402811BE
0x1402811b8  bts     edi, 8
0x1402811bc  jmp     short loc_1402811C2
0x1402811be  btr     edi, 8
0x1402811c2  mov     rcx, r15; Thread
0x1402811c5  call    cs:__imp_PsGetThreadProcess
0x1402811cc  nop     dword ptr [rax+rax+00h]
0x1402811d1  mov     rcx, rax
0x1402811d4  call    cs:__imp_PsGetProcessWin32Process
0x1402811db  nop     dword ptr [rax+rax+00h]
0x1402811e0  mov     r14, rax
0x1402811e3  test    rax, rax
0x1402811e6  jz      loc_1402812DF
0x1402811ec  cmp     qword ptr [rax], 0
0x1402811f0  jz      loc_1402812DF
0x1402811f6  mov     r13, [rax+290h]
0x1402811fd  call    cs:__imp_W32GetUserSessionState
0x140281204  nop     dword ptr [rax+rax+00h]
0x140281209  mov     rcx, r15; Thread
0x14028120c  mov     rbx, [rax+0F750h]
0x140281213  call    cs:__imp_PsGetThreadProcessId
0x14028121a  nop     dword ptr [rax+rax+00h]
0x14028121f  mov     esi, 1
0x140281224  cmp     rax, rbx
0x140281227  jz      loc_14028157E
0x14028122d  btr     edi, 9
0x140281231  mov     [r12], edi
0x140281235  test    r13, r13
0x140281238  jnz     loc_14028130C
0x14028123e  mov     rcx, cs:WPP_GLOBAL_Control
0x140281245  lea     rax, WPP_GLOBAL_Control
0x14028124c  cmp     rcx, rax
0x14028124f  jz      short loc_140281260
0x140281251  test    dword ptr [rcx+2Ch], 400h
0x140281258  jz      short loc_140281260
0x14028125a  cmp     byte ptr [rcx+29h], 3
0x14028125e  jnb     short loc_140281263
0x140281260  xor     sil, sil
0x140281263  lea     rax, WPP_RECORDER_INITIALIZED
0x14028126a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140281271  setnz   dil
0x140281275  test    sil, sil
0x140281278  jnz     short loc_14028127F
0x14028127a  test    dil, dil
0x14028127d  jz      short loc_1402812DF
0x14028127f  mov     rcx, [r14]; Process
0x140281282  call    cs:__imp_PsGetProcessId
0x140281289  nop     dword ptr [rax+rax+00h]
0x14028128e  mov     rbx, rax
0x140281291  call    cs:__imp_W32GetUserSessionState
0x140281298  nop     dword ptr [rax+rax+00h]
0x14028129d  mov     [rsp+80h+var_40], rbx
0x1402812a2  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x1402812a9  mov     [rsp+80h+var_48], rcx
0x1402812ae  mov     r8b, dil
0x1402812b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1402812b8  mov     dl, sil
0x1402812bb  mov     r9, [rax+10E20h]
0x1402812c2  mov     [rsp+80h+var_50], 0Ah
0x1402812c9  mov     [rsp+80h+var_58], 0Bh
0x1402812d1  mov     rcx, [rcx+18h]
0x1402812d5  mov     [rsp+80h+var_60], 3
0x1402812da  call    WPP_RECORDER_AND_TRACE_SF_q
0x1402812df  mov     eax, 0C0000008h
0x1402812e4  mov     rcx, [rbp+var_10]
0x1402812e8  xor     rcx, rsp; StackCookie
0x1402812eb  call    __security_check_cookie
0x1402812f0  mov     rbx, [rsp+80h+arg_10]
0x1402812f8  add     rsp, 80h
0x1402812ff  pop     r15
0x140281301  pop     r14
0x140281303  pop     r13
0x140281305  pop     r12
0x140281307  pop     rdi
0x140281308  pop     rsi
0x140281309  pop     rbp
0x14028130a  retn
0x14028130c  mov     ecx, [r14+2A0h]; GrantedAccess
0x140281313  mov     edx, 40h ; '@'; DesiredAccess
0x140281318  call    cs:__imp_RtlAreAllAccessesGranted
0x14028131f  nop     dword ptr [rax+rax+00h]
0x140281324  test    al, al
0x140281326  jnz     loc_1402813D6
0x14028132c  mov     rcx, cs:WPP_GLOBAL_Control
0x140281333  lea     rax, WPP_GLOBAL_Control
0x14028133a  cmp     rcx, rax
0x14028133d  jz      short loc_14028134E
0x14028133f  test    dword ptr [rcx+2Ch], 400h
0x140281346  jz      short loc_14028134E
0x140281348  cmp     byte ptr [rcx+29h], 3
0x14028134c  jnb     short loc_140281351
0x14028134e  xor     sil, sil
0x140281351  lea     rax, WPP_RECORDER_INITIALIZED
0x140281358  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14028135f  setnz   dil
0x140281363  test    sil, sil
0x140281366  jnz     short loc_14028136D
0x140281368  test    dil, dil
0x14028136b  jz      short loc_1402813CC
0x14028136d  mov     rcx, [r14]; Process
0x140281370  call    cs:__imp_PsGetProcessId
0x140281377  nop     dword ptr [rax+rax+00h]
0x14028137c  mov     rbx, rax
0x14028137f  call    cs:__imp_W32GetUserSessionState
0x140281386  nop     dword ptr [rax+rax+00h]
0x14028138b  mov     [rsp+80h+var_40], rbx
0x140281390  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x140281397  mov     [rsp+80h+var_48], rcx
0x14028139c  mov     r8b, dil
0x14028139f  mov     rcx, cs:WPP_GLOBAL_Control
0x1402813a6  mov     dl, sil
0x1402813a9  mov     r9, [rax+10E20h]
0x1402813b0  mov     eax, 0Bh
0x1402813b5  mov     [rsp+80h+var_50], ax
0x1402813ba  mov     [rsp+80h+var_58], eax
0x1402813be  mov     rcx, [rcx+18h]
0x1402813c2  mov     [rsp+80h+var_60], 3
0x1402813c7  call    WPP_RECORDER_AND_TRACE_SF_q
0x1402813cc  mov     eax, 0C0000022h
0x1402813d1  jmp     loc_1402812E4
0x1402813d6  test    sil, dil
0x1402813d9  jz      loc_1402814C2
0x1402813df  mov     rcx, [r14]
0x1402813e2  lea     r8, [rbp+var_28]
0x1402813e6  xor     eax, eax
0x1402813e8  mov     [rbp+var_28], esi
0x1402813eb  mov     rdx, r15
0x1402813ee  mov     [rbp+var_18], eax
0x1402813f1  mov     [rbp+var_24], esi
0x1402813f4  mov     [rbp+var_20], 13h
0x1402813fc  call    cs:__imp_IsPrivileged
0x140281403  nop     dword ptr [rax+rax+00h]
0x140281408  test    al, al
0x14028140a  jnz     loc_14028157E
0x140281410  mov     rcx, cs:WPP_GLOBAL_Control
0x140281417  lea     rax, WPP_GLOBAL_Control
0x14028141e  cmp     rcx, rax
0x140281421  jz      short loc_140281432
0x140281423  test    dword ptr [rcx+2Ch], 400h
0x14028142a  jz      short loc_140281432
0x14028142c  cmp     byte ptr [rcx+29h], 3
0x140281430  jnb     short loc_140281435
0x140281432  xor     sil, sil
0x140281435  lea     rax, WPP_RECORDER_INITIALIZED
0x14028143c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140281443  setnz   r12b
0x140281447  test    sil, sil
0x14028144a  jnz     short loc_140281451
0x14028144c  test    r12b, r12b
0x14028144f  jz      short loc_1402814B8
0x140281451  mov     edi, [r14+38h]
0x140281455  mov     rcx, r15; Thread
0x140281458  call    cs:__imp_PsGetThreadId
0x14028145f  nop     dword ptr [rax+rax+00h]
0x140281464  mov     rbx, rax
0x140281467  call    cs:__imp_W32GetUserSessionState
0x14028146e  nop     dword ptr [rax+rax+00h]
0x140281473  mov     dword ptr [rsp+80h+var_38], edi
0x140281477  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x14028147e  mov     dword ptr [rsp+80h+var_40], ebx
0x140281482  mov     r8b, r12b
0x140281485  mov     [rsp+80h+var_48], rcx
0x14028148a  mov     dl, sil
0x14028148d  mov     rcx, cs:WPP_GLOBAL_Control
0x140281494  mov     r9, [rax+10E20h]
0x14028149b  mov     [rsp+80h+var_50], 0Ch
0x1402814a2  mov     [rsp+80h+var_58], 0Bh
0x1402814aa  mov     rcx, [rcx+18h]
0x1402814ae  mov     [rsp+80h+var_60], 3
0x1402814b3  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1402814b8  mov     eax, 0C0000061h
0x1402814bd  jmp     loc_1402812E4
0x1402814c2  mov     eax, [r13+20h]
0x1402814c6  test    al, 4
0x1402814c8  jz      loc_14028157E
0x1402814ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1402814d5  lea     rax, WPP_GLOBAL_Control
0x1402814dc  cmp     rcx, rax
0x1402814df  jz      short loc_1402814F0
0x1402814e1  test    dword ptr [rcx+2Ch], 400h
0x1402814e8  jz      short loc_1402814F0
0x1402814ea  cmp     byte ptr [rcx+29h], 3
0x1402814ee  jnb     short loc_1402814F3
0x1402814f0  xor     sil, sil
0x1402814f3  lea     rax, WPP_RECORDER_INITIALIZED
0x1402814fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140281501  setnz   dil
0x140281505  test    sil, sil
0x140281508  jnz     short loc_14028150F
0x14028150a  test    dil, dil
0x14028150d  jz      short loc_140281574
0x14028150f  mov     rcx, [r14]; Process
0x140281512  call    cs:__imp_PsGetProcessId
0x140281519  nop     dword ptr [rax+rax+00h]
0x14028151e  mov     rbx, rax
0x140281521  call    cs:__imp_W32GetUserSessionState
0x140281528  nop     dword ptr [rax+rax+00h]
0x14028152d  mov     [rsp+80h+var_38], r13
0x140281532  lea     rcx, WPP_10cc4f57605a3a9d31248f005dacd70d_Traceguids
0x140281539  mov     [rsp+80h+var_40], rbx
0x14028153e  mov     r8b, dil
0x140281541  mov     [rsp+80h+var_48], rcx
0x140281546  mov     dl, sil
0x140281549  mov     rcx, cs:WPP_GLOBAL_Control
0x140281550  mov     r9, [rax+10E20h]
0x140281557  mov     [rsp+80h+var_50], 0Dh
0x14028155e  mov     [rsp+80h+var_58], 0Bh
0x140281566  mov     rcx, [rcx+18h]
0x14028156a  mov     [rsp+80h+var_60], 3
0x14028156f  call    WPP_RECORDER_AND_TRACE_SF_qq
0x140281574  mov     eax, 0C0000010h
0x140281579  jmp     loc_1402812E4
0x14028157e  call    cs:__imp_W32GetUserSessionState
0x140281585  nop     dword ptr [rax+rax+00h]
0x14028158a  cmp     dword ptr [rax+0F708h], 0
0x140281591  jz      loc_140281675
0x140281597  call    cs:__imp_W32GetUserSessionState
0x14028159e  nop     dword ptr [rax+rax+00h]
0x1402815a3  mov     rcx, [rax+0F730h]
0x1402815aa  mov     eax, [rcx+90h]
0x1402815b0  cmp     dword ptr [rbp+var_30], eax
0x1402815b3  jnz     short loc_1402815D3
0x1402815b5  call    cs:__imp_W32GetUserSessionState
0x1402815bc  nop     dword ptr [rax+rax+00h]
0x1402815c1  mov     rcx, [rax+0F730h]
0x1402815c8  mov     eax, [rcx+94h]
0x1402815ce  cmp     dword ptr [rbp+var_30+4], eax
0x1402815d1  jz      short loc_1402815FB
0x1402815d3  call    cs:__imp_W32GetUserSessionState
0x1402815da  nop     dword ptr [rax+rax+00h]
0x1402815df  mov     rbx, [rax+0F728h]
0x1402815e6  call    cs:__imp_W32GetUserSessionState
0x1402815ed  nop     dword ptr [rax+rax+00h]
0x1402815f2  cmp     rbx, [rax+0F750h]
0x1402815f9  jnz     short loc_14028166B
0x1402815fb  call    cs:__imp_W32GetUserSessionState
0x140281602  nop     dword ptr [rax+rax+00h]
0x140281607  mov     r14d, [rax+0F724h]
0x14028160e  not     r14d
0x140281611  and     r14d, edi
0x140281614  and     r14d, 7
0x140281618  jz      loc_1402816C0
0x14028161e  call    cs:__imp_PsGetCurrentThreadId
0x140281625  nop     dword ptr [rax+rax+00h]
0x14028162a  mov     rbx, rax
0x14028162d  call    cs:__imp_W32GetUserSessionState
0x140281634  nop     dword ptr [rax+rax+00h]
0x140281639  cmp     ebx, [rax+0F708h]
0x14028163f  jz      short loc_1402816C0
0x140281641  test    sil, dil
0x140281644  jnz     short loc_140281665
0x140281646  call    cs:__imp_W32GetUserSessionState
0x14028164d  nop     dword ptr [rax+rax+00h]
0x140281652  cmp     r13, [rax+0F730h]
0x140281659  jz      short loc_140281665
0x14028165b  mov     eax, 80000011h
0x140281660  jmp     loc_1402812E4
0x140281665  test    r14b, 4
0x140281669  jz      short loc_1402816C0
0x14028166b  mov     eax, 0C000022Dh
0x140281670  jmp     loc_1402812E4
0x140281675  call    cs:__imp_W32GetUserSessionState
0x14028167c  nop     dword ptr [rax+rax+00h]
0x140281681  mov     rcx, r15; Thread
0x140281684  mov     rbx, [rax+0F750h]
0x14028168b  call    cs:__imp_PsGetThreadProcessId
0x140281692  nop     dword ptr [rax+rax+00h]
0x140281697  cmp     rax, rbx
0x14028169a  jz      short loc_1402816E2
0x14028169c  mov     rcx, r15
0x14028169f  call    W32GetThreadWin32Thread
0x1402816a4  mov     rbx, rax
0x1402816a7  bt      edi, 0Fh
0x1402816ab  jnb     short loc_1402816B5
  ... truncated ...
```
