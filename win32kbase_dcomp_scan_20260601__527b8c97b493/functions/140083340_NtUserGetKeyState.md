# NtUserGetKeyState

- ea: `0x140083340`
- end: `0x140083762`
- name: `NtUserGetKeyState`
- size: `1058`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140012c80`
- `0x140012dc0`
- `0x140012df0`
- `0x140012fa0`
- `0x140013130`
- `0x140013164`
- `0x140013300`
- `0x140029324`
- `0x140029fe8`
- `0x14002ce98`
- `0x14003fbd0`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400814fc`
- `0x140083340`
- `0x140083768`
- `0x1400837c8`
- `0x14009e550`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140083707`
- `ntoskrnl!KeBugCheckEx` at `0x140083707`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008364c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008364c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140083622`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140083622`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140083722`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140083722`
- `ntoskrnl!ExReleaseFastResource` at `0x140083616`
- `ntoskrnl!ExReleaseFastResource` at `0x140083616`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140083430`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400835a6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14008363d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140083430`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400835a6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14008363d`
- `WIN32K!W32GetUserSessionState` at `0x1400833fe`
- `WIN32K!W32GetUserSessionState` at `0x140083488`
- `WIN32K!W32GetUserSessionState` at `0x1400834ad`
- `WIN32K!W32GetUserSessionState` at `0x14008353b`
- `WIN32K!W32GetUserSessionState` at `0x140083566`
- `WIN32K!W32GetUserSessionState` at `0x140083597`
- `WIN32K!W32GetUserSessionState` at `0x14008362e`
- `WIN32K!W32GetUserSessionState` at `0x1400833fe`
- `WIN32K!W32GetUserSessionState` at `0x140083488`
- `WIN32K!W32GetUserSessionState` at `0x1400834ad`
- `WIN32K!W32GetUserSessionState` at `0x14008353b`
- `WIN32K!W32GetUserSessionState` at `0x140083566`
- `WIN32K!W32GetUserSessionState` at `0x140083597`
- `WIN32K!W32GetUserSessionState` at `0x14008362e`

## pseudocode

```c
__int64 __fastcall NtUserGetKeyState(unsigned int a1)
{
  __int64 i; // rcx
  InputDelegation *v3; // rsi
  char v4; // al
  __int64 v5; // rcx
  __int16 v6; // bx
  const struct tagTHREADINFO *v7; // rdx
  __int64 *v9; // rax
  __int64 v10; // rax
  int v11; // r8d
  unsigned int v12; // edx
  __int16 v13; // ax
  const struct tagTHREADINFO *v14; // rdx
  __int64 v15; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  __int64 UserSessionState; // r15
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax
  __int64 v24; // rcx
  __int64 v25; // r15
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // [rsp+50h] [rbp-28h] BYREF
  int v29; // [rsp+58h] [rbp-20h]
  InputDelegation *v30; // [rsp+88h] [rbp+10h] BYREF

  EnterLeaveCritShared::EnterLeaveCritShared(&v30, 1);
  v3 = v30;
  if ( (*(_DWORD *)(*((_QWORD *)v30 + 58) + 508LL) & 1) == 0 )
    goto LABEL_2;
  UserSessionState = W32GetUserSessionState(i);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread();
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(UserSessionState + 19620) = 0;
    *(_QWORD *)(UserSessionState + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(UserSessionState + 16) = 0;
  }
  if ( *(_QWORD *)CurrentThreadWin32Thread && (CurrentThreadWin32Thread[6] & 2) == 0 )
    *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 0;
  Count = AtomicExecutionCheck::GetCount();
  if ( Count )
    KeBugCheckEx(0x160u, Count, 0, 0, 0);
  EtwTraceReleaseUserCrit();
  CurrentThreadWin32Thread[6] &= 0xFFFFFFF1;
  if ( (CurrentThreadWin32Thread[6] & 0x10) != 0 )
    PsSetThreadWin32Thread(KeGetCurrentThread(), 0, CurrentThreadWin32Thread);
  ExReleaseFastResource(*(_QWORD *)UserSessionState, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
  v25 = W32GetUserSessionState(v24);
  v26 = PsGetCurrentThreadWin32Thread();
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)v25,
    (struct _W32THREADNONPAGED *)v26);
  if ( *(_QWORD *)v26 )
  {
    if ( !(unsigned int)IsThreadCrossSessionAttached() )
    {
      v27 = *(_QWORD *)v26;
      *(_BYTE *)(*(_QWORD *)v26 + 1708LL) = 1;
      goto LABEL_47;
    }
    *(_DWORD *)(v26 + 24) |= 2u;
  }
  v27 = 0;
LABEL_47:
  *(_QWORD *)(v25 + 16) = v27;
  if ( v27 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v27) )
  {
    DestroySharedUserCritDeferredUnlockList(v25 + 19520);
    DestroyDeferredUnlockObjectAssignmentList(v25 + 19576);
    DestroyDeferredUnlockObjectAssignmentList(v25 + 19560);
  }
  i = *((_QWORD *)v3 + 58);
  if ( (*(_DWORD *)(i + 508) & 1) != 0 )
    PostUpdateKeyStateEvent();
LABEL_2:
  if ( (unsigned __int8)a1 < 0x20u )
    goto LABEL_20;
  for ( i = 0; (unsigned int)i < 0xE; i = (unsigned int)(i + 1) )
  {
    if ( *((_BYTE *)qword_140254308 + (int)i) == (_BYTE)a1 )
      goto LABEL_20;
  }
  i = (unsigned int)(unsigned __int8)a1 - 91;
  if ( (unsigned __int8)a1 == 91
    || (i = (unsigned int)(unsigned __int8)a1 - 92, (unsigned __int8)a1 == 92)
    || (i = (unsigned int)(unsigned __int8)a1 - 160, (unsigned __int8)a1 == 160)
    || (i = (unsigned int)(unsigned __int8)a1 - 161, (unsigned __int8)a1 == 161)
    || (i = (unsigned int)(unsigned __int8)a1 - 162, (unsigned __int8)a1 == 162)
    || (i = (unsigned int)(unsigned __int8)a1 - 163, (unsigned __int8)a1 == 163)
    || (i = (unsigned int)(unsigned __int8)a1 - 164, (unsigned __int8)a1 == 164)
    || (v4 = 0, (unsigned __int8)a1 == 165) )
  {
    v4 = 1;
  }
  if ( v4 )
    goto LABEL_20;
  if ( (unsigned int)ApiSetEditionIsGetKeyStateBlocked() )
  {
LABEL_18:
    v6 = 0;
    goto LABEL_28;
  }
  if ( (unsigned int)ApiSetEditionIsGpqForegroundAccessibleCurrent(1) )
  {
LABEL_20:
    v5 = *(_QWORD *)(W32GetUserSessionState(i) + 19432);
    if ( (*(_DWORD *)(v5 + 8) & 1) != 0 && InputDelegation::IsDelegationEnabledForThread(v3, v7) )
      goto LABEL_18;
    if ( a1 >= 0x100 )
    {
      UserSetLastError(87);
      goto LABEL_18;
    }
    v9 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    v11 = *(unsigned __int8 *)(((unsigned __int64)(unsigned __int8)a1 >> 2) + *(_QWORD *)(v10 + 464) + 352);
    v12 = 2 * (a1 & 3);
    v5 = v12 + 1;
    v13 = _bittest(&v11, (unsigned __int8)(2 * (a1 & 3) + 1));
    v6 = v13 | 0xFF80;
    if ( !_bittest(&v11, v12) )
      v6 = v13;
  }
  else
  {
    v18 = *(_QWORD *)(W32GetUserSessionState(i) + 18968);
    v19 = *(_DWORD *)(v18 + 552);
    v28 = *(_QWORD *)(v18 + 544);
    v29 = v19;
    v20 = W32GetUserSessionState(v18);
    EtwTraceUIPIInputError((_DWORD)v3, 0, *(_QWORD *)(v20 + 18968), (unsigned int)&v28, 3);
    v6 = 0;
  }
LABEL_28:
  v15 = *(_QWORD *)(W32GetUserSessionState(v5) + 19432);
  if ( (*(_DWORD *)(v15 + 8) & 1) != 0 && InputDelegation::IsDelegationEnabledForThread(v3, v14) )
  {
    *(_DWORD *)(*((_QWORD *)v3 + 64) + 112LL) = 0;
    *(_QWORD *)(*((_QWORD *)v3 + 64) + 116LL) = 0;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)v3 + 64) + 112LL) = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v15) + 19704) + 6984LL);
    *(_QWORD *)(*((_QWORD *)v3 + 64) + 116LL) = *(_QWORD *)(*((_QWORD *)v3 + 58) + 352LL);
  }
  UserSessionSwitchLeaveCritWithNonPaged();
  return v6;
}

```

## disassembly

```asm
0x140083340  mov     rax, rsp
0x140083343  mov     [rax+8], rbx
0x140083347  mov     [rax+18h], rsi
0x14008334b  push    rdi
0x14008334c  push    r14
0x14008334e  push    r15
0x140083350  sub     rsp, 60h
0x140083354  mov     r14d, ecx
0x140083357  mov     edx, 1
0x14008335c  lea     rcx, [rax+10h]
0x140083360  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x140083365  mov     rsi, [rsp+78h+arg_8]
0x14008336d  mov     rax, [rsi+1D0h]
0x140083374  mov     edx, [rax+1FCh]
0x14008337a  test    dl, 1
0x14008337d  jnz     loc_140083597
0x140083383  xor     edi, edi
0x140083385  cmp     r14b, 20h ; ' '
0x140083389  jb      short loc_1400833FE
0x14008338b  mov     ecx, edi
0x14008338d  cmp     ecx, 0Eh
0x140083390  jnb     short loc_1400833A6
0x140083392  movsxd  rax, ecx
0x140083395  lea     rdx, qword_140254308
0x14008339c  cmp     [rax+rdx], r14b
0x1400833a0  jz      short loc_1400833FE
0x1400833a2  inc     ecx
0x1400833a4  jmp     short loc_14008338D
0x1400833a6  movzx   ecx, r14b
0x1400833aa  sub     ecx, 5Bh ; '['
0x1400833ad  jz      short loc_1400833D5
0x1400833af  sub     ecx, 1
0x1400833b2  jz      short loc_1400833D5
0x1400833b4  sub     ecx, 44h ; 'D'
0x1400833b7  jz      short loc_1400833D5
0x1400833b9  sub     ecx, 1
0x1400833bc  jz      short loc_1400833D5
0x1400833be  sub     ecx, 1
0x1400833c1  jz      short loc_1400833D5
0x1400833c3  sub     ecx, 1
0x1400833c6  jz      short loc_1400833D5
0x1400833c8  sub     ecx, 1
0x1400833cb  jz      short loc_1400833D5
0x1400833cd  cmp     ecx, 1
0x1400833d0  mov     al, dil
0x1400833d3  jnz     short loc_1400833D7
0x1400833d5  mov     al, 1
0x1400833d7  test    al, al
0x1400833d9  jnz     short loc_1400833FE
0x1400833db  call    ApiSetEditionIsGetKeyStateBlocked
0x1400833e0  test    eax, eax
0x1400833e2  jz      short loc_1400833EC
0x1400833e4  movzx   ebx, di
0x1400833e7  jmp     loc_140083488
0x1400833ec  mov     ecx, 1
0x1400833f1  call    ApiSetEditionIsGpqForegroundAccessibleCurrent
0x1400833f6  test    eax, eax
0x1400833f8  jz      loc_14008353B
0x1400833fe  call    cs:__imp_W32GetUserSessionState
0x140083405  nop     dword ptr [rax+rax+00h]
0x14008340a  mov     rcx, [rax+4BE8h]
0x140083411  mov     eax, [rcx+8]
0x140083414  test    al, 1
0x140083416  jnz     loc_140083526
0x14008341c  mov     al, dil
0x14008341f  test    al, al
0x140083421  jnz     short loc_1400833E4
0x140083423  cmp     r14d, 100h
0x14008342a  jnb     loc_140083517
0x140083430  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140083437  nop     dword ptr [rax+rax+00h]
0x14008343c  test    rax, rax
0x14008343f  jz      loc_140083533
0x140083445  mov     rax, [rax]
0x140083448  movzx   ecx, r14b
0x14008344c  shr     rcx, 2
0x140083450  mov     rax, [rax+1D0h]
0x140083457  movzx   r8d, byte ptr [rcx+rax+160h]
0x140083460  movzx   eax, r14b
0x140083464  and     eax, 3
0x140083467  lea     edx, [rax+rax]
0x14008346a  lea     ecx, [rdx+1]
0x14008346d  movzx   eax, cl
0x140083470  mov     ebx, edi
0x140083472  bt      r8d, eax
0x140083476  setb    bl
0x140083479  movzx   eax, bx
0x14008347c  or      bx, 0FF80h
0x140083480  bt      r8d, edx
0x140083484  cmovnb  bx, ax
0x140083488  call    cs:__imp_W32GetUserSessionState
0x14008348f  nop     dword ptr [rax+rax+00h]
0x140083494  mov     rcx, [rax+4BE8h]
0x14008349b  mov     eax, [rcx+8]
0x14008349e  test    al, 1
0x1400834a0  jnz     short loc_14008350D
0x1400834a2  mov     al, dil
0x1400834a5  test    al, al
0x1400834a7  jnz     loc_14008373F
0x1400834ad  call    cs:__imp_W32GetUserSessionState
0x1400834b4  nop     dword ptr [rax+rax+00h]
0x1400834b9  mov     rcx, [rax+4CF8h]
0x1400834c0  mov     edx, [rcx+1B48h]
0x1400834c6  mov     rax, [rsi+200h]
0x1400834cd  mov     [rax+70h], edx
0x1400834d0  mov     rax, [rsi+1D0h]
0x1400834d7  mov     rcx, [rsi+200h]
0x1400834de  mov     rax, [rax+160h]
0x1400834e5  mov     [rcx+74h], rax
0x1400834e9  jmp     short loc_1400834ED
0x1400834eb  xor     ebx, ebx
0x1400834ed  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400834f2  movsx   rax, bx
0x1400834f6  lea     r11, [rsp+78h+var_18]
0x1400834fb  mov     rbx, [r11+20h]
0x1400834ff  mov     rsi, [r11+30h]
0x140083503  mov     rsp, r11
0x140083506  pop     r15
0x140083508  pop     r14
0x14008350a  pop     rdi
0x14008350b  retn
0x14008350d  mov     rcx, rsi; this
0x140083510  call    ?IsDelegationEnabledForThread@InputDelegation@@YA_NPEBUtagTHREADINFO@@@Z; InputDelegation::IsDelegationEnabledForThread(tagTHREADINFO const *)
0x140083515  jmp     short loc_1400834A5
0x140083517  mov     ecx, 57h ; 'W'
0x14008351c  call    UserSetLastError
0x140083521  jmp     loc_1400833E4
0x140083526  mov     rcx, rsi; this
0x140083529  call    ?IsDelegationEnabledForThread@InputDelegation@@YA_NPEBUtagTHREADINFO@@@Z; InputDelegation::IsDelegationEnabledForThread(tagTHREADINFO const *)
0x14008352e  jmp     loc_14008341F
0x140083533  mov     rax, rdi
0x140083536  jmp     loc_140083448
0x14008353b  call    cs:__imp_W32GetUserSessionState
0x140083542  nop     dword ptr [rax+rax+00h]
0x140083547  mov     rcx, [rax+4A18h]
0x14008354e  movsd   xmm0, qword ptr [rcx+220h]
0x140083556  mov     eax, [rcx+228h]
0x14008355c  movsd   [rsp+78h+var_28], xmm0
0x140083562  mov     [rsp+78h+var_20], eax
0x140083566  call    cs:__imp_W32GetUserSessionState
0x14008356d  nop     dword ptr [rax+rax+00h]
0x140083572  mov     dword ptr [rsp+78h+BugCheckParameter4], 3
0x14008357a  lea     r9, [rsp+78h+var_28]
0x14008357f  mov     r8, [rax+4A18h]
0x140083586  xor     edx, edx
0x140083588  mov     rcx, rsi
0x14008358b  call    EtwTraceUIPIInputError
0x140083590  mov     ebx, edi
0x140083592  jmp     loc_140083488
0x140083597  call    cs:__imp_W32GetUserSessionState
0x14008359e  nop     dword ptr [rax+rax+00h]
0x1400835a3  mov     r15, rax
0x1400835a6  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400835ad  nop     dword ptr [rax+rax+00h]
0x1400835b2  mov     rbx, rax
0x1400835b5  mov     ecx, [rax+18h]
0x1400835b8  and     cl, 0Ch
0x1400835bb  cmp     cl, 8
0x1400835be  jnz     loc_1400836EE
0x1400835c4  call    UpdateDirtyVisRgnTrackers
0x1400835c9  lea     rcx, [r15+4C40h]
0x1400835d0  xor     edi, edi
0x1400835d2  mov     [rcx+64h], edi
0x1400835d5  mov     [rcx+50h], rdi
0x1400835d9  call    DestroyExclusiveUserCritDeferredUnlockList
0x1400835de  mov     [r15+10h], rdi
0x1400835e2  mov     rcx, [rbx]
0x1400835e5  test    rcx, rcx
0x1400835e8  jnz     loc_1400836AB
0x1400835ee  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1400835f3  test    eax, eax
0x1400835f5  jnz     loc_1400836F5
0x1400835fb  call    EtwTraceReleaseUserCrit
0x140083600  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x140083604  mov     eax, [rbx+18h]
0x140083607  test    al, 10h
0x140083609  jnz     loc_140083714
0x14008360f  lea     rdx, [rbx+20h]
0x140083613  mov     rcx, [r15]
0x140083616  call    cs:__imp_ExReleaseFastResource
0x14008361d  nop     dword ptr [rax+rax+00h]
0x140083622  call    cs:__imp_KeLeaveCriticalRegion
0x140083629  nop     dword ptr [rax+rax+00h]
0x14008362e  call    cs:__imp_W32GetUserSessionState
0x140083635  nop     dword ptr [rax+rax+00h]
0x14008363a  mov     r15, rax
0x14008363d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140083644  nop     dword ptr [rax+rax+00h]
0x140083649  mov     rbx, rax
0x14008364c  call    cs:__imp_KeEnterCriticalRegion
0x140083653  nop     dword ptr [rax+rax+00h]
0x140083658  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14008365b  mov     rcx, [r15]; struct _FAST_ERESOURCE *
0x14008365e  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140083663  cmp     [rbx], rdi
0x140083666  jz      loc_140083737
0x14008366c  call    IsThreadCrossSessionAttached
0x140083671  test    eax, eax
0x140083673  jnz     loc_140083733
0x140083679  mov     rcx, [rbx]
0x14008367c  mov     byte ptr [rcx+6ACh], 1
0x140083683  mov     [r15+10h], rcx
0x140083687  test    rcx, rcx
0x14008368a  jnz     short loc_1400836C2
0x14008368c  mov     rcx, [rsi+1D0h]
0x140083693  mov     eax, [rcx+1FCh]
0x140083699  test    al, 1
0x14008369b  jz      loc_140083385
0x1400836a1  call    PostUpdateKeyStateEvent
0x1400836a6  jmp     loc_140083385
0x1400836ab  mov     eax, [rbx+18h]
0x1400836ae  test    al, 2
0x1400836b0  jnz     loc_1400835EE
0x1400836b6  mov     [rcx+6ACh], dil
0x1400836bd  jmp     loc_1400835EE
0x1400836c2  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400836c7  test    al, al
0x1400836c9  jz      short loc_14008368C
0x1400836cb  lea     rbx, [r15+4C40h]
0x1400836d2  mov     rcx, rbx
0x1400836d5  call    DestroySharedUserCritDeferredUnlockList
0x1400836da  lea     rcx, [rbx+38h]
0x1400836de  call    DestroyDeferredUnlockObjectAssignmentList
0x1400836e3  lea     rcx, [rbx+28h]
0x1400836e7  call    DestroyDeferredUnlockObjectAssignmentList
0x1400836ec  jmp     short loc_14008368C
0x1400836ee  xor     edi, edi
0x1400836f0  jmp     loc_1400835E2
0x1400836f5  mov     edx, eax; BugCheckParameter1
0x1400836f7  mov     [rsp+78h+BugCheckParameter4], rdi; BugCheckParameter4
0x1400836fc  xor     r9d, r9d; BugCheckParameter3
0x1400836ff  xor     r8d, r8d; BugCheckParameter2
0x140083702  mov     ecx, 160h; BugCheckCode
0x140083707  call    cs:__imp_KeBugCheckEx
0x140083714  mov     rcx, gs:188h
0x14008371d  mov     r8, rbx
0x140083720  xor     edx, edx
0x140083722  call    cs:__imp_PsSetThreadWin32Thread
0x140083729  nop     dword ptr [rax+rax+00h]
0x14008372e  jmp     loc_14008360F
0x140083733  or      dword ptr [rbx+18h], 2
0x140083737  mov     rcx, rdi
0x14008373a  jmp     loc_140083683
0x14008373f  mov     rax, [rsi+200h]
0x140083746  mov     [rax+70h], edi
0x140083749  mov     rax, [rsi+200h]
0x140083750  xor     ecx, ecx
0x140083752  mov     [rax+74h], rcx
0x140083756  jmp     loc_1400834ED
0x14008375b  xor     ebx, ebx
0x14008375d  jmp     loc_1400834ED
0x1402398ee  push    rbp
0x1402398f0  sub     rsp, 30h
0x1402398f4  mov     rbp, rdx
0x1402398f7  mov     rax, [rcx]
0x1402398fa  mov     ecx, [rax]
0x1402398fc  mov     [rbp+30h], ecx
0x1402398ff  mov     ecx, [rbp+30h]
0x140239902  call    SetLastNtError
0x140239907  mov     dword ptr [rbp+38h], 1
0x14023990e  mov     eax, [rbp+38h]
0x140239911  add     rsp, 30h
0x140239915  pop     rbp
0x140239916  retn
0x140239918  push    rbp
0x14023991a  sub     rsp, 30h
0x14023991e  mov     rbp, rdx
0x140239921  mov     rax, [rcx]
0x140239924  mov     ecx, [rax]
0x140239926  mov     [rbp+40h], ecx
0x140239929  mov     ecx, [rbp+40h]
0x14023992c  call    SetLastNtError
0x140239931  mov     dword ptr [rbp+48h], 1
0x140239938  mov     eax, [rbp+48h]
0x14023993b  add     rsp, 30h
0x14023993f  pop     rbp
0x140239940  retn
```
