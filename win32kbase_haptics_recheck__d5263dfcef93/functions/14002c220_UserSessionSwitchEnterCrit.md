# UserSessionSwitchEnterCrit

- ea: `0x14002c220`
- end: `0x14002c3c6`
- name: `UserSessionSwitchEnterCrit`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14002c090`
- `0x14002c0c0`

## callees

- `0x140012c80`
- `0x140013300`
- `0x14002c220`
- `0x14002ccb4`
- `0x14002ce98`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c248`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c345`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c248`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c345`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c31b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c31b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002c239`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002c336`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002c239`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002c336`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002c289`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002c289`
- `WIN32K!W32GetUserSessionState` at `0x14002c22a`
- `WIN32K!W32GetUserSessionState` at `0x14002c2de`
- `WIN32K!W32GetUserSessionState` at `0x14002c2f5`
- `WIN32K!W32GetUserSessionState` at `0x14002c327`
- `WIN32K!W32GetUserSessionState` at `0x14002c22a`
- `WIN32K!W32GetUserSessionState` at `0x14002c2de`
- `WIN32K!W32GetUserSessionState` at `0x14002c2f5`
- `WIN32K!W32GetUserSessionState` at `0x14002c327`

## pseudocode

```c
__int64 __fastcall UserSessionSwitchEnterCrit(__int64 a1)
{
  __int64 UserSessionState; // rdi
  __int64 v2; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdi

  UserSessionState = W32GetUserSessionState(a1);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v2);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  if ( !*(_QWORD *)CurrentThreadWin32Thread )
    goto LABEL_18;
  if ( (unsigned int)IsThreadCrossSessionAttached() )
  {
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
LABEL_18:
    v5 = 0;
    goto LABEL_4;
  }
  v5 = *(_QWORD *)CurrentThreadWin32Thread;
  *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
LABEL_4:
  *(_QWORD *)(UserSessionState + 16) = v5;
  if ( v5 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v5) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    v8 = UserSessionState + 19560;
LABEL_10:
    DestroyDeferredUnlockObjectAssignmentList(v8);
  }
  while ( *(_DWORD *)(W32GetUserGdiSessionState(v5, v4) + 36) && !(unsigned int)IsCurrentProcessDwm() )
  {
    v9 = W32GetUserSessionState(v6);
    ++*(_DWORD *)(v9 + 68864);
    UserSessionSwitchLeaveCritWithNonPaged(v10);
    v12 = W32GetUserSessionState(v11);
    KeWaitForSingleObject(*(PVOID *)(v12 + 68856), UserRequest, 0, 0, 0);
    v14 = W32GetUserSessionState(v13);
    v16 = PsGetCurrentThreadWin32Thread(v15);
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v14,
      (struct _W32THREADNONPAGED *)v16);
    if ( *(_QWORD *)v16 )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v5 = *(_QWORD *)v16;
        *(_BYTE *)(*(_QWORD *)v16 + 1708LL) = 1;
        goto LABEL_14;
      }
      *(_DWORD *)(v16 + 24) |= 2u;
    }
    v5 = 0;
LABEL_14:
    *(_QWORD *)(v14 + 16) = v5;
    if ( v5 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v5) )
    {
      DestroySharedUserCritDeferredUnlockList(v14 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v14 + 19576);
      v8 = v14 + 19560;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002c220  mov     [rsp+arg_0], rbx
0x14002c225  push    rdi
0x14002c226  sub     rsp, 30h
0x14002c22a  call    cs:__imp_W32GetUserSessionState
0x14002c231  nop     dword ptr [rax+rax+00h]
0x14002c236  mov     rdi, rax
0x14002c239  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002c240  nop     dword ptr [rax+rax+00h]
0x14002c245  mov     rbx, rax
0x14002c248  call    cs:__imp_KeEnterCriticalRegion
0x14002c24f  nop     dword ptr [rax+rax+00h]
0x14002c254  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x14002c257  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14002c25a  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14002c25f  cmp     qword ptr [rbx], 0
0x14002c263  jz      loc_14002C3B7
0x14002c269  call    IsThreadCrossSessionAttached
0x14002c26e  test    eax, eax
0x14002c270  jnz     loc_14002C3B3
0x14002c276  mov     rcx, [rbx]
0x14002c279  mov     byte ptr [rcx+6ACh], 1
0x14002c280  mov     [rdi+10h], rcx
0x14002c284  test    rcx, rcx
0x14002c287  jnz     short loc_14002C2B2
0x14002c289  call    cs:__imp_W32GetUserGdiSessionState
0x14002c290  nop     dword ptr [rax+rax+00h]
0x14002c295  cmp     dword ptr [rax+24h], 0
0x14002c299  jz      short loc_14002C2A4
0x14002c29b  call    ?IsCurrentProcessDwm@@YAHXZ; IsCurrentProcessDwm(void)
0x14002c2a0  test    eax, eax
0x14002c2a2  jz      short loc_14002C2DE
0x14002c2a4  mov     rbx, [rsp+38h+arg_0]
0x14002c2a9  xor     eax, eax
0x14002c2ab  add     rsp, 30h
0x14002c2af  pop     rdi
0x14002c2b0  retn
0x14002c2b2  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x14002c2b7  test    al, al
0x14002c2b9  jz      short loc_14002C289
0x14002c2bb  lea     rbx, [rdi+4C40h]
0x14002c2c2  mov     rcx, rbx
0x14002c2c5  call    DestroySharedUserCritDeferredUnlockList
0x14002c2ca  lea     rcx, [rbx+38h]
0x14002c2ce  call    DestroyDeferredUnlockObjectAssignmentList
0x14002c2d3  lea     rcx, [rbx+28h]
0x14002c2d7  call    DestroyDeferredUnlockObjectAssignmentList
0x14002c2dc  jmp     short loc_14002C289
0x14002c2de  call    cs:__imp_W32GetUserSessionState
0x14002c2e5  nop     dword ptr [rax+rax+00h]
0x14002c2ea  inc     dword ptr [rax+10D00h]
0x14002c2f0  call    UserSessionSwitchLeaveCritWithNonPaged
0x14002c2f5  call    cs:__imp_W32GetUserSessionState
0x14002c2fc  nop     dword ptr [rax+rax+00h]
0x14002c301  xor     r9d, r9d; Alertable
0x14002c304  mov     [rsp+38h+Timeout], 0; Timeout
0x14002c30d  xor     r8d, r8d; WaitMode
0x14002c310  mov     rcx, [rax+10CF8h]; Object
0x14002c317  lea     edx, [r9+6]; WaitReason
0x14002c31b  call    cs:__imp_KeWaitForSingleObject
0x14002c322  nop     dword ptr [rax+rax+00h]
0x14002c327  call    cs:__imp_W32GetUserSessionState
0x14002c32e  nop     dword ptr [rax+rax+00h]
0x14002c333  mov     rbx, rax
0x14002c336  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002c33d  nop     dword ptr [rax+rax+00h]
0x14002c342  mov     rdi, rax
0x14002c345  call    cs:__imp_KeEnterCriticalRegion
0x14002c34c  nop     dword ptr [rax+rax+00h]
0x14002c351  mov     rcx, [rbx]; struct _FAST_ERESOURCE *
0x14002c354  mov     rdx, rdi; struct _W32THREADNONPAGED *
0x14002c357  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14002c35c  cmp     qword ptr [rdi], 0
0x14002c360  jz      short loc_14002C3C2
0x14002c362  call    IsThreadCrossSessionAttached
0x14002c367  test    eax, eax
0x14002c369  jnz     short loc_14002C3BE
0x14002c36b  mov     rcx, [rdi]
0x14002c36e  mov     byte ptr [rcx+6ACh], 1
0x14002c375  mov     [rbx+10h], rcx
0x14002c379  test    rcx, rcx
0x14002c37c  jz      loc_14002C289
0x14002c382  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x14002c387  test    al, al
0x14002c389  jz      loc_14002C289
0x14002c38f  lea     rcx, [rbx+4C40h]
0x14002c396  call    DestroySharedUserCritDeferredUnlockList
0x14002c39b  lea     rcx, [rbx+4C78h]
0x14002c3a2  call    DestroyDeferredUnlockObjectAssignmentList
0x14002c3a7  lea     rcx, [rbx+4C68h]
0x14002c3ae  jmp     loc_14002C2D7
0x14002c3b3  or      dword ptr [rbx+18h], 2
0x14002c3b7  xor     ecx, ecx
0x14002c3b9  jmp     loc_14002C280
0x14002c3be  or      dword ptr [rdi+18h], 2
0x14002c3c2  xor     ecx, ecx
0x14002c3c4  jmp     short loc_14002C375
```
