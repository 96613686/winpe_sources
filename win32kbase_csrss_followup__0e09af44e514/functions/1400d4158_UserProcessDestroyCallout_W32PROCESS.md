# UserProcessDestroyCallout(_W32PROCESS *)

- ea: `0x1400d4158`
- end: `0x1400d43cf`
- name: `?UserProcessDestroyCallout@@YAXPEAU_W32PROCESS@@@Z`
- size: `631`
- prototype: `void __fastcall(struct _W32PROCESS *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14014bc30`

## callees

- `0x1400173d0`
- `0x14001bdf0`
- `0x14001c470`
- `0x14001e528`
- `0x14001e554`
- `0x140036118`
- `0x140072a90`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x1400984d0`
- `0x1400d34cc`
- `0x1400d4158`
- `0x1401b8414`
- `0x140215890`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4186`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d4186`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d4177`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d41fd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d4177`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d41fd`
- `WIN32K!W32GetSessionState` at `0x1400d4357`
- `WIN32K!W32GetSessionState` at `0x1400d4395`
- `WIN32K!W32GetSessionState` at `0x1400d4357`
- `WIN32K!W32GetSessionState` at `0x1400d4395`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d420f`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d420f`
- `WIN32K!W32GetUserSessionState` at `0x1400d4168`
- `WIN32K!W32GetUserSessionState` at `0x1400d422e`
- `WIN32K!W32GetUserSessionState` at `0x1400d4293`
- `WIN32K!W32GetUserSessionState` at `0x1400d42ef`
- `WIN32K!W32GetUserSessionState` at `0x1400d42fe`
- `WIN32K!W32GetUserSessionState` at `0x1400d4332`
- `WIN32K!W32GetUserSessionState` at `0x1400d4344`
- `WIN32K!W32GetUserSessionState` at `0x1400d4168`
- `WIN32K!W32GetUserSessionState` at `0x1400d422e`
- `WIN32K!W32GetUserSessionState` at `0x1400d4293`
- `WIN32K!W32GetUserSessionState` at `0x1400d42ef`
- `WIN32K!W32GetUserSessionState` at `0x1400d42fe`
- `WIN32K!W32GetUserSessionState` at `0x1400d4332`
- `WIN32K!W32GetUserSessionState` at `0x1400d4344`

## pseudocode

```c
void __fastcall UserProcessDestroyCallout(struct _W32PROCESS *a1)
{
  __int64 UserSessionState; // rsi
  __int64 v3; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  char v5; // di
  AtomicExecutionCheck *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v12; // bl
  bool v13; // bp
  __int64 v14; // rax
  int v15; // r8d
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned int v22; // ebp
  unsigned __int64 i; // rax
  __int64 v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rcx
  __int64 SessionState; // rax
  _DWORD **v28; // r14
  _DWORD *v29; // rcx
  _DWORD *v30; // rbx
  __int64 v31; // rax

  UserSessionState = W32GetUserSessionState(a1);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v3);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  v5 = 1;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
  {
    if ( !(unsigned int)IsThreadCrossSessionAttached() )
    {
      v6 = *(AtomicExecutionCheck **)CurrentThreadWin32Thread;
      *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
      goto LABEL_6;
    }
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
  }
  v6 = 0;
LABEL_6:
  *(_QWORD *)(UserSessionState + 16) = v6;
  if ( v6 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v6) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  AtomicExecutionCheck::EnforceConsistency(v6);
  v8 = PsGetCurrentThreadWin32Thread(v7);
  ++*(_DWORD *)(v8 + 28);
  v11 = *(_QWORD *)(W32GetUserGdiSessionState(v10, v9) + 40);
  if ( *(_QWORD *)a1 == v11 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v11) + 36200) + 368LL) )
    {
      v12 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u;
      v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v15) = v13;
        LOBYTE(v16) = v12;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v16,
          v15,
          *(_QWORD *)(v14 + 69136),
          3,
          14,
          32,
          (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( (unsigned int)DestroyProcessInfo(a1) )
  {
    v18 = W32GetUserSessionState(v17);
    v20 = W32GetUserSessionState(v19);
    v21 = *(_QWORD *)(v18 + 19720);
    v22 = *(_DWORD *)(v20 + 19648);
    for ( i = v21 + 32LL * v22; i > v21 && !*(_BYTE *)(i + 24); i -= 32LL )
      --v22;
    *(_DWORD *)(W32GetUserSessionState(v21) + 19648) = v22;
    v25 = *(_QWORD *)(W32GetUserSessionState(v24) + 56744);
    SessionState = W32GetSessionState(v26);
    GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
    v28 = (_DWORD **)(v25 + 24);
    v29 = *v28;
    if ( *v28 != (_DWORD *)v28 )
    {
      do
      {
        v30 = *(_DWORD **)v29;
        if ( (v29[12] & 0x400000) != 0 )
          DestroyCacheDC(v29);
        v29 = v30;
      }
      while ( v30 != (_DWORD *)v28 );
    }
    v31 = W32GetSessionState(v29);
    GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v31 + 88));
    ApiSetEditionShowSystemCursor();
    if ( v5 )
      CloseWin32InputRelatedObHandles();
  }
  --*(_DWORD *)(v8 + 28);
  UserSessionSwitchLeaveCritWithNonPaged(v17);
}

```

## disassembly

```asm
0x1400d4158  push    rbx
0x1400d415a  push    rbp
0x1400d415b  push    rsi
0x1400d415c  push    rdi
0x1400d415d  push    r13
0x1400d415f  push    r14
0x1400d4161  sub     rsp, 48h
0x1400d4165  mov     r14, rcx
0x1400d4168  call    cs:__imp_W32GetUserSessionState
0x1400d416f  nop     dword ptr [rax+rax+00h]
0x1400d4174  mov     rsi, rax
0x1400d4177  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d417e  nop     dword ptr [rax+rax+00h]
0x1400d4183  mov     rbx, rax
0x1400d4186  call    cs:__imp_KeEnterCriticalRegion
0x1400d418d  nop     dword ptr [rax+rax+00h]
0x1400d4192  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400d4195  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400d4198  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400d419d  cmp     qword ptr [rbx], 0
0x1400d41a1  mov     edi, 1
0x1400d41a6  jnz     short loc_1400D41AC
0x1400d41a8  xor     ecx, ecx
0x1400d41aa  jmp     short loc_1400D41C5
0x1400d41ac  call    IsThreadCrossSessionAttached
0x1400d41b1  test    eax, eax
0x1400d41b3  jz      short loc_1400D41BB
0x1400d41b5  or      dword ptr [rbx+18h], 2
0x1400d41b9  jmp     short loc_1400D41A8
0x1400d41bb  mov     rcx, [rbx]
0x1400d41be  mov     [rcx+6ACh], dil
0x1400d41c5  mov     [rsi+10h], rcx
0x1400d41c9  test    rcx, rcx
0x1400d41cc  jz      short loc_1400D41F8
0x1400d41ce  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400d41d3  test    al, al
0x1400d41d5  jz      short loc_1400D41F8
0x1400d41d7  lea     rbx, [rsi+4C40h]
0x1400d41de  mov     rcx, rbx
0x1400d41e1  call    DestroySharedUserCritDeferredUnlockList
0x1400d41e6  lea     rcx, [rbx+38h]
0x1400d41ea  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d41ef  lea     rcx, [rbx+28h]
0x1400d41f3  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d41f8  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x1400d41fd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d4204  nop     dword ptr [rax+rax+00h]
0x1400d4209  mov     rsi, rax
0x1400d420c  add     [rax+1Ch], edi
0x1400d420f  call    cs:__imp_W32GetUserGdiSessionState
0x1400d4216  nop     dword ptr [rax+rax+00h]
0x1400d421b  mov     r13d, 20h ; ' '
0x1400d4221  mov     rcx, [rax+28h]
0x1400d4225  cmp     [r14], rcx
0x1400d4228  jnz     loc_1400D42DC
0x1400d422e  call    cs:__imp_W32GetUserSessionState
0x1400d4235  nop     dword ptr [rax+rax+00h]
0x1400d423a  mov     rcx, [rax+8D68h]
0x1400d4241  cmp     qword ptr [rcx+170h], 0
0x1400d4249  jz      loc_1400D42DF
0x1400d424f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4256  lea     rax, WPP_GLOBAL_Control
0x1400d425d  cmp     rcx, rax
0x1400d4260  jz      short loc_1400D4276
0x1400d4262  test    dword ptr [rcx+2Ch], 2000h
0x1400d4269  jz      short loc_1400D4276
0x1400d426b  cmp     byte ptr [rcx+29h], 3
0x1400d426f  jb      short loc_1400D4276
0x1400d4271  mov     bl, dil
0x1400d4274  jmp     short loc_1400D4278
0x1400d4276  xor     bl, bl
0x1400d4278  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d427f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d4286  setnz   bpl
0x1400d428a  test    bl, bl
0x1400d428c  jnz     short loc_1400D4293
0x1400d428e  test    bpl, bpl
0x1400d4291  jz      short loc_1400D42DF
0x1400d4293  call    cs:__imp_W32GetUserSessionState
0x1400d429a  nop     dword ptr [rax+rax+00h]
0x1400d429f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d42a6  mov     r8b, bpl
0x1400d42a9  mov     dl, bl
0x1400d42ab  mov     r9, [rax+10E10h]
0x1400d42b2  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x1400d42b9  mov     rcx, [rcx+18h]
0x1400d42bd  mov     [rsp+78h+var_40], rax
0x1400d42c2  mov     [rsp+78h+var_48], r13w
0x1400d42c8  mov     [rsp+78h+var_50], 0Eh
0x1400d42d0  mov     [rsp+78h+var_58], 3
0x1400d42d5  call    WPP_RECORDER_AND_TRACE_SF_
0x1400d42da  jmp     short loc_1400D42DF
0x1400d42dc  xor     dil, dil
0x1400d42df  mov     rcx, r14
0x1400d42e2  call    DestroyProcessInfo
0x1400d42e7  test    eax, eax
0x1400d42e9  jz      loc_1400D43B9
0x1400d42ef  call    cs:__imp_W32GetUserSessionState
0x1400d42f6  nop     dword ptr [rax+rax+00h]
0x1400d42fb  mov     rbx, rax
0x1400d42fe  call    cs:__imp_W32GetUserSessionState
0x1400d4305  nop     dword ptr [rax+rax+00h]
0x1400d430a  mov     rcx, [rbx+4D08h]
0x1400d4311  mov     ebp, [rax+4CC0h]
0x1400d4317  mov     eax, ebp
0x1400d4319  shl     rax, 5
0x1400d431d  add     rax, rcx
0x1400d4320  jmp     short loc_1400D432D
0x1400d4322  cmp     byte ptr [rax+18h], 0
0x1400d4326  jnz     short loc_1400D4332
0x1400d4328  sub     rax, r13
0x1400d432b  dec     ebp
0x1400d432d  cmp     rax, rcx
0x1400d4330  ja      short loc_1400D4322
0x1400d4332  call    cs:__imp_W32GetUserSessionState
0x1400d4339  nop     dword ptr [rax+rax+00h]
0x1400d433e  mov     [rax+4CC0h], ebp
0x1400d4344  call    cs:__imp_W32GetUserSessionState
0x1400d434b  nop     dword ptr [rax+rax+00h]
0x1400d4350  mov     r14, [rax+0DDA8h]
0x1400d4357  call    cs:__imp_W32GetSessionState
0x1400d435e  nop     dword ptr [rax+rax+00h]
0x1400d4363  mov     rcx, [rax+58h]; struct Gre::Base::SESSION_GLOBALS *
0x1400d4367  call    ?GrepLockVisRgn@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GrepLockVisRgn(Gre::Base::SESSION_GLOBALS &)
0x1400d436c  add     r14, 18h
0x1400d4370  mov     rcx, [r14]; Buffer
0x1400d4373  cmp     rcx, r14
0x1400d4376  jz      short loc_1400D4395
0x1400d4378  test    dword ptr [rcx+30h], 400000h
0x1400d437f  mov     rbx, [rcx]
0x1400d4382  jz      short loc_1400D438D
0x1400d4384  mov     rdx, [rcx+10h]
0x1400d4388  call    DestroyCacheDC
0x1400d438d  mov     rcx, rbx
0x1400d4390  cmp     rbx, r14
0x1400d4393  jnz     short loc_1400D4378
0x1400d4395  call    cs:__imp_W32GetSessionState
0x1400d439c  nop     dword ptr [rax+rax+00h]
0x1400d43a1  mov     rcx, [rax+58h]; struct Gre::Base::SESSION_GLOBALS *
0x1400d43a5  call    ?GrepUnlockVisRgn@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GrepUnlockVisRgn(Gre::Base::SESSION_GLOBALS &)
0x1400d43aa  call    ApiSetEditionShowSystemCursor
0x1400d43af  test    dil, dil
0x1400d43b2  jz      short loc_1400D43B9
0x1400d43b4  call    CloseWin32InputRelatedObHandles
0x1400d43b9  dec     dword ptr [rsi+1Ch]
0x1400d43bc  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400d43c1  add     rsp, 48h
0x1400d43c5  pop     r14
0x1400d43c7  pop     r13
0x1400d43c9  pop     rdi
0x1400d43ca  pop     rsi
0x1400d43cb  pop     rbp
0x1400d43cc  pop     rbx
0x1400d43cd  retn
```
