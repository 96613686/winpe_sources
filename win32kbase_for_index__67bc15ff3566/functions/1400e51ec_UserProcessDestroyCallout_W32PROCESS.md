# UserProcessDestroyCallout(_W32PROCESS *)

- ea: `0x1400e51ec`
- end: `0x1400e5463`
- name: `?UserProcessDestroyCallout@@YAXPEAU_W32PROCESS@@@Z`
- size: `631`
- prototype: `void __fastcall(struct _W32PROCESS *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14014da60`

## callees

- `0x140029710`
- `0x140029d90`
- `0x14002ad88`
- `0x14002adb4`
- `0x140037420`
- `0x140049ec0`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x14006b610`
- `0x1400d7988`
- `0x1400e51ec`
- `0x1400e546c`
- `0x1401b953c`
- `0x140216140`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e521a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e521a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e520b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e5291`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e520b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e5291`
- `WIN32K!W32GetSessionState` at `0x1400e53eb`
- `WIN32K!W32GetSessionState` at `0x1400e5429`
- `WIN32K!W32GetSessionState` at `0x1400e53eb`
- `WIN32K!W32GetSessionState` at `0x1400e5429`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400e52a3`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400e52a3`
- `WIN32K!W32GetUserSessionState` at `0x1400e51fc`
- `WIN32K!W32GetUserSessionState` at `0x1400e52c2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5327`
- `WIN32K!W32GetUserSessionState` at `0x1400e5383`
- `WIN32K!W32GetUserSessionState` at `0x1400e5392`
- `WIN32K!W32GetUserSessionState` at `0x1400e53c6`
- `WIN32K!W32GetUserSessionState` at `0x1400e53d8`
- `WIN32K!W32GetUserSessionState` at `0x1400e51fc`
- `WIN32K!W32GetUserSessionState` at `0x1400e52c2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5327`
- `WIN32K!W32GetUserSessionState` at `0x1400e5383`
- `WIN32K!W32GetUserSessionState` at `0x1400e5392`
- `WIN32K!W32GetUserSessionState` at `0x1400e53c6`
- `WIN32K!W32GetUserSessionState` at `0x1400e53d8`

## pseudocode

```c
void __fastcall UserProcessDestroyCallout(struct _W32PROCESS *a1, __int64 a2, __int64 a3)
{
  __int64 UserSessionState; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 CurrentThreadWin32Thread; // rbx
  char v10; // di
  AtomicExecutionCheck *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  bool v24; // bl
  bool v25; // bp
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned __int64 v39; // rcx
  unsigned int v40; // ebp
  unsigned __int64 i; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r14
  __int64 v46; // rcx
  __int64 SessionState; // rax
  _DWORD **v48; // r14
  _DWORD *v49; // rcx
  _DWORD *v50; // rbx
  __int64 v51; // rax

  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v6, v5, v7, v8);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  v10 = 1;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
  {
    if ( !(unsigned int)IsThreadCrossSessionAttached() )
    {
      v11 = *(AtomicExecutionCheck **)CurrentThreadWin32Thread;
      *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
      goto LABEL_6;
    }
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
  }
  v11 = 0;
LABEL_6:
  *(_QWORD *)(UserSessionState + 16) = v11;
  if ( v11 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v11) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  AtomicExecutionCheck::EnforceConsistency(v11);
  v16 = PsGetCurrentThreadWin32Thread(v13, v12, v14, v15);
  ++*(_DWORD *)(v16 + 28);
  v20 = *(_QWORD *)(W32GetUserGdiSessionState(v18, v17) + 40);
  if ( *(_QWORD *)a1 == v20 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v20, v19, v21) + 36200) + 368LL) )
    {
      v24 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u;
      v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v26 = W32GetUserSessionState(WPP_GLOBAL_Control, v22, v23);
        LOBYTE(v27) = v25;
        LOBYTE(v28) = v24;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v28,
          v27,
          *(_QWORD *)(v26 + 69136),
          3,
          14,
          32,
          (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids);
      }
    }
  }
  else
  {
    v10 = 0;
  }
  if ( (unsigned int)DestroyProcessInfo(a1) )
  {
    v32 = W32GetUserSessionState(v30, v29, v31);
    v36 = W32GetUserSessionState(v34, v33, v35);
    v39 = *(_QWORD *)(v32 + 19720);
    v40 = *(_DWORD *)(v36 + 19648);
    for ( i = v39 + 32LL * v40; i > v39 && !*(_BYTE *)(i + 24); i -= 32LL )
      --v40;
    *(_DWORD *)(W32GetUserSessionState(v39, v37, v38) + 19648) = v40;
    v45 = *(_QWORD *)(W32GetUserSessionState(v43, v42, v44) + 56744);
    SessionState = W32GetSessionState(v46);
    GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
    v48 = (_DWORD **)(v45 + 24);
    v49 = *v48;
    if ( *v48 != (_DWORD *)v48 )
    {
      do
      {
        v50 = *(_DWORD **)v49;
        if ( (v49[12] & 0x400000) != 0 )
          DestroyCacheDC(v49);
        v49 = v50;
      }
      while ( v50 != (_DWORD *)v48 );
    }
    v51 = W32GetSessionState(v49);
    GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v51 + 88));
    ApiSetEditionShowSystemCursor();
    if ( v10 )
      CloseWin32InputRelatedObHandles();
  }
  --*(_DWORD *)(v16 + 28);
  UserSessionSwitchLeaveCritWithNonPaged(v30, v29, v31);
}

```

## disassembly

```asm
0x1400e51ec  push    rbx
0x1400e51ee  push    rbp
0x1400e51ef  push    rsi
0x1400e51f0  push    rdi
0x1400e51f1  push    r13
0x1400e51f3  push    r14
0x1400e51f5  sub     rsp, 48h
0x1400e51f9  mov     r14, rcx
0x1400e51fc  call    cs:__imp_W32GetUserSessionState
0x1400e5203  nop     dword ptr [rax+rax+00h]
0x1400e5208  mov     rsi, rax
0x1400e520b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e5212  nop     dword ptr [rax+rax+00h]
0x1400e5217  mov     rbx, rax
0x1400e521a  call    cs:__imp_KeEnterCriticalRegion
0x1400e5221  nop     dword ptr [rax+rax+00h]
0x1400e5226  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400e5229  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400e522c  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400e5231  cmp     qword ptr [rbx], 0
0x1400e5235  mov     edi, 1
0x1400e523a  jnz     short loc_1400E5240
0x1400e523c  xor     ecx, ecx
0x1400e523e  jmp     short loc_1400E5259
0x1400e5240  call    IsThreadCrossSessionAttached
0x1400e5245  test    eax, eax
0x1400e5247  jz      short loc_1400E524F
0x1400e5249  or      dword ptr [rbx+18h], 2
0x1400e524d  jmp     short loc_1400E523C
0x1400e524f  mov     rcx, [rbx]
0x1400e5252  mov     [rcx+6ACh], dil
0x1400e5259  mov     [rsi+10h], rcx
0x1400e525d  test    rcx, rcx
0x1400e5260  jz      short loc_1400E528C
0x1400e5262  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400e5267  test    al, al
0x1400e5269  jz      short loc_1400E528C
0x1400e526b  lea     rbx, [rsi+4C40h]
0x1400e5272  mov     rcx, rbx
0x1400e5275  call    DestroySharedUserCritDeferredUnlockList
0x1400e527a  lea     rcx, [rbx+38h]
0x1400e527e  call    DestroyDeferredUnlockObjectAssignmentList
0x1400e5283  lea     rcx, [rbx+28h]
0x1400e5287  call    DestroyDeferredUnlockObjectAssignmentList
0x1400e528c  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x1400e5291  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e5298  nop     dword ptr [rax+rax+00h]
0x1400e529d  mov     rsi, rax
0x1400e52a0  add     [rax+1Ch], edi
0x1400e52a3  call    cs:__imp_W32GetUserGdiSessionState
0x1400e52aa  nop     dword ptr [rax+rax+00h]
0x1400e52af  mov     r13d, 20h ; ' '
0x1400e52b5  mov     rcx, [rax+28h]
0x1400e52b9  cmp     [r14], rcx
0x1400e52bc  jnz     loc_1400E5370
0x1400e52c2  call    cs:__imp_W32GetUserSessionState
0x1400e52c9  nop     dword ptr [rax+rax+00h]
0x1400e52ce  mov     rcx, [rax+8D68h]
0x1400e52d5  cmp     qword ptr [rcx+170h], 0
0x1400e52dd  jz      loc_1400E5373
0x1400e52e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e52ea  lea     rax, WPP_GLOBAL_Control
0x1400e52f1  cmp     rcx, rax
0x1400e52f4  jz      short loc_1400E530A
0x1400e52f6  test    dword ptr [rcx+2Ch], 2000h
0x1400e52fd  jz      short loc_1400E530A
0x1400e52ff  cmp     byte ptr [rcx+29h], 3
0x1400e5303  jb      short loc_1400E530A
0x1400e5305  mov     bl, dil
0x1400e5308  jmp     short loc_1400E530C
0x1400e530a  xor     bl, bl
0x1400e530c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e5313  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e531a  setnz   bpl
0x1400e531e  test    bl, bl
0x1400e5320  jnz     short loc_1400E5327
0x1400e5322  test    bpl, bpl
0x1400e5325  jz      short loc_1400E5373
0x1400e5327  call    cs:__imp_W32GetUserSessionState
0x1400e532e  nop     dword ptr [rax+rax+00h]
0x1400e5333  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e533a  mov     r8b, bpl
0x1400e533d  mov     dl, bl
0x1400e533f  mov     r9, [rax+10E10h]
0x1400e5346  lea     rax, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x1400e534d  mov     rcx, [rcx+18h]
0x1400e5351  mov     [rsp+78h+var_40], rax
0x1400e5356  mov     [rsp+78h+var_48], r13w
0x1400e535c  mov     [rsp+78h+var_50], 0Eh
0x1400e5364  mov     [rsp+78h+var_58], 3
0x1400e5369  call    WPP_RECORDER_AND_TRACE_SF_
0x1400e536e  jmp     short loc_1400E5373
0x1400e5370  xor     dil, dil
0x1400e5373  mov     rcx, r14
0x1400e5376  call    DestroyProcessInfo
0x1400e537b  test    eax, eax
0x1400e537d  jz      loc_1400E544D
0x1400e5383  call    cs:__imp_W32GetUserSessionState
0x1400e538a  nop     dword ptr [rax+rax+00h]
0x1400e538f  mov     rbx, rax
0x1400e5392  call    cs:__imp_W32GetUserSessionState
0x1400e5399  nop     dword ptr [rax+rax+00h]
0x1400e539e  mov     rcx, [rbx+4D08h]
0x1400e53a5  mov     ebp, [rax+4CC0h]
0x1400e53ab  mov     eax, ebp
0x1400e53ad  shl     rax, 5
0x1400e53b1  add     rax, rcx
0x1400e53b4  jmp     short loc_1400E53C1
0x1400e53b6  cmp     byte ptr [rax+18h], 0
0x1400e53ba  jnz     short loc_1400E53C6
0x1400e53bc  sub     rax, r13
0x1400e53bf  dec     ebp
0x1400e53c1  cmp     rax, rcx
0x1400e53c4  ja      short loc_1400E53B6
0x1400e53c6  call    cs:__imp_W32GetUserSessionState
0x1400e53cd  nop     dword ptr [rax+rax+00h]
0x1400e53d2  mov     [rax+4CC0h], ebp
0x1400e53d8  call    cs:__imp_W32GetUserSessionState
0x1400e53df  nop     dword ptr [rax+rax+00h]
0x1400e53e4  mov     r14, [rax+0DDA8h]
0x1400e53eb  call    cs:__imp_W32GetSessionState
0x1400e53f2  nop     dword ptr [rax+rax+00h]
0x1400e53f7  mov     rcx, [rax+58h]; struct Gre::Base::SESSION_GLOBALS *
0x1400e53fb  call    ?GrepLockVisRgn@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GrepLockVisRgn(Gre::Base::SESSION_GLOBALS &)
0x1400e5400  add     r14, 18h
0x1400e5404  mov     rcx, [r14]; Buffer
0x1400e5407  cmp     rcx, r14
0x1400e540a  jz      short loc_1400E5429
0x1400e540c  test    dword ptr [rcx+30h], 400000h
0x1400e5413  mov     rbx, [rcx]
0x1400e5416  jz      short loc_1400E5421
0x1400e5418  mov     rdx, [rcx+10h]
0x1400e541c  call    DestroyCacheDC
0x1400e5421  mov     rcx, rbx
0x1400e5424  cmp     rbx, r14
0x1400e5427  jnz     short loc_1400E540C
0x1400e5429  call    cs:__imp_W32GetSessionState
0x1400e5430  nop     dword ptr [rax+rax+00h]
0x1400e5435  mov     rcx, [rax+58h]; struct Gre::Base::SESSION_GLOBALS *
0x1400e5439  call    ?GrepUnlockVisRgn@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GrepUnlockVisRgn(Gre::Base::SESSION_GLOBALS &)
0x1400e543e  call    ApiSetEditionShowSystemCursor
0x1400e5443  test    dil, dil
0x1400e5446  jz      short loc_1400E544D
0x1400e5448  call    CloseWin32InputRelatedObHandles
0x1400e544d  dec     dword ptr [rsi+1Ch]
0x1400e5450  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400e5455  add     rsp, 48h
0x1400e5459  pop     r14
0x1400e545b  pop     r13
0x1400e545d  pop     rdi
0x1400e545e  pop     rsi
0x1400e545f  pop     rbp
0x1400e5460  pop     rbx
0x1400e5461  retn
```
