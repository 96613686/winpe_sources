# UserSessionSwitchEnterCrit

- ea: `0x1400354a0`
- end: `0x140035646`
- name: `UserSessionSwitchEnterCrit`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140035310`
- `0x140035340`

## callees

- `0x14001bdf0`
- `0x14001c470`
- `0x1400354a0`
- `0x140035f34`
- `0x140036118`
- `0x140077f50`
- `0x140078090`
- `0x140078120`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400354c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400355c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400354c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400355c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003559b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003559b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400354b9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400355b6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400354b9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400355b6`
- `WIN32K!W32GetUserGdiSessionState` at `0x140035509`
- `WIN32K!W32GetUserGdiSessionState` at `0x140035509`
- `WIN32K!W32GetUserSessionState` at `0x1400354aa`
- `WIN32K!W32GetUserSessionState` at `0x14003555e`
- `WIN32K!W32GetUserSessionState` at `0x140035575`
- `WIN32K!W32GetUserSessionState` at `0x1400355a7`
- `WIN32K!W32GetUserSessionState` at `0x1400354aa`
- `WIN32K!W32GetUserSessionState` at `0x14003555e`
- `WIN32K!W32GetUserSessionState` at `0x140035575`
- `WIN32K!W32GetUserSessionState` at `0x1400355a7`

## pseudocode

```c
__int64 __fastcall UserSessionSwitchEnterCrit(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 UserSessionState; // rdi
  __int64 v4; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rdi

  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v4);
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
    v7 = 0;
    goto LABEL_4;
  }
  v7 = *(_QWORD *)CurrentThreadWin32Thread;
  *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
LABEL_4:
  *(_QWORD *)(UserSessionState + 16) = v7;
  if ( v7 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v7) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    v12 = UserSessionState + 19560;
LABEL_10:
    DestroyDeferredUnlockObjectAssignmentList(v12);
  }
  while ( *(_DWORD *)(W32GetUserGdiSessionState(v7, v6) + 36) && !(unsigned int)IsCurrentProcessDwm() )
  {
    v13 = W32GetUserSessionState(v9, v8, v10);
    ++*(_DWORD *)(v13 + 68864);
    UserSessionSwitchLeaveCritWithNonPaged(v15, v14, v16);
    v20 = W32GetUserSessionState(v18, v17, v19);
    KeWaitForSingleObject(*(PVOID *)(v20 + 68856), UserRequest, 0, 0, 0);
    v24 = W32GetUserSessionState(v22, v21, v23);
    v26 = PsGetCurrentThreadWin32Thread(v25);
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v24,
      (struct _W32THREADNONPAGED *)v26);
    if ( *(_QWORD *)v26 )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v7 = *(_QWORD *)v26;
        *(_BYTE *)(*(_QWORD *)v26 + 1708LL) = 1;
        goto LABEL_14;
      }
      *(_DWORD *)(v26 + 24) |= 2u;
    }
    v7 = 0;
LABEL_14:
    *(_QWORD *)(v24 + 16) = v7;
    if ( v7 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v7) )
    {
      DestroySharedUserCritDeferredUnlockList(v24 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v24 + 19576);
      v12 = v24 + 19560;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400354a0  mov     [rsp+arg_0], rbx
0x1400354a5  push    rdi
0x1400354a6  sub     rsp, 30h
0x1400354aa  call    cs:__imp_W32GetUserSessionState
0x1400354b1  nop     dword ptr [rax+rax+00h]
0x1400354b6  mov     rdi, rax
0x1400354b9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400354c0  nop     dword ptr [rax+rax+00h]
0x1400354c5  mov     rbx, rax
0x1400354c8  call    cs:__imp_KeEnterCriticalRegion
0x1400354cf  nop     dword ptr [rax+rax+00h]
0x1400354d4  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x1400354d7  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400354da  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400354df  cmp     qword ptr [rbx], 0
0x1400354e3  jz      loc_140035637
0x1400354e9  call    IsThreadCrossSessionAttached
0x1400354ee  test    eax, eax
0x1400354f0  jnz     loc_140035633
0x1400354f6  mov     rcx, [rbx]
0x1400354f9  mov     byte ptr [rcx+6ACh], 1
0x140035500  mov     [rdi+10h], rcx
0x140035504  test    rcx, rcx
0x140035507  jnz     short loc_140035532
0x140035509  call    cs:__imp_W32GetUserGdiSessionState
0x140035510  nop     dword ptr [rax+rax+00h]
0x140035515  cmp     dword ptr [rax+24h], 0
0x140035519  jz      short loc_140035524
0x14003551b  call    ?IsCurrentProcessDwm@@YAHXZ; IsCurrentProcessDwm(void)
0x140035520  test    eax, eax
0x140035522  jz      short loc_14003555E
0x140035524  mov     rbx, [rsp+38h+arg_0]
0x140035529  xor     eax, eax
0x14003552b  add     rsp, 30h
0x14003552f  pop     rdi
0x140035530  retn
0x140035532  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x140035537  test    al, al
0x140035539  jz      short loc_140035509
0x14003553b  lea     rbx, [rdi+4C40h]
0x140035542  mov     rcx, rbx
0x140035545  call    DestroySharedUserCritDeferredUnlockList
0x14003554a  lea     rcx, [rbx+38h]
0x14003554e  call    DestroyDeferredUnlockObjectAssignmentList
0x140035553  lea     rcx, [rbx+28h]
0x140035557  call    DestroyDeferredUnlockObjectAssignmentList
0x14003555c  jmp     short loc_140035509
0x14003555e  call    cs:__imp_W32GetUserSessionState
0x140035565  nop     dword ptr [rax+rax+00h]
0x14003556a  inc     dword ptr [rax+10D00h]
0x140035570  call    UserSessionSwitchLeaveCritWithNonPaged
0x140035575  call    cs:__imp_W32GetUserSessionState
0x14003557c  nop     dword ptr [rax+rax+00h]
0x140035581  xor     r9d, r9d; Alertable
0x140035584  mov     [rsp+38h+Timeout], 0; Timeout
0x14003558d  xor     r8d, r8d; WaitMode
0x140035590  mov     rcx, [rax+10CF8h]; Object
0x140035597  lea     edx, [r9+6]; WaitReason
0x14003559b  call    cs:__imp_KeWaitForSingleObject
0x1400355a2  nop     dword ptr [rax+rax+00h]
0x1400355a7  call    cs:__imp_W32GetUserSessionState
0x1400355ae  nop     dword ptr [rax+rax+00h]
0x1400355b3  mov     rbx, rax
0x1400355b6  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400355bd  nop     dword ptr [rax+rax+00h]
0x1400355c2  mov     rdi, rax
0x1400355c5  call    cs:__imp_KeEnterCriticalRegion
0x1400355cc  nop     dword ptr [rax+rax+00h]
0x1400355d1  mov     rcx, [rbx]; struct _FAST_ERESOURCE *
0x1400355d4  mov     rdx, rdi; struct _W32THREADNONPAGED *
0x1400355d7  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400355dc  cmp     qword ptr [rdi], 0
0x1400355e0  jz      short loc_140035642
0x1400355e2  call    IsThreadCrossSessionAttached
0x1400355e7  test    eax, eax
0x1400355e9  jnz     short loc_14003563E
0x1400355eb  mov     rcx, [rdi]
0x1400355ee  mov     byte ptr [rcx+6ACh], 1
0x1400355f5  mov     [rbx+10h], rcx
0x1400355f9  test    rcx, rcx
0x1400355fc  jz      loc_140035509
0x140035602  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x140035607  test    al, al
0x140035609  jz      loc_140035509
0x14003560f  lea     rcx, [rbx+4C40h]
0x140035616  call    DestroySharedUserCritDeferredUnlockList
0x14003561b  lea     rcx, [rbx+4C78h]
0x140035622  call    DestroyDeferredUnlockObjectAssignmentList
0x140035627  lea     rcx, [rbx+4C68h]
0x14003562e  jmp     loc_140035557
0x140035633  or      dword ptr [rbx+18h], 2
0x140035637  xor     ecx, ecx
0x140035639  jmp     loc_140035500
0x14003563e  or      dword ptr [rdi+18h], 2
0x140035642  xor     ecx, ecx
0x140035644  jmp     short loc_1400355F5
```
