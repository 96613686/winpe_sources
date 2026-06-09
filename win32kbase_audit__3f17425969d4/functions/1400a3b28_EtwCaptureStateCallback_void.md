# EtwCaptureStateCallback(void)

- ea: `0x1400a3b28`
- end: `0x1400a3e0b`
- name: `?EtwCaptureStateCallback@@YAXXZ`
- size: `739`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140064560`

## callees

- `0x140029710`
- `0x140029d90`
- `0x1400371c0`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400814d4`
- `0x1400a3b28`
- `0x1400a4260`
- `0x1400d7988`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a3b55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a3b55`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400a3b46`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400a3b46`
- `ntoskrnl!PsGetThreadId` at `0x1400a3ca0`
- `ntoskrnl!PsGetThreadId` at `0x1400a3ca0`
- `WIN32K!W32GetUserSessionState` at `0x1400a3b37`
- `WIN32K!W32GetUserSessionState` at `0x1400a3be9`
- `WIN32K!W32GetUserSessionState` at `0x1400a3c4b`
- `WIN32K!W32GetUserSessionState` at `0x1400a3d81`
- `WIN32K!W32GetUserSessionState` at `0x1400a3dac`
- `WIN32K!W32GetUserSessionState` at `0x1400a3dc5`
- `WIN32K!W32GetUserSessionState` at `0x1400a3dd7`
- `WIN32K!W32GetUserSessionState` at `0x1400a3b37`
- `WIN32K!W32GetUserSessionState` at `0x1400a3be9`
- `WIN32K!W32GetUserSessionState` at `0x1400a3c4b`
- `WIN32K!W32GetUserSessionState` at `0x1400a3d81`
- `WIN32K!W32GetUserSessionState` at `0x1400a3dac`
- `WIN32K!W32GetUserSessionState` at `0x1400a3dc5`
- `WIN32K!W32GetUserSessionState` at `0x1400a3dd7`

## pseudocode

```c
void __fastcall EtwCaptureStateCallback(__int64 a1, __int64 a2)
{
  __int64 *UserSessionState; // rdi
  __int64 v3; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rbp
  __int64 i; // rdi
  __int64 v10; // rbx
  _QWORD *j; // rsi
  int ThreadId; // r12d
  char ThreadInfoFlags; // al
  int v14; // ecx
  char v15; // r10
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rbp
  __int64 v20; // rdx
  unsigned int v21; // ebp
  int v22; // esi
  __int64 v23; // rcx
  char CurrentWin32kSessionId; // di
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8

  UserSessionState = (__int64 *)W32GetUserSessionState(a1, a2);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v3);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  if ( !*(_QWORD *)CurrentThreadWin32Thread )
    goto LABEL_37;
  if ( IsThreadCrossSessionAttached() )
  {
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
LABEL_37:
    v5 = 0;
    goto LABEL_4;
  }
  v5 = *(_QWORD *)CurrentThreadWin32Thread;
  *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
LABEL_4:
  UserSessionState[2] = v5;
  if ( v5 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v5) )
  {
    DestroySharedUserCritDeferredUnlockList((__int64)(UserSessionState + 2440), v18);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 2447);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 2445);
  }
  if ( (W32kEtwEnabledKeyword & 0x8000000000040000uLL) != 0
    && (unsigned __int8)(byte_140293DD8 - 1) > 2u
    && (qword_140293DC0 & 0x8000000000040000uLL) != 0
    && (qword_140293DC8 & 0x8000000000040000uLL) == qword_140293DC8 )
  {
    if ( *(_DWORD *)(W32GetUserSessionState(v5, 0x8000000000040000uLL) + 36184) )
    {
      v19 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v21 = v19 - *(_DWORD *)(W32GetUserSessionState(v5, v6) + 36188);
      if ( v21 >= 0xC8 && (Microsoft_Windows_Win32kEnableBits & 0x40) != 0 )
      {
        v22 = *(_DWORD *)(W32GetUserSessionState(v5, v20) + 36184);
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v23);
        v27 = *(_DWORD *)(W32GetUserSessionState(v26, v25) + 36196);
        v30 = W32GetUserSessionState(v29, v28);
        McTemplateK0qqqqq_EtwWriteTransfer(
          v31,
          (const EVENT_DESCRIPTOR *)WaitCursorEvent,
          v32,
          *(_DWORD *)(v30 + 36192),
          v27,
          CurrentWin32kSessionId,
          v22,
          v21);
      }
    }
  }
  v7 = 0x8000000000080000uLL;
  if ( (W32kEtwEnabledKeyword & 0x8000000000080000uLL) != 0
    && (unsigned __int8)(byte_140293DD8 - 1) > 2u
    && (qword_140293DC0 & 0x8000000000080000uLL) != 0
    && (qword_140293DC8 & 0x8000000000080000uLL) == qword_140293DC8 )
  {
    v8 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    for ( i = *(_QWORD *)(W32GetUserSessionState(v5, 0x8000000000080000uLL) + 63288); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
        goto LABEL_19;
      v10 = *(_QWORD *)(i + 16);
LABEL_16:
      if ( v10 )
        break;
    }
    for ( j = *(_QWORD **)(v10 + 176); ; j = (_QWORD *)*j )
    {
      if ( j == (_QWORD *)(v10 + 176) )
      {
        v10 = *(_QWORD *)(v10 + 32);
        goto LABEL_16;
      }
      ThreadId = (unsigned int)PsGetThreadId((PETHREAD)*(j - 96));
      ThreadInfoFlags = EtwpGetThreadInfoFlags((struct tagTHREADINFO *const)(j - 96));
      v14 = *((_DWORD *)j + 134);
      v15 = ThreadInfoFlags;
      v16 = v14 ? (unsigned int)(v8 - v14) : 0LL;
      v17 = *(j - 38);
      if ( !v17 )
        break;
      v7 = (unsigned int)(v8 - *(_DWORD *)(v17 + 528));
      if ( !*(_DWORD *)(v17 + 40) )
        goto LABEL_26;
      v5 = (unsigned int)(v8 - *(_DWORD *)(*(_QWORD *)(v17 + 24) + 48LL));
LABEL_27:
      if ( (Microsoft_Windows_Win32kEnableBits & 0x80u) != 0LL )
        McTemplateK0qqqqq_EtwWriteTransfer(
          v5,
          (const EVENT_DESCRIPTOR *)ThreadInfoRundownEvent,
          v16,
          ThreadId,
          v15,
          v16,
          v7,
          v5);
    }
    v7 = 0;
LABEL_26:
    v5 = 0;
    goto LABEL_27;
  }
LABEL_19:
  UserSessionSwitchLeaveCritWithNonPaged(v5, v7);
}

```

## disassembly

```asm
0x1400a3b28  push    rbx
0x1400a3b2a  push    rbp
0x1400a3b2b  push    rsi
0x1400a3b2c  push    rdi
0x1400a3b2d  push    r12
0x1400a3b2f  push    r14
0x1400a3b31  push    r15
0x1400a3b33  sub     rsp, 40h
0x1400a3b37  call    cs:__imp_W32GetUserSessionState
0x1400a3b3e  nop     dword ptr [rax+rax+00h]
0x1400a3b43  mov     rdi, rax
0x1400a3b46  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400a3b4d  nop     dword ptr [rax+rax+00h]
0x1400a3b52  mov     rbx, rax
0x1400a3b55  call    cs:__imp_KeEnterCriticalRegion
0x1400a3b5c  nop     dword ptr [rax+rax+00h]
0x1400a3b61  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x1400a3b64  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400a3b67  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400a3b6c  cmp     qword ptr [rbx], 0
0x1400a3b70  jz      loc_1400A3D6C
0x1400a3b76  call    IsThreadCrossSessionAttached
0x1400a3b7b  test    eax, eax
0x1400a3b7d  jnz     loc_1400A3D68
0x1400a3b83  mov     rcx, [rbx]
0x1400a3b86  mov     byte ptr [rcx+6ACh], 1
0x1400a3b8d  mov     [rdi+10h], rcx
0x1400a3b91  test    rcx, rcx
0x1400a3b94  jnz     loc_1400A3D35
0x1400a3b9a  mov     rdx, 8000000000040000h
0x1400a3ba4  mov     r14, 0FFFFF78000000320h
0x1400a3bae  test    cs:W32kEtwEnabledKeyword, rdx
0x1400a3bb5  mov     r15, 0FFFFF78000000004h
0x1400a3bbf  jz      short loc_1400A3C02
0x1400a3bc1  mov     al, cs:byte_140293DD8
0x1400a3bc7  dec     al
0x1400a3bc9  cmp     al, 2
0x1400a3bcb  jbe     short loc_1400A3C02
0x1400a3bcd  test    cs:qword_140293DC0, rdx
0x1400a3bd4  jz      short loc_1400A3C02
0x1400a3bd6  mov     rax, cs:qword_140293DC8
0x1400a3bdd  and     rax, rdx
0x1400a3be0  cmp     rax, cs:qword_140293DC8
0x1400a3be7  jnz     short loc_1400A3C02
0x1400a3be9  call    cs:__imp_W32GetUserSessionState
0x1400a3bf0  nop     dword ptr [rax+rax+00h]
0x1400a3bf5  cmp     dword ptr [rax+8D58h], 0
0x1400a3bfc  jnz     loc_1400A3D73
0x1400a3c02  mov     rdx, 8000000000080000h
0x1400a3c0c  test    cs:W32kEtwEnabledKeyword, rdx
0x1400a3c13  jz      short loc_1400A3C72
0x1400a3c15  mov     al, cs:byte_140293DD8
0x1400a3c1b  dec     al
0x1400a3c1d  cmp     al, 2
0x1400a3c1f  jbe     short loc_1400A3C72
0x1400a3c21  test    cs:qword_140293DC0, rdx
0x1400a3c28  jz      short loc_1400A3C72
0x1400a3c2a  mov     rax, cs:qword_140293DC8
0x1400a3c31  and     rax, rdx
0x1400a3c34  cmp     rax, cs:qword_140293DC8
0x1400a3c3b  jnz     short loc_1400A3C72
0x1400a3c3d  mov     rax, [r14]
0x1400a3c40  mov     ebp, [r15]
0x1400a3c43  imul    rbp, rax
0x1400a3c47  shr     rbp, 18h
0x1400a3c4b  call    cs:__imp_W32GetUserSessionState
0x1400a3c52  nop     dword ptr [rax+rax+00h]
0x1400a3c57  mov     rdi, [rax+0F738h]
0x1400a3c5e  jmp     short loc_1400A3C6D
0x1400a3c60  mov     rbx, [rdi+10h]
0x1400a3c64  test    rbx, rbx
0x1400a3c67  jnz     short loc_1400A3C87
0x1400a3c69  mov     rdi, [rdi+8]
0x1400a3c6d  test    rdi, rdi
0x1400a3c70  jnz     short loc_1400A3C60
0x1400a3c72  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400a3c77  add     rsp, 40h
0x1400a3c7b  pop     r15
0x1400a3c7d  pop     r14
0x1400a3c7f  pop     r12
0x1400a3c81  pop     rdi
0x1400a3c82  pop     rsi
0x1400a3c83  pop     rbp
0x1400a3c84  pop     rbx
0x1400a3c85  retn
0x1400a3c87  lea     r14, [rbx+0B0h]
0x1400a3c8e  mov     rsi, [r14]
0x1400a3c91  cmp     rsi, r14
0x1400a3c94  jz      short loc_1400A3D05
0x1400a3c96  lea     r15, [rsi-300h]
0x1400a3c9d  mov     rcx, [r15]; Thread
0x1400a3ca0  call    cs:__imp_PsGetThreadId
0x1400a3ca7  nop     dword ptr [rax+rax+00h]
0x1400a3cac  mov     rcx, r15; struct tagTHREADINFO *
0x1400a3caf  mov     r12, rax
0x1400a3cb2  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x1400a3cb7  mov     ecx, [r15+518h]
0x1400a3cbe  mov     r10d, eax
0x1400a3cc1  test    ecx, ecx
0x1400a3cc3  jz      short loc_1400A3CF5
0x1400a3cc5  mov     r8d, ebp
0x1400a3cc8  sub     r8d, ecx
0x1400a3ccb  mov     rax, [r15+1D0h]
0x1400a3cd2  test    rax, rax
0x1400a3cd5  jz      short loc_1400A3D31
0x1400a3cd7  mov     edx, ebp
0x1400a3cd9  sub     edx, [rax+210h]
0x1400a3cdf  cmp     dword ptr [rax+28h], 0
0x1400a3ce3  jnz     short loc_1400A3CFA
0x1400a3ce5  xor     ecx, ecx
0x1400a3ce7  cmp     byte ptr cs:Microsoft_Windows_Win32kEnableBits, 0
0x1400a3cee  jl      short loc_1400A3D0E
0x1400a3cf0  mov     rsi, [rsi]
0x1400a3cf3  jmp     short loc_1400A3C91
0x1400a3cf5  xor     r8d, r8d
0x1400a3cf8  jmp     short loc_1400A3CCB
0x1400a3cfa  mov     rax, [rax+18h]
0x1400a3cfe  mov     ecx, ebp
0x1400a3d00  sub     ecx, [rax+30h]
0x1400a3d03  jmp     short loc_1400A3CE7
0x1400a3d05  mov     rbx, [rbx+20h]
0x1400a3d09  jmp     loc_1400A3C64
0x1400a3d0e  mov     [rsp+78h+var_40], ecx
0x1400a3d12  mov     r9d, r12d
0x1400a3d15  mov     [rsp+78h+var_48], edx
0x1400a3d19  lea     rdx, ThreadInfoRundownEvent
0x1400a3d20  mov     [rsp+78h+var_50], r8d
0x1400a3d25  mov     [rsp+78h+var_58], r10d
0x1400a3d2a  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1400a3d2f  jmp     short loc_1400A3CF0
0x1400a3d31  xor     edx, edx
0x1400a3d33  jmp     short loc_1400A3CE5
0x1400a3d35  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400a3d3a  test    al, al
0x1400a3d3c  jz      loc_1400A3B9A
0x1400a3d42  lea     rbx, [rdi+4C40h]
0x1400a3d49  mov     rcx, rbx
0x1400a3d4c  call    DestroySharedUserCritDeferredUnlockList
0x1400a3d51  lea     rcx, [rbx+38h]
0x1400a3d55  call    DestroyDeferredUnlockObjectAssignmentList
0x1400a3d5a  lea     rcx, [rbx+28h]
0x1400a3d5e  call    DestroyDeferredUnlockObjectAssignmentList
0x1400a3d63  jmp     loc_1400A3B9A
0x1400a3d68  or      dword ptr [rbx+18h], 2
0x1400a3d6c  xor     ecx, ecx
0x1400a3d6e  jmp     loc_1400A3B8D
0x1400a3d73  mov     rax, [r14]
0x1400a3d76  mov     ebp, [r15]
0x1400a3d79  imul    rbp, rax
0x1400a3d7d  shr     rbp, 18h
0x1400a3d81  call    cs:__imp_W32GetUserSessionState
0x1400a3d88  nop     dword ptr [rax+rax+00h]
0x1400a3d8d  sub     ebp, [rax+8D5Ch]
0x1400a3d93  cmp     ebp, 0C8h
0x1400a3d99  jb      loc_1400A3C02
0x1400a3d9f  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 40h
0x1400a3da6  jz      loc_1400A3C02
0x1400a3dac  call    cs:__imp_W32GetUserSessionState
0x1400a3db3  nop     dword ptr [rax+rax+00h]
0x1400a3db8  mov     esi, [rax+8D58h]
0x1400a3dbe  call    W32GetCurrentWin32kSessionId
0x1400a3dc3  mov     edi, eax
0x1400a3dc5  call    cs:__imp_W32GetUserSessionState
0x1400a3dcc  nop     dword ptr [rax+rax+00h]
0x1400a3dd1  mov     ebx, [rax+8D64h]
0x1400a3dd7  call    cs:__imp_W32GetUserSessionState
0x1400a3dde  nop     dword ptr [rax+rax+00h]
0x1400a3de3  mov     [rsp+78h+var_40], ebp
0x1400a3de7  lea     rdx, WaitCursorEvent
0x1400a3dee  mov     [rsp+78h+var_48], esi
0x1400a3df2  mov     [rsp+78h+var_50], edi
0x1400a3df6  mov     r9d, [rax+8D60h]
0x1400a3dfd  mov     [rsp+78h+var_58], ebx
0x1400a3e01  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1400a3e06  jmp     loc_1400A3C02
```
