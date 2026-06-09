# UserSessionSwitchEnterCrit

- ea: `0x1400d6d10`
- end: `0x1400d6eb6`
- name: `UserSessionSwitchEnterCrit`
- size: `422`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400d6b80`
- `0x1400d6bb0`

## callees

- `0x140029710`
- `0x140029d90`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400d6d10`
- `0x1400d77a4`
- `0x1400d7988`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d6d38`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d6e35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d6d38`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d6e35`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d6e0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d6e0b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6d29`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6e26`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6d29`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6e26`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d6d79`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d6d79`
- `WIN32K!W32GetUserSessionState` at `0x1400d6d1a`
- `WIN32K!W32GetUserSessionState` at `0x1400d6dce`
- `WIN32K!W32GetUserSessionState` at `0x1400d6de5`
- `WIN32K!W32GetUserSessionState` at `0x1400d6e17`
- `WIN32K!W32GetUserSessionState` at `0x1400d6d1a`
- `WIN32K!W32GetUserSessionState` at `0x1400d6dce`
- `WIN32K!W32GetUserSessionState` at `0x1400d6de5`
- `WIN32K!W32GetUserSessionState` at `0x1400d6e17`

## pseudocode

```c
__int64 __fastcall UserSessionSwitchEnterCrit(__int64 a1, __int64 a2)
{
  __int64 *UserSessionState; // rdi
  __int64 v3; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rdx

  UserSessionState = (__int64 *)W32GetUserSessionState(a1, a2);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v3);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  if ( !*(_QWORD *)CurrentThreadWin32Thread )
    goto LABEL_18;
  if ( IsThreadCrossSessionAttached() )
  {
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
LABEL_18:
    v5 = 0;
    goto LABEL_4;
  }
  v5 = *(_QWORD *)CurrentThreadWin32Thread;
  *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
LABEL_4:
  UserSessionState[2] = v5;
  if ( v5 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v5) )
  {
    DestroySharedUserCritDeferredUnlockList((__int64)(UserSessionState + 2440), v9);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 2447);
    v10 = UserSessionState + 2445;
LABEL_10:
    DestroyDeferredUnlockObjectAssignmentList(v10);
  }
  while ( *(_DWORD *)(W32GetUserGdiSessionState(v5) + 36) && !(unsigned int)IsCurrentProcessDwm() )
  {
    v11 = W32GetUserSessionState(v7, v6);
    ++*(_DWORD *)(v11 + 68864);
    UserSessionSwitchLeaveCritWithNonPaged(v13, v12);
    v16 = W32GetUserSessionState(v15, v14);
    KeWaitForSingleObject(*(PVOID *)(v16 + 68856), UserRequest, 0, 0, 0);
    v19 = (__int64 *)W32GetUserSessionState(v18, v17);
    v21 = PsGetCurrentThreadWin32Thread(v20);
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(*v19, (struct _W32THREADNONPAGED *)v21);
    if ( *(_QWORD *)v21 )
    {
      if ( !IsThreadCrossSessionAttached() )
      {
        v5 = *(_QWORD *)v21;
        *(_BYTE *)(*(_QWORD *)v21 + 1708LL) = 1;
        goto LABEL_14;
      }
      *(_DWORD *)(v21 + 24) |= 2u;
    }
    v5 = 0;
LABEL_14:
    v19[2] = v5;
    if ( v5 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v5) )
    {
      DestroySharedUserCritDeferredUnlockList((__int64)(v19 + 2440), v22);
      DestroyDeferredUnlockObjectAssignmentList(v19 + 2447);
      v10 = v19 + 2445;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400d6d10  mov     [rsp+arg_0], rbx
0x1400d6d15  push    rdi
0x1400d6d16  sub     rsp, 30h
0x1400d6d1a  call    cs:__imp_W32GetUserSessionState
0x1400d6d21  nop     dword ptr [rax+rax+00h]
0x1400d6d26  mov     rdi, rax
0x1400d6d29  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d6d30  nop     dword ptr [rax+rax+00h]
0x1400d6d35  mov     rbx, rax
0x1400d6d38  call    cs:__imp_KeEnterCriticalRegion
0x1400d6d3f  nop     dword ptr [rax+rax+00h]
0x1400d6d44  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x1400d6d47  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400d6d4a  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400d6d4f  cmp     qword ptr [rbx], 0
0x1400d6d53  jz      loc_1400D6EA7
0x1400d6d59  call    IsThreadCrossSessionAttached
0x1400d6d5e  test    eax, eax
0x1400d6d60  jnz     loc_1400D6EA3
0x1400d6d66  mov     rcx, [rbx]
0x1400d6d69  mov     byte ptr [rcx+6ACh], 1
0x1400d6d70  mov     [rdi+10h], rcx
0x1400d6d74  test    rcx, rcx
0x1400d6d77  jnz     short loc_1400D6DA2
0x1400d6d79  call    cs:__imp_W32GetUserGdiSessionState
0x1400d6d80  nop     dword ptr [rax+rax+00h]
0x1400d6d85  cmp     dword ptr [rax+24h], 0
0x1400d6d89  jz      short loc_1400D6D94
0x1400d6d8b  call    ?IsCurrentProcessDwm@@YAHXZ; IsCurrentProcessDwm(void)
0x1400d6d90  test    eax, eax
0x1400d6d92  jz      short loc_1400D6DCE
0x1400d6d94  mov     rbx, [rsp+38h+arg_0]
0x1400d6d99  xor     eax, eax
0x1400d6d9b  add     rsp, 30h
0x1400d6d9f  pop     rdi
0x1400d6da0  retn
0x1400d6da2  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400d6da7  test    al, al
0x1400d6da9  jz      short loc_1400D6D79
0x1400d6dab  lea     rbx, [rdi+4C40h]
0x1400d6db2  mov     rcx, rbx
0x1400d6db5  call    DestroySharedUserCritDeferredUnlockList
0x1400d6dba  lea     rcx, [rbx+38h]
0x1400d6dbe  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d6dc3  lea     rcx, [rbx+28h]
0x1400d6dc7  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d6dcc  jmp     short loc_1400D6D79
0x1400d6dce  call    cs:__imp_W32GetUserSessionState
0x1400d6dd5  nop     dword ptr [rax+rax+00h]
0x1400d6dda  inc     dword ptr [rax+10D00h]
0x1400d6de0  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400d6de5  call    cs:__imp_W32GetUserSessionState
0x1400d6dec  nop     dword ptr [rax+rax+00h]
0x1400d6df1  xor     r9d, r9d; Alertable
0x1400d6df4  mov     [rsp+38h+Timeout], 0; Timeout
0x1400d6dfd  xor     r8d, r8d; WaitMode
0x1400d6e00  mov     rcx, [rax+10CF8h]; Object
0x1400d6e07  lea     edx, [r9+6]; WaitReason
0x1400d6e0b  call    cs:__imp_KeWaitForSingleObject
0x1400d6e12  nop     dword ptr [rax+rax+00h]
0x1400d6e17  call    cs:__imp_W32GetUserSessionState
0x1400d6e1e  nop     dword ptr [rax+rax+00h]
0x1400d6e23  mov     rbx, rax
0x1400d6e26  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d6e2d  nop     dword ptr [rax+rax+00h]
0x1400d6e32  mov     rdi, rax
0x1400d6e35  call    cs:__imp_KeEnterCriticalRegion
0x1400d6e3c  nop     dword ptr [rax+rax+00h]
0x1400d6e41  mov     rcx, [rbx]; struct _FAST_ERESOURCE *
0x1400d6e44  mov     rdx, rdi; struct _W32THREADNONPAGED *
0x1400d6e47  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400d6e4c  cmp     qword ptr [rdi], 0
0x1400d6e50  jz      short loc_1400D6EB2
0x1400d6e52  call    IsThreadCrossSessionAttached
0x1400d6e57  test    eax, eax
0x1400d6e59  jnz     short loc_1400D6EAE
0x1400d6e5b  mov     rcx, [rdi]
0x1400d6e5e  mov     byte ptr [rcx+6ACh], 1
0x1400d6e65  mov     [rbx+10h], rcx
0x1400d6e69  test    rcx, rcx
0x1400d6e6c  jz      loc_1400D6D79
0x1400d6e72  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400d6e77  test    al, al
0x1400d6e79  jz      loc_1400D6D79
0x1400d6e7f  lea     rcx, [rbx+4C40h]
0x1400d6e86  call    DestroySharedUserCritDeferredUnlockList
0x1400d6e8b  lea     rcx, [rbx+4C78h]
0x1400d6e92  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d6e97  lea     rcx, [rbx+4C68h]
0x1400d6e9e  jmp     loc_1400D6DC7
0x1400d6ea3  or      dword ptr [rbx+18h], 2
0x1400d6ea7  xor     ecx, ecx
0x1400d6ea9  jmp     loc_1400D6D70
0x1400d6eae  or      dword ptr [rdi+18h], 2
0x1400d6eb2  xor     ecx, ecx
0x1400d6eb4  jmp     short loc_1400D6E65
```
