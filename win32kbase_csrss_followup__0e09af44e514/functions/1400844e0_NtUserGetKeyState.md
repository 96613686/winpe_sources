# NtUserGetKeyState

- ea: `0x1400844e0`
- end: `0x140084902`
- name: `NtUserGetKeyState`
- size: `1058`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001bdf0`
- `0x14001bf30`
- `0x14001bf60`
- `0x14001c110`
- `0x14001c2a0`
- `0x14001c2d4`
- `0x14001c470`
- `0x1400325a4`
- `0x140033268`
- `0x140036118`
- `0x140048ae0`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x14008269c`
- `0x1400844e0`
- `0x140084908`
- `0x140084968`
- `0x140095350`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400848a7`
- `ntoskrnl!KeBugCheckEx` at `0x1400848a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400847ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400847ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400847c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400847c2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400848c2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400848c2`
- `ntoskrnl!ExReleaseFastResource` at `0x1400847b6`
- `ntoskrnl!ExReleaseFastResource` at `0x1400847b6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400845d0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140084746`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400847dd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400845d0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140084746`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400847dd`
- `WIN32K!W32GetUserSessionState` at `0x14008459e`
- `WIN32K!W32GetUserSessionState` at `0x140084628`
- `WIN32K!W32GetUserSessionState` at `0x14008464d`
- `WIN32K!W32GetUserSessionState` at `0x1400846db`
- `WIN32K!W32GetUserSessionState` at `0x140084706`
- `WIN32K!W32GetUserSessionState` at `0x140084737`
- `WIN32K!W32GetUserSessionState` at `0x1400847ce`
- `WIN32K!W32GetUserSessionState` at `0x14008459e`
- `WIN32K!W32GetUserSessionState` at `0x140084628`
- `WIN32K!W32GetUserSessionState` at `0x14008464d`
- `WIN32K!W32GetUserSessionState` at `0x1400846db`
- `WIN32K!W32GetUserSessionState` at `0x140084706`
- `WIN32K!W32GetUserSessionState` at `0x140084737`
- `WIN32K!W32GetUserSessionState` at `0x1400847ce`

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
    if ( *((_BYTE *)qword_1402531A0 + (int)i) == (_BYTE)a1 )
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
0x1400844e0  mov     rax, rsp
0x1400844e3  mov     [rax+8], rbx
0x1400844e7  mov     [rax+18h], rsi
0x1400844eb  push    rdi
0x1400844ec  push    r14
0x1400844ee  push    r15
0x1400844f0  sub     rsp, 60h
0x1400844f4  mov     r14d, ecx
0x1400844f7  mov     edx, 1
0x1400844fc  lea     rcx, [rax+10h]
0x140084500  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x140084505  mov     rsi, [rsp+78h+arg_8]
0x14008450d  mov     rax, [rsi+1D0h]
0x140084514  mov     edx, [rax+1FCh]
0x14008451a  test    dl, 1
0x14008451d  jnz     loc_140084737
0x140084523  xor     edi, edi
0x140084525  cmp     r14b, 20h ; ' '
0x140084529  jb      short loc_14008459E
0x14008452b  mov     ecx, edi
0x14008452d  cmp     ecx, 0Eh
0x140084530  jnb     short loc_140084546
0x140084532  movsxd  rax, ecx
0x140084535  lea     rdx, qword_1402531A0
0x14008453c  cmp     [rax+rdx], r14b
0x140084540  jz      short loc_14008459E
0x140084542  inc     ecx
0x140084544  jmp     short loc_14008452D
0x140084546  movzx   ecx, r14b
0x14008454a  sub     ecx, 5Bh ; '['
0x14008454d  jz      short loc_140084575
0x14008454f  sub     ecx, 1
0x140084552  jz      short loc_140084575
0x140084554  sub     ecx, 44h ; 'D'
0x140084557  jz      short loc_140084575
0x140084559  sub     ecx, 1
0x14008455c  jz      short loc_140084575
0x14008455e  sub     ecx, 1
0x140084561  jz      short loc_140084575
0x140084563  sub     ecx, 1
0x140084566  jz      short loc_140084575
0x140084568  sub     ecx, 1
0x14008456b  jz      short loc_140084575
0x14008456d  cmp     ecx, 1
0x140084570  mov     al, dil
0x140084573  jnz     short loc_140084577
0x140084575  mov     al, 1
0x140084577  test    al, al
0x140084579  jnz     short loc_14008459E
0x14008457b  call    ApiSetEditionIsGetKeyStateBlocked
0x140084580  test    eax, eax
0x140084582  jz      short loc_14008458C
0x140084584  movzx   ebx, di
0x140084587  jmp     loc_140084628
0x14008458c  mov     ecx, 1
0x140084591  call    ApiSetEditionIsGpqForegroundAccessibleCurrent
0x140084596  test    eax, eax
0x140084598  jz      loc_1400846DB
0x14008459e  call    cs:__imp_W32GetUserSessionState
0x1400845a5  nop     dword ptr [rax+rax+00h]
0x1400845aa  mov     rcx, [rax+4BE8h]
0x1400845b1  mov     eax, [rcx+8]
0x1400845b4  test    al, 1
0x1400845b6  jnz     loc_1400846C6
0x1400845bc  mov     al, dil
0x1400845bf  test    al, al
0x1400845c1  jnz     short loc_140084584
0x1400845c3  cmp     r14d, 100h
0x1400845ca  jnb     loc_1400846B7
0x1400845d0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400845d7  nop     dword ptr [rax+rax+00h]
0x1400845dc  test    rax, rax
0x1400845df  jz      loc_1400846D3
0x1400845e5  mov     rax, [rax]
0x1400845e8  movzx   ecx, r14b
0x1400845ec  shr     rcx, 2
0x1400845f0  mov     rax, [rax+1D0h]
0x1400845f7  movzx   r8d, byte ptr [rcx+rax+160h]
0x140084600  movzx   eax, r14b
0x140084604  and     eax, 3
0x140084607  lea     edx, [rax+rax]
0x14008460a  lea     ecx, [rdx+1]
0x14008460d  movzx   eax, cl
0x140084610  mov     ebx, edi
0x140084612  bt      r8d, eax
0x140084616  setb    bl
0x140084619  movzx   eax, bx
0x14008461c  or      bx, 0FF80h
0x140084620  bt      r8d, edx
0x140084624  cmovnb  bx, ax
0x140084628  call    cs:__imp_W32GetUserSessionState
0x14008462f  nop     dword ptr [rax+rax+00h]
0x140084634  mov     rcx, [rax+4BE8h]
0x14008463b  mov     eax, [rcx+8]
0x14008463e  test    al, 1
0x140084640  jnz     short loc_1400846AD
0x140084642  mov     al, dil
0x140084645  test    al, al
0x140084647  jnz     loc_1400848DF
0x14008464d  call    cs:__imp_W32GetUserSessionState
0x140084654  nop     dword ptr [rax+rax+00h]
0x140084659  mov     rcx, [rax+4CF8h]
0x140084660  mov     edx, [rcx+1B48h]
0x140084666  mov     rax, [rsi+200h]
0x14008466d  mov     [rax+70h], edx
0x140084670  mov     rax, [rsi+1D0h]
0x140084677  mov     rcx, [rsi+200h]
0x14008467e  mov     rax, [rax+160h]
0x140084685  mov     [rcx+74h], rax
0x140084689  jmp     short loc_14008468D
0x14008468b  xor     ebx, ebx
0x14008468d  call    UserSessionSwitchLeaveCritWithNonPaged
0x140084692  movsx   rax, bx
0x140084696  lea     r11, [rsp+78h+var_18]
0x14008469b  mov     rbx, [r11+20h]
0x14008469f  mov     rsi, [r11+30h]
0x1400846a3  mov     rsp, r11
0x1400846a6  pop     r15
0x1400846a8  pop     r14
0x1400846aa  pop     rdi
0x1400846ab  retn
0x1400846ad  mov     rcx, rsi; this
0x1400846b0  call    ?IsDelegationEnabledForThread@InputDelegation@@YA_NPEBUtagTHREADINFO@@@Z; InputDelegation::IsDelegationEnabledForThread(tagTHREADINFO const *)
0x1400846b5  jmp     short loc_140084645
0x1400846b7  mov     ecx, 57h ; 'W'
0x1400846bc  call    UserSetLastError
0x1400846c1  jmp     loc_140084584
0x1400846c6  mov     rcx, rsi; this
0x1400846c9  call    ?IsDelegationEnabledForThread@InputDelegation@@YA_NPEBUtagTHREADINFO@@@Z; InputDelegation::IsDelegationEnabledForThread(tagTHREADINFO const *)
0x1400846ce  jmp     loc_1400845BF
0x1400846d3  mov     rax, rdi
0x1400846d6  jmp     loc_1400845E8
0x1400846db  call    cs:__imp_W32GetUserSessionState
0x1400846e2  nop     dword ptr [rax+rax+00h]
0x1400846e7  mov     rcx, [rax+4A18h]
0x1400846ee  movsd   xmm0, qword ptr [rcx+220h]
0x1400846f6  mov     eax, [rcx+228h]
0x1400846fc  movsd   [rsp+78h+var_28], xmm0
0x140084702  mov     [rsp+78h+var_20], eax
0x140084706  call    cs:__imp_W32GetUserSessionState
0x14008470d  nop     dword ptr [rax+rax+00h]
0x140084712  mov     dword ptr [rsp+78h+BugCheckParameter4], 3
0x14008471a  lea     r9, [rsp+78h+var_28]
0x14008471f  mov     r8, [rax+4A18h]
0x140084726  xor     edx, edx
0x140084728  mov     rcx, rsi
0x14008472b  call    EtwTraceUIPIInputError
0x140084730  mov     ebx, edi
0x140084732  jmp     loc_140084628
0x140084737  call    cs:__imp_W32GetUserSessionState
0x14008473e  nop     dword ptr [rax+rax+00h]
0x140084743  mov     r15, rax
0x140084746  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14008474d  nop     dword ptr [rax+rax+00h]
0x140084752  mov     rbx, rax
0x140084755  mov     ecx, [rax+18h]
0x140084758  and     cl, 0Ch
0x14008475b  cmp     cl, 8
0x14008475e  jnz     loc_14008488E
0x140084764  call    UpdateDirtyVisRgnTrackers
0x140084769  lea     rcx, [r15+4C40h]
0x140084770  xor     edi, edi
0x140084772  mov     [rcx+64h], edi
0x140084775  mov     [rcx+50h], rdi
0x140084779  call    DestroyExclusiveUserCritDeferredUnlockList
0x14008477e  mov     [r15+10h], rdi
0x140084782  mov     rcx, [rbx]
0x140084785  test    rcx, rcx
0x140084788  jnz     loc_14008484B
0x14008478e  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x140084793  test    eax, eax
0x140084795  jnz     loc_140084895
0x14008479b  call    EtwTraceReleaseUserCrit
0x1400847a0  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x1400847a4  mov     eax, [rbx+18h]
0x1400847a7  test    al, 10h
0x1400847a9  jnz     loc_1400848B4
0x1400847af  lea     rdx, [rbx+20h]
0x1400847b3  mov     rcx, [r15]
0x1400847b6  call    cs:__imp_ExReleaseFastResource
0x1400847bd  nop     dword ptr [rax+rax+00h]
0x1400847c2  call    cs:__imp_KeLeaveCriticalRegion
0x1400847c9  nop     dword ptr [rax+rax+00h]
0x1400847ce  call    cs:__imp_W32GetUserSessionState
0x1400847d5  nop     dword ptr [rax+rax+00h]
0x1400847da  mov     r15, rax
0x1400847dd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400847e4  nop     dword ptr [rax+rax+00h]
0x1400847e9  mov     rbx, rax
0x1400847ec  call    cs:__imp_KeEnterCriticalRegion
0x1400847f3  nop     dword ptr [rax+rax+00h]
0x1400847f8  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400847fb  mov     rcx, [r15]; struct _FAST_ERESOURCE *
0x1400847fe  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140084803  cmp     [rbx], rdi
0x140084806  jz      loc_1400848D7
0x14008480c  call    IsThreadCrossSessionAttached
0x140084811  test    eax, eax
0x140084813  jnz     loc_1400848D3
0x140084819  mov     rcx, [rbx]
0x14008481c  mov     byte ptr [rcx+6ACh], 1
0x140084823  mov     [r15+10h], rcx
0x140084827  test    rcx, rcx
0x14008482a  jnz     short loc_140084862
0x14008482c  mov     rcx, [rsi+1D0h]
0x140084833  mov     eax, [rcx+1FCh]
0x140084839  test    al, 1
0x14008483b  jz      loc_140084525
0x140084841  call    PostUpdateKeyStateEvent
0x140084846  jmp     loc_140084525
0x14008484b  mov     eax, [rbx+18h]
0x14008484e  test    al, 2
0x140084850  jnz     loc_14008478E
0x140084856  mov     [rcx+6ACh], dil
0x14008485d  jmp     loc_14008478E
0x140084862  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x140084867  test    al, al
0x140084869  jz      short loc_14008482C
0x14008486b  lea     rbx, [r15+4C40h]
0x140084872  mov     rcx, rbx
0x140084875  call    DestroySharedUserCritDeferredUnlockList
0x14008487a  lea     rcx, [rbx+38h]
0x14008487e  call    DestroyDeferredUnlockObjectAssignmentList
0x140084883  lea     rcx, [rbx+28h]
0x140084887  call    DestroyDeferredUnlockObjectAssignmentList
0x14008488c  jmp     short loc_14008482C
0x14008488e  xor     edi, edi
0x140084890  jmp     loc_140084782
0x140084895  mov     edx, eax; BugCheckParameter1
0x140084897  mov     [rsp+78h+BugCheckParameter4], rdi; BugCheckParameter4
0x14008489c  xor     r9d, r9d; BugCheckParameter3
0x14008489f  xor     r8d, r8d; BugCheckParameter2
0x1400848a2  mov     ecx, 160h; BugCheckCode
0x1400848a7  call    cs:__imp_KeBugCheckEx
0x1400848b4  mov     rcx, gs:188h
0x1400848bd  mov     r8, rbx
0x1400848c0  xor     edx, edx
0x1400848c2  call    cs:__imp_PsSetThreadWin32Thread
0x1400848c9  nop     dword ptr [rax+rax+00h]
0x1400848ce  jmp     loc_1400847AF
0x1400848d3  or      dword ptr [rbx+18h], 2
0x1400848d7  mov     rcx, rdi
0x1400848da  jmp     loc_140084823
0x1400848df  mov     rax, [rsi+200h]
0x1400848e6  mov     [rax+70h], edi
0x1400848e9  mov     rax, [rsi+200h]
0x1400848f0  xor     ecx, ecx
0x1400848f2  mov     [rax+74h], rcx
0x1400848f6  jmp     loc_14008468D
0x1400848fb  xor     ebx, ebx
0x1400848fd  jmp     loc_14008468D
0x140238f2e  push    rbp
0x140238f30  sub     rsp, 30h
0x140238f34  mov     rbp, rdx
0x140238f37  mov     rax, [rcx]
0x140238f3a  mov     ecx, [rax]
0x140238f3c  mov     [rbp+30h], ecx
0x140238f3f  mov     ecx, [rbp+30h]
0x140238f42  call    SetLastNtError
0x140238f47  mov     dword ptr [rbp+38h], 1
0x140238f4e  mov     eax, [rbp+38h]
0x140238f51  add     rsp, 30h
0x140238f55  pop     rbp
0x140238f56  retn
0x140238f58  push    rbp
0x140238f5a  sub     rsp, 30h
0x140238f5e  mov     rbp, rdx
0x140238f61  mov     rax, [rcx]
0x140238f64  mov     ecx, [rax]
0x140238f66  mov     [rbp+40h], ecx
0x140238f69  mov     ecx, [rbp+40h]
0x140238f6c  call    SetLastNtError
0x140238f71  mov     dword ptr [rbp+48h], 1
0x140238f78  mov     eax, [rbp+48h]
0x140238f7b  add     rsp, 30h
0x140238f7f  pop     rbp
0x140238f80  retn
```
