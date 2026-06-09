# NtUserGetKeyState

- ea: `0x14002a440`
- end: `0x14002a862`
- name: `NtUserGetKeyState`
- size: `1058`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140029710`
- `0x140029850`
- `0x140029880`
- `0x140029a30`
- `0x140029bc0`
- `0x140029bf4`
- `0x140029d90`
- `0x14002a440`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x140059acc`
- `0x140068450`
- `0x14006f3a4`
- `0x1400700d8`
- `0x14007a340`
- `0x1400cbdbc`
- `0x1400cc39c`
- `0x1400d7988`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14002a807`
- `ntoskrnl!KeBugCheckEx` at `0x14002a807`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002a74c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002a74c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a722`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a722`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14002a822`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14002a822`
- `ntoskrnl!ExReleaseFastResource` at `0x14002a716`
- `ntoskrnl!ExReleaseFastResource` at `0x14002a716`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a530`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a6a6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a73d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a530`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a6a6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002a73d`
- `WIN32K!W32GetUserSessionState` at `0x14002a4fe`
- `WIN32K!W32GetUserSessionState` at `0x14002a588`
- `WIN32K!W32GetUserSessionState` at `0x14002a5ad`
- `WIN32K!W32GetUserSessionState` at `0x14002a63b`
- `WIN32K!W32GetUserSessionState` at `0x14002a666`
- `WIN32K!W32GetUserSessionState` at `0x14002a697`
- `WIN32K!W32GetUserSessionState` at `0x14002a72e`
- `WIN32K!W32GetUserSessionState` at `0x14002a4fe`
- `WIN32K!W32GetUserSessionState` at `0x14002a588`
- `WIN32K!W32GetUserSessionState` at `0x14002a5ad`
- `WIN32K!W32GetUserSessionState` at `0x14002a63b`
- `WIN32K!W32GetUserSessionState` at `0x14002a666`
- `WIN32K!W32GetUserSessionState` at `0x14002a697`
- `WIN32K!W32GetUserSessionState` at `0x14002a72e`

## pseudocode

```c
__int64 __fastcall NtUserGetKeyState(unsigned int a1)
{
  __int64 i; // rcx
  InputDelegation *v3; // rsi
  __int64 *v4; // rdx
  char v5; // al
  const struct tagTHREADINFO *v6; // rdx
  __int64 v7; // rcx
  __int16 v8; // bx
  __int64 *v10; // rax
  __int64 v11; // rax
  int v12; // r8d
  __int16 v13; // ax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 UserSessionState; // r15
  __int64 v24; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int Count; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r15
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // [rsp+50h] [rbp-28h] BYREF
  int v37; // [rsp+58h] [rbp-20h]
  InputDelegation *v38; // [rsp+88h] [rbp+10h] BYREF

  EnterLeaveCritShared::EnterLeaveCritShared(&v38, 1);
  v3 = v38;
  v4 = (__int64 *)*(unsigned int *)(*((_QWORD *)v38 + 58) + 508LL);
  if ( ((unsigned __int8)v4 & 1) == 0 )
    goto LABEL_2;
  UserSessionState = W32GetUserSessionState(i, v4);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v24);
  v26 = *(unsigned int *)(CurrentThreadWin32Thread + 24);
  LOBYTE(v26) = v26 & 0xC;
  if ( (_BYTE)v26 == 8 )
  {
    UpdateDirtyVisRgnTrackers(v26);
    *(_DWORD *)(UserSessionState + 19620) = 0;
    *(_QWORD *)(UserSessionState + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList(UserSessionState + 19520);
    *(_QWORD *)(UserSessionState + 16) = 0;
  }
  v27 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread && (*(_DWORD *)(CurrentThreadWin32Thread + 24) & 2) == 0 )
    *(_BYTE *)(v27 + 1708) = 0;
  Count = AtomicExecutionCheck::GetCount(v27);
  if ( Count )
    KeBugCheckEx(0x160u, Count, 0, 0, 0);
  EtwTraceReleaseUserCrit(v29);
  *(_DWORD *)(CurrentThreadWin32Thread + 24) &= 0xFFFFFFF1;
  if ( (*(_DWORD *)(CurrentThreadWin32Thread + 24) & 0x10) != 0 )
    PsSetThreadWin32Thread(KeGetCurrentThread(), 0, CurrentThreadWin32Thread);
  ExReleaseFastResource(*(_QWORD *)UserSessionState, CurrentThreadWin32Thread + 32);
  KeLeaveCriticalRegion();
  v32 = W32GetUserSessionState(v31, v30);
  v34 = PsGetCurrentThreadWin32Thread(v33);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)v32,
    (struct _W32THREADNONPAGED *)v34);
  if ( *(_QWORD *)v34 )
  {
    if ( !IsThreadCrossSessionAttached() )
    {
      v35 = *(_QWORD *)v34;
      *(_BYTE *)(*(_QWORD *)v34 + 1708LL) = 1;
      goto LABEL_47;
    }
    *(_DWORD *)(v34 + 24) |= 2u;
  }
  v35 = 0;
LABEL_47:
  *(_QWORD *)(v32 + 16) = v35;
  if ( v35 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v35) )
  {
    DestroySharedUserCritDeferredUnlockList(v32 + 19520);
    DestroyDeferredUnlockObjectAssignmentList(v32 + 19576);
    DestroyDeferredUnlockObjectAssignmentList(v32 + 19560);
  }
  i = *((_QWORD *)v3 + 58);
  if ( (*(_DWORD *)(i + 508) & 1) != 0 )
    PostUpdateKeyStateEvent();
LABEL_2:
  if ( (unsigned __int8)a1 < 0x20u )
    goto LABEL_20;
  for ( i = 0; (unsigned int)i < 0xE; i = (unsigned int)(i + 1) )
  {
    v4 = qword_140252358;
    if ( *((_BYTE *)qword_140252358 + (int)i) == (_BYTE)a1 )
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
    || (v5 = 0, (unsigned __int8)a1 == 165) )
  {
    v5 = 1;
  }
  if ( v5 )
    goto LABEL_20;
  if ( (unsigned int)ApiSetEditionIsGetKeyStateBlocked() )
  {
LABEL_18:
    v8 = 0;
    goto LABEL_28;
  }
  if ( (unsigned int)ApiSetEditionIsGpqForegroundAccessibleCurrent(1) )
  {
LABEL_20:
    v7 = *(_QWORD *)(W32GetUserSessionState(i, v4) + 19432);
    if ( (*(_DWORD *)(v7 + 8) & 1) != 0 && InputDelegation::IsDelegationEnabledForThread(v3, v6) )
      goto LABEL_18;
    if ( a1 >= 0x100 )
    {
      UserSetLastError(87);
      goto LABEL_18;
    }
    v10 = (__int64 *)PsGetCurrentThreadWin32Thread(v7);
    if ( v10 )
      v11 = *v10;
    else
      v11 = 0;
    v12 = *(unsigned __int8 *)(((unsigned __int64)(unsigned __int8)a1 >> 2) + *(_QWORD *)(v11 + 464) + 352);
    v6 = (const struct tagTHREADINFO *)(2 * (a1 & 3));
    v7 = (unsigned int)((_DWORD)v6 + 1);
    v13 = _bittest(&v12, (unsigned __int8)(2 * (a1 & 3) + 1));
    v8 = v13 | 0xFF80;
    if ( !_bittest(&v12, (unsigned int)v6) )
      v8 = v13;
  }
  else
  {
    v19 = *(_QWORD *)(W32GetUserSessionState(i, v4) + 18968);
    v20 = *(_DWORD *)(v19 + 552);
    v36 = *(_QWORD *)(v19 + 544);
    v37 = v20;
    v22 = W32GetUserSessionState(v19, v21);
    EtwTraceUIPIInputError((_DWORD)v3, 0, *(_QWORD *)(v22 + 18968), (unsigned int)&v36, 3);
    v8 = 0;
  }
LABEL_28:
  v15 = *(_QWORD *)(W32GetUserSessionState(v7, v6) + 19432);
  if ( (*(_DWORD *)(v15 + 8) & 1) != 0
    && InputDelegation::IsDelegationEnabledForThread(v3, (const struct tagTHREADINFO *)v14) )
  {
    *(_DWORD *)(*((_QWORD *)v3 + 64) + 112LL) = 0;
    v17 = 0;
    *(_QWORD *)(*((_QWORD *)v3 + 64) + 116LL) = 0;
  }
  else
  {
    v14 = *(unsigned int *)(*(_QWORD *)(W32GetUserSessionState(v15, v14) + 19704) + 6984LL);
    *(_DWORD *)(*((_QWORD *)v3 + 64) + 112LL) = v14;
    v17 = *((_QWORD *)v3 + 64);
    *(_QWORD *)(v17 + 116) = *(_QWORD *)(*((_QWORD *)v3 + 58) + 352LL);
  }
  UserSessionSwitchLeaveCritWithNonPaged(v17, v14);
  return v8;
}

```

## disassembly

```asm
0x14002a440  mov     rax, rsp
0x14002a443  mov     [rax+8], rbx
0x14002a447  mov     [rax+18h], rsi
0x14002a44b  push    rdi
0x14002a44c  push    r14
0x14002a44e  push    r15
0x14002a450  sub     rsp, 60h
0x14002a454  mov     r14d, ecx
0x14002a457  mov     edx, 1
0x14002a45c  lea     rcx, [rax+10h]
0x14002a460  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x14002a465  mov     rsi, [rsp+78h+arg_8]
0x14002a46d  mov     rax, [rsi+1D0h]
0x14002a474  mov     edx, [rax+1FCh]
0x14002a47a  test    dl, 1
0x14002a47d  jnz     loc_14002A697
0x14002a483  xor     edi, edi
0x14002a485  cmp     r14b, 20h ; ' '
0x14002a489  jb      short loc_14002A4FE
0x14002a48b  mov     ecx, edi
0x14002a48d  cmp     ecx, 0Eh
0x14002a490  jnb     short loc_14002A4A6
0x14002a492  movsxd  rax, ecx
0x14002a495  lea     rdx, qword_140252358
0x14002a49c  cmp     [rax+rdx], r14b
0x14002a4a0  jz      short loc_14002A4FE
0x14002a4a2  inc     ecx
0x14002a4a4  jmp     short loc_14002A48D
0x14002a4a6  movzx   ecx, r14b
0x14002a4aa  sub     ecx, 5Bh ; '['
0x14002a4ad  jz      short loc_14002A4D5
0x14002a4af  sub     ecx, 1
0x14002a4b2  jz      short loc_14002A4D5
0x14002a4b4  sub     ecx, 44h ; 'D'
0x14002a4b7  jz      short loc_14002A4D5
0x14002a4b9  sub     ecx, 1
0x14002a4bc  jz      short loc_14002A4D5
0x14002a4be  sub     ecx, 1
0x14002a4c1  jz      short loc_14002A4D5
0x14002a4c3  sub     ecx, 1
0x14002a4c6  jz      short loc_14002A4D5
0x14002a4c8  sub     ecx, 1
0x14002a4cb  jz      short loc_14002A4D5
0x14002a4cd  cmp     ecx, 1
0x14002a4d0  mov     al, dil
0x14002a4d3  jnz     short loc_14002A4D7
0x14002a4d5  mov     al, 1
0x14002a4d7  test    al, al
0x14002a4d9  jnz     short loc_14002A4FE
0x14002a4db  call    ApiSetEditionIsGetKeyStateBlocked
0x14002a4e0  test    eax, eax
0x14002a4e2  jz      short loc_14002A4EC
0x14002a4e4  movzx   ebx, di
0x14002a4e7  jmp     loc_14002A588
0x14002a4ec  mov     ecx, 1
0x14002a4f1  call    ApiSetEditionIsGpqForegroundAccessibleCurrent
0x14002a4f6  test    eax, eax
0x14002a4f8  jz      loc_14002A63B
0x14002a4fe  call    cs:__imp_W32GetUserSessionState
0x14002a505  nop     dword ptr [rax+rax+00h]
0x14002a50a  mov     rcx, [rax+4BE8h]
0x14002a511  mov     eax, [rcx+8]
0x14002a514  test    al, 1
0x14002a516  jnz     loc_14002A626
0x14002a51c  mov     al, dil
0x14002a51f  test    al, al
0x14002a521  jnz     short loc_14002A4E4
0x14002a523  cmp     r14d, 100h
0x14002a52a  jnb     loc_14002A617
0x14002a530  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002a537  nop     dword ptr [rax+rax+00h]
0x14002a53c  test    rax, rax
0x14002a53f  jz      loc_14002A633
0x14002a545  mov     rax, [rax]
0x14002a548  movzx   ecx, r14b
0x14002a54c  shr     rcx, 2
0x14002a550  mov     rax, [rax+1D0h]
0x14002a557  movzx   r8d, byte ptr [rcx+rax+160h]
0x14002a560  movzx   eax, r14b
0x14002a564  and     eax, 3
0x14002a567  lea     edx, [rax+rax]
0x14002a56a  lea     ecx, [rdx+1]
0x14002a56d  movzx   eax, cl
0x14002a570  mov     ebx, edi
0x14002a572  bt      r8d, eax
0x14002a576  setb    bl
0x14002a579  movzx   eax, bx
0x14002a57c  or      bx, 0FF80h
0x14002a580  bt      r8d, edx
0x14002a584  cmovnb  bx, ax
0x14002a588  call    cs:__imp_W32GetUserSessionState
0x14002a58f  nop     dword ptr [rax+rax+00h]
0x14002a594  mov     rcx, [rax+4BE8h]
0x14002a59b  mov     eax, [rcx+8]
0x14002a59e  test    al, 1
0x14002a5a0  jnz     short loc_14002A60D
0x14002a5a2  mov     al, dil
0x14002a5a5  test    al, al
0x14002a5a7  jnz     loc_14002A83F
0x14002a5ad  call    cs:__imp_W32GetUserSessionState
0x14002a5b4  nop     dword ptr [rax+rax+00h]
0x14002a5b9  mov     rcx, [rax+4CF8h]
0x14002a5c0  mov     edx, [rcx+1B48h]
0x14002a5c6  mov     rax, [rsi+200h]
0x14002a5cd  mov     [rax+70h], edx
0x14002a5d0  mov     rax, [rsi+1D0h]
0x14002a5d7  mov     rcx, [rsi+200h]
0x14002a5de  mov     rax, [rax+160h]
0x14002a5e5  mov     [rcx+74h], rax
0x14002a5e9  jmp     short loc_14002A5ED
0x14002a5eb  xor     ebx, ebx
0x14002a5ed  call    UserSessionSwitchLeaveCritWithNonPaged
0x14002a5f2  movsx   rax, bx
0x14002a5f6  lea     r11, [rsp+78h+var_18]
0x14002a5fb  mov     rbx, [r11+20h]
0x14002a5ff  mov     rsi, [r11+30h]
0x14002a603  mov     rsp, r11
0x14002a606  pop     r15
0x14002a608  pop     r14
0x14002a60a  pop     rdi
0x14002a60b  retn
0x14002a60d  mov     rcx, rsi; this
0x14002a610  call    ?IsDelegationEnabledForThread@InputDelegation@@YA_NPEBUtagTHREADINFO@@@Z; InputDelegation::IsDelegationEnabledForThread(tagTHREADINFO const *)
0x14002a615  jmp     short loc_14002A5A5
0x14002a617  mov     ecx, 57h ; 'W'
0x14002a61c  call    UserSetLastError
0x14002a621  jmp     loc_14002A4E4
0x14002a626  mov     rcx, rsi; this
0x14002a629  call    ?IsDelegationEnabledForThread@InputDelegation@@YA_NPEBUtagTHREADINFO@@@Z; InputDelegation::IsDelegationEnabledForThread(tagTHREADINFO const *)
0x14002a62e  jmp     loc_14002A51F
0x14002a633  mov     rax, rdi
0x14002a636  jmp     loc_14002A548
0x14002a63b  call    cs:__imp_W32GetUserSessionState
0x14002a642  nop     dword ptr [rax+rax+00h]
0x14002a647  mov     rcx, [rax+4A18h]
0x14002a64e  movsd   xmm0, qword ptr [rcx+220h]
0x14002a656  mov     eax, [rcx+228h]
0x14002a65c  movsd   [rsp+78h+var_28], xmm0
0x14002a662  mov     [rsp+78h+var_20], eax
0x14002a666  call    cs:__imp_W32GetUserSessionState
0x14002a66d  nop     dword ptr [rax+rax+00h]
0x14002a672  mov     dword ptr [rsp+78h+BugCheckParameter4], 3
0x14002a67a  lea     r9, [rsp+78h+var_28]
0x14002a67f  mov     r8, [rax+4A18h]
0x14002a686  xor     edx, edx
0x14002a688  mov     rcx, rsi
0x14002a68b  call    EtwTraceUIPIInputError
0x14002a690  mov     ebx, edi
0x14002a692  jmp     loc_14002A588
0x14002a697  call    cs:__imp_W32GetUserSessionState
0x14002a69e  nop     dword ptr [rax+rax+00h]
0x14002a6a3  mov     r15, rax
0x14002a6a6  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002a6ad  nop     dword ptr [rax+rax+00h]
0x14002a6b2  mov     rbx, rax
0x14002a6b5  mov     ecx, [rax+18h]
0x14002a6b8  and     cl, 0Ch
0x14002a6bb  cmp     cl, 8
0x14002a6be  jnz     loc_14002A7EE
0x14002a6c4  call    UpdateDirtyVisRgnTrackers
0x14002a6c9  lea     rcx, [r15+4C40h]
0x14002a6d0  xor     edi, edi
0x14002a6d2  mov     [rcx+64h], edi
0x14002a6d5  mov     [rcx+50h], rdi
0x14002a6d9  call    DestroyExclusiveUserCritDeferredUnlockList
0x14002a6de  mov     [r15+10h], rdi
0x14002a6e2  mov     rcx, [rbx]
0x14002a6e5  test    rcx, rcx
0x14002a6e8  jnz     loc_14002A7AB
0x14002a6ee  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x14002a6f3  test    eax, eax
0x14002a6f5  jnz     loc_14002A7F5
0x14002a6fb  call    EtwTraceReleaseUserCrit
0x14002a700  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14002a704  mov     eax, [rbx+18h]
0x14002a707  test    al, 10h
0x14002a709  jnz     loc_14002A814
0x14002a70f  lea     rdx, [rbx+20h]
0x14002a713  mov     rcx, [r15]
0x14002a716  call    cs:__imp_ExReleaseFastResource
0x14002a71d  nop     dword ptr [rax+rax+00h]
0x14002a722  call    cs:__imp_KeLeaveCriticalRegion
0x14002a729  nop     dword ptr [rax+rax+00h]
0x14002a72e  call    cs:__imp_W32GetUserSessionState
0x14002a735  nop     dword ptr [rax+rax+00h]
0x14002a73a  mov     r15, rax
0x14002a73d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002a744  nop     dword ptr [rax+rax+00h]
0x14002a749  mov     rbx, rax
0x14002a74c  call    cs:__imp_KeEnterCriticalRegion
0x14002a753  nop     dword ptr [rax+rax+00h]
0x14002a758  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14002a75b  mov     rcx, [r15]; struct _FAST_ERESOURCE *
0x14002a75e  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14002a763  cmp     [rbx], rdi
0x14002a766  jz      loc_14002A837
0x14002a76c  call    IsThreadCrossSessionAttached
0x14002a771  test    eax, eax
0x14002a773  jnz     loc_14002A833
0x14002a779  mov     rcx, [rbx]
0x14002a77c  mov     byte ptr [rcx+6ACh], 1
0x14002a783  mov     [r15+10h], rcx
0x14002a787  test    rcx, rcx
0x14002a78a  jnz     short loc_14002A7C2
0x14002a78c  mov     rcx, [rsi+1D0h]
0x14002a793  mov     eax, [rcx+1FCh]
0x14002a799  test    al, 1
0x14002a79b  jz      loc_14002A485
0x14002a7a1  call    PostUpdateKeyStateEvent
0x14002a7a6  jmp     loc_14002A485
0x14002a7ab  mov     eax, [rbx+18h]
0x14002a7ae  test    al, 2
0x14002a7b0  jnz     loc_14002A6EE
0x14002a7b6  mov     [rcx+6ACh], dil
0x14002a7bd  jmp     loc_14002A6EE
0x14002a7c2  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x14002a7c7  test    al, al
0x14002a7c9  jz      short loc_14002A78C
0x14002a7cb  lea     rbx, [r15+4C40h]
0x14002a7d2  mov     rcx, rbx
0x14002a7d5  call    DestroySharedUserCritDeferredUnlockList
0x14002a7da  lea     rcx, [rbx+38h]
0x14002a7de  call    DestroyDeferredUnlockObjectAssignmentList
0x14002a7e3  lea     rcx, [rbx+28h]
0x14002a7e7  call    DestroyDeferredUnlockObjectAssignmentList
0x14002a7ec  jmp     short loc_14002A78C
0x14002a7ee  xor     edi, edi
0x14002a7f0  jmp     loc_14002A6E2
0x14002a7f5  mov     edx, eax; BugCheckParameter1
0x14002a7f7  mov     [rsp+78h+BugCheckParameter4], rdi; BugCheckParameter4
0x14002a7fc  xor     r9d, r9d; BugCheckParameter3
0x14002a7ff  xor     r8d, r8d; BugCheckParameter2
0x14002a802  mov     ecx, 160h; BugCheckCode
0x14002a807  call    cs:__imp_KeBugCheckEx
0x14002a814  mov     rcx, gs:188h
0x14002a81d  mov     r8, rbx
0x14002a820  xor     edx, edx
0x14002a822  call    cs:__imp_PsSetThreadWin32Thread
0x14002a829  nop     dword ptr [rax+rax+00h]
0x14002a82e  jmp     loc_14002A70F
0x14002a833  or      dword ptr [rbx+18h], 2
0x14002a837  mov     rcx, rdi
0x14002a83a  jmp     loc_14002A783
0x14002a83f  mov     rax, [rsi+200h]
0x14002a846  mov     [rax+70h], edi
0x14002a849  mov     rax, [rsi+200h]
0x14002a850  xor     ecx, ecx
0x14002a852  mov     [rax+74h], rcx
0x14002a856  jmp     loc_14002A5ED
0x14002a85b  xor     ebx, ebx
0x14002a85d  jmp     loc_14002A5ED
0x14023935e  push    rbp
0x140239360  sub     rsp, 30h
0x140239364  mov     rbp, rdx
0x140239367  mov     rax, [rcx]
0x14023936a  mov     ecx, [rax]
0x14023936c  mov     [rbp+30h], ecx
0x14023936f  mov     ecx, [rbp+30h]
0x140239372  call    SetLastNtError
0x140239377  mov     dword ptr [rbp+38h], 1
0x14023937e  mov     eax, [rbp+38h]
0x140239381  add     rsp, 30h
0x140239385  pop     rbp
0x140239386  retn
0x140239388  push    rbp
0x14023938a  sub     rsp, 30h
0x14023938e  mov     rbp, rdx
0x140239391  mov     rax, [rcx]
0x140239394  mov     ecx, [rax]
0x140239396  mov     [rbp+40h], ecx
0x140239399  mov     ecx, [rbp+40h]
0x14023939c  call    SetLastNtError
0x1402393a1  mov     dword ptr [rbp+48h], 1
0x1402393a8  mov     eax, [rbp+48h]
0x1402393ab  add     rsp, 30h
0x1402393af  pop     rbp
0x1402393b0  retn
```
