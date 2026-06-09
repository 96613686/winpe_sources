# UserSessionSwitchLeaveCritWithNonPaged

- ea: `0x14001bdf0`
- end: `0x14001bf1b`
- name: `UserSessionSwitchLeaveCritWithNonPaged`
- size: `299`
- prototype: `__int64(void)`
- caller_count: `200`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400187f0`
- `0x140019f88`
- `0x14001a1e4`
- `0x14001e010`
- `0x14002fc20`
- `0x140031db0`
- `0x1400325d0`
- `0x140032a20`
- `0x14003302c`
- `0x1400336b0`
- `0x140034300`
- `0x1400346e0`
- `0x140034c30`
- `0x1400352b0`
- `0x140035310`
- `0x1400354a0`
- `0x14003564c`
- `0x1400361c0`
- `0x140036aa4`
- `0x140047010`
- `0x14005d19c`
- `0x140064c30`
- `0x1400657c0`
- `0x140065fbc`
- `0x140066cd0`
- `0x14006a180`
- `0x14006f390`
- `0x140070750`
- `0x1400777a8`
- `0x1400844e0`
- `0x14008afb0`
- `0x14008b780`
- `0x14009041c`
- `0x140090df8`
- `0x140091468`
- `0x140091a00`
- `0x14009228c`
- `0x140092bf0`
- `0x140094a74`
- `0x14009b460`
- `0x14009b610`
- `0x1400a1c90`
- `0x1400a3730`
- `0x1400a3b90`
- `0x1400a5774`
- `0x1400a5860`
- `0x1400a65c8`
- `0x1400a76b8`
- `0x1400a8c30`
- `0x1400b0b38`

## callees

- `0x14001bdf0`
- `0x14001bf30`
- `0x14001bf60`
- `0x14001c110`
- `0x14001c2a0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001bef2`
- `ntoskrnl!KeBugCheckEx` at `0x14001bef2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001beb3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001beb3`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001bf0d`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14001bf0d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001be28`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001be28`
- `ntoskrnl!ExReleaseFastResource` at `0x14001bea7`
- `ntoskrnl!ExReleaseFastResource` at `0x14001bea7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001be49`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001be49`
- `WIN32K!W32GetUserSessionState` at `0x14001bdff`
- `WIN32K!W32GetUserSessionState` at `0x14001be3a`
- `WIN32K!W32GetUserSessionState` at `0x14001bdff`
- `WIN32K!W32GetUserSessionState` at `0x14001be3a`

## pseudocode

```c
void __fastcall UserSessionSwitchLeaveCritWithNonPaged(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 UserSessionState; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdi
  __int64 v9; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  v6 = UserSessionState;
  v7 = *(unsigned int *)(UserSessionState + 68864);
  if ( (_DWORD)v7 )
  {
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(UserSessionState + 68856), 0, v7, 0);
    *(_DWORD *)(v6 + 68864) = 0;
  }
  v8 = W32GetUserSessionState(v5, v4, v7);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v9);
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(v8 + 19620) = 0;
    *(_QWORD *)(v8 + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(v8 + 16) = 0;
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
  ExReleaseFastResource(*(_QWORD *)v8, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14001bdf0  mov     [rsp+arg_0], rbx; ReleaseUserCriticalSection
0x14001bdf5  mov     [rsp+arg_8], rsi
0x14001bdfa  push    rdi
0x14001bdfb  sub     rsp, 30h
0x14001bdff  call    cs:__imp_W32GetUserSessionState
0x14001be06  nop     dword ptr [rax+rax+00h]
0x14001be0b  xor     esi, esi
0x14001be0d  mov     rbx, rax
0x14001be10  mov     r8d, [rax+10D00h]; Adjustment
0x14001be17  test    r8d, r8d
0x14001be1a  jz      short loc_14001BE3A
0x14001be1c  mov     rcx, [rax+10CF8h]; Semaphore
0x14001be23  xor     r9d, r9d; Wait
0x14001be26  xor     edx, edx; Increment
0x14001be28  call    cs:__imp_KeReleaseSemaphore
0x14001be2f  nop     dword ptr [rax+rax+00h]
0x14001be34  mov     [rbx+10D00h], esi
0x14001be3a  call    cs:__imp_W32GetUserSessionState
0x14001be41  nop     dword ptr [rax+rax+00h]
0x14001be46  mov     rdi, rax
0x14001be49  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001be50  nop     dword ptr [rax+rax+00h]
0x14001be55  mov     rbx, rax
0x14001be58  mov     ecx, [rax+18h]
0x14001be5b  and     cl, 0Ch
0x14001be5e  cmp     cl, 8
0x14001be61  jnz     short loc_14001BE7F
0x14001be63  call    UpdateDirtyVisRgnTrackers
0x14001be68  lea     rcx, [rdi+4C40h]
0x14001be6f  mov     [rcx+64h], esi
0x14001be72  mov     [rcx+50h], rsi
0x14001be76  call    DestroyExclusiveUserCritDeferredUnlockList
0x14001be7b  mov     [rdi+10h], rsi
0x14001be7f  mov     rcx, [rbx]
0x14001be82  test    rcx, rcx
0x14001be85  jnz     short loc_14001BED0
0x14001be87  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x14001be8c  test    eax, eax
0x14001be8e  jnz     short loc_14001BEE0
0x14001be90  call    EtwTraceReleaseUserCrit
0x14001be95  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14001be99  mov     eax, [rbx+18h]
0x14001be9c  test    al, 10h
0x14001be9e  jnz     short loc_14001BEFF
0x14001bea0  mov     rcx, [rdi]
0x14001bea3  lea     rdx, [rbx+20h]
0x14001bea7  call    cs:__imp_ExReleaseFastResource
0x14001beae  nop     dword ptr [rax+rax+00h]
0x14001beb3  call    cs:__imp_KeLeaveCriticalRegion
0x14001beba  nop     dword ptr [rax+rax+00h]
0x14001bebf  mov     rbx, [rsp+38h+arg_0]
0x14001bec4  mov     rsi, [rsp+38h+arg_8]
0x14001bec9  add     rsp, 30h
0x14001becd  pop     rdi
0x14001bece  retn
0x14001bed0  mov     eax, [rbx+18h]
0x14001bed3  test    al, 2
0x14001bed5  jnz     short loc_14001BE87
0x14001bed7  mov     [rcx+6ACh], sil
0x14001bede  jmp     short loc_14001BE87
0x14001bee0  mov     edx, eax; BugCheckParameter1
0x14001bee2  xor     r9d, r9d; BugCheckParameter3
0x14001bee5  xor     r8d, r8d; BugCheckParameter2
0x14001bee8  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x14001beed  mov     ecx, 160h; BugCheckCode
0x14001bef2  call    cs:__imp_KeBugCheckEx
0x14001beff  mov     rcx, gs:188h
0x14001bf08  mov     r8, rbx
0x14001bf0b  xor     edx, edx
0x14001bf0d  call    cs:__imp_PsSetThreadWin32Thread
0x14001bf14  nop     dword ptr [rax+rax+00h]
0x14001bf19  jmp     short loc_14001BEA0
```
