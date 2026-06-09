# MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)

- ea: `0x14001b904`
- end: `0x14001ba40`
- name: `??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ`
- size: `316`
- prototype: `void __fastcall(MaybeEnterLeaveCritSharedOnly *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400337a0`
- `0x140034ad0`
- `0x1400eb020`
- `0x140178c70`

## callees

- `0x14001b904`
- `0x14001bf30`
- `0x14001bf60`
- `0x14001c110`
- `0x14001c2a0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001ba17`
- `ntoskrnl!KeBugCheckEx` at `0x14001ba17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b9d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b9d9`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001ba32`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001ba32`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001b93e`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001b93e`
- `ntoskrnl!ExReleaseFastResource` at `0x14001b9cd`
- `ntoskrnl!ExReleaseFastResource` at `0x14001b9cd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001b963`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001b963`
- `WIN32K!W32GetUserSessionState` at `0x14001b917`
- `WIN32K!W32GetUserSessionState` at `0x14001b954`
- `WIN32K!W32GetUserSessionState` at `0x14001b917`
- `WIN32K!W32GetUserSessionState` at `0x14001b954`

## pseudocode

```c
void __fastcall MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(MaybeEnterLeaveCritSharedOnly *this)
{
  __int64 UserSessionState; // rax
  __int64 v2; // rcx
  __int64 v3; // rbx
  LONG v4; // r8d
  __int64 v5; // rdi
  __int64 v6; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  if ( *(_BYTE *)this )
  {
    UserSessionState = W32GetUserSessionState(this);
    v3 = UserSessionState;
    v4 = *(_DWORD *)(UserSessionState + 68864);
    if ( v4 )
    {
      KeReleaseSemaphore(*(PRKSEMAPHORE *)(UserSessionState + 68856), 0, v4, 0);
      *(_DWORD *)(v3 + 68864) = 0;
    }
    v5 = W32GetUserSessionState(v2);
    CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v6);
    if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
    {
      UpdateDirtyVisRgnTrackers();
      *(_DWORD *)(v5 + 19620) = 0;
      *(_QWORD *)(v5 + 19600) = 0;
      DestroyExclusiveUserCritDeferredUnlockList();
      *(_QWORD *)(v5 + 16) = 0;
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
    ExReleaseFastResource(*(_QWORD *)v5, CurrentThreadWin32Thread + 8);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x14001b904  mov     [rsp+arg_0], rbx
0x14001b909  push    rdi
0x14001b90a  sub     rsp, 30h
0x14001b90e  cmp     byte ptr [rcx], 0
0x14001b911  jz      loc_14001B9E5
0x14001b917  call    cs:__imp_W32GetUserSessionState
0x14001b91e  nop     dword ptr [rax+rax+00h]
0x14001b923  mov     rbx, rax
0x14001b926  mov     r8d, [rax+10D00h]; Adjustment
0x14001b92d  test    r8d, r8d
0x14001b930  jz      short loc_14001B954
0x14001b932  mov     rcx, [rax+10CF8h]; Semaphore
0x14001b939  xor     r9d, r9d; Wait
0x14001b93c  xor     edx, edx; Increment
0x14001b93e  call    cs:__imp_KeReleaseSemaphore
0x14001b945  nop     dword ptr [rax+rax+00h]
0x14001b94a  mov     dword ptr [rbx+10D00h], 0
0x14001b954  call    cs:__imp_W32GetUserSessionState
0x14001b95b  nop     dword ptr [rax+rax+00h]
0x14001b960  mov     rdi, rax
0x14001b963  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001b96a  nop     dword ptr [rax+rax+00h]
0x14001b96f  mov     rbx, rax
0x14001b972  mov     ecx, [rax+18h]
0x14001b975  and     cl, 0Ch
0x14001b978  cmp     cl, 8
0x14001b97b  jnz     short loc_14001B9A5
0x14001b97d  call    UpdateDirtyVisRgnTrackers
0x14001b982  lea     rcx, [rdi+4C40h]
0x14001b989  mov     dword ptr [rcx+64h], 0
0x14001b990  mov     qword ptr [rcx+50h], 0
0x14001b998  call    DestroyExclusiveUserCritDeferredUnlockList
0x14001b99d  mov     qword ptr [rdi+10h], 0
0x14001b9a5  mov     rcx, [rbx]
0x14001b9a8  test    rcx, rcx
0x14001b9ab  jnz     short loc_14001B9F1
0x14001b9ad  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x14001b9b2  test    eax, eax
0x14001b9b4  jnz     short loc_14001BA01
0x14001b9b6  call    EtwTraceReleaseUserCrit
0x14001b9bb  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14001b9bf  mov     eax, [rbx+18h]
0x14001b9c2  test    al, 10h
0x14001b9c4  jnz     short loc_14001BA24
0x14001b9c6  mov     rcx, [rdi]
0x14001b9c9  lea     rdx, [rbx+20h]
0x14001b9cd  call    cs:__imp_ExReleaseFastResource
0x14001b9d4  nop     dword ptr [rax+rax+00h]
0x14001b9d9  call    cs:__imp_KeLeaveCriticalRegion
0x14001b9e0  nop     dword ptr [rax+rax+00h]
0x14001b9e5  mov     rbx, [rsp+38h+arg_0]
0x14001b9ea  add     rsp, 30h
0x14001b9ee  pop     rdi
0x14001b9ef  retn
0x14001b9f1  mov     eax, [rbx+18h]
0x14001b9f4  test    al, 2
0x14001b9f6  jnz     short loc_14001B9AD
0x14001b9f8  mov     byte ptr [rcx+6ACh], 0
0x14001b9ff  jmp     short loc_14001B9AD
0x14001ba01  mov     edx, eax; BugCheckParameter1
0x14001ba03  xor     r9d, r9d; BugCheckParameter3
0x14001ba06  xor     r8d, r8d; BugCheckParameter2
0x14001ba09  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14001ba12  mov     ecx, 160h; BugCheckCode
0x14001ba17  call    cs:__imp_KeBugCheckEx
0x14001ba24  mov     rcx, gs:188h
0x14001ba2d  mov     r8, rbx
0x14001ba30  xor     edx, edx
0x14001ba32  call    cs:__imp_PsSetThreadWin32Thread
0x14001ba39  nop     dword ptr [rax+rax+00h]
0x14001ba3e  jmp     short loc_14001B9C6
```
