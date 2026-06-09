# UserSessionSwitchLeaveCritWithNonPaged

- ea: `0x140012c80`
- end: `0x140012dab`
- name: `UserSessionSwitchLeaveCritWithNonPaged`
- size: `299`
- prototype: ``
- caller_count: `200`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f680`
- `0x140010e18`
- `0x140011074`
- `0x140014ea0`
- `0x1400269a0`
- `0x140028b30`
- `0x140029350`
- `0x1400297a0`
- `0x140029dac`
- `0x14002a430`
- `0x14002b080`
- `0x14002b460`
- `0x14002b9b0`
- `0x14002c030`
- `0x14002c090`
- `0x14002c220`
- `0x14002c3cc`
- `0x14002cf40`
- `0x14002d824`
- `0x14003e100`
- `0x1400543dc`
- `0x1400568a0`
- `0x140058010`
- `0x140059e38`
- `0x14005a164`
- `0x14005b680`
- `0x14005ed50`
- `0x140060b24`
- `0x140061ec4`
- `0x140067180`
- `0x140068fe0`
- `0x14006e1f0`
- `0x14006f5b0`
- `0x140076608`
- `0x140083340`
- `0x140089e10`
- `0x14008a5e0`
- `0x14009961c`
- `0x140099ff8`
- `0x14009a668`
- `0x14009ac00`
- `0x14009b48c`
- `0x14009bdf0`
- `0x14009dc74`
- `0x1400a4660`
- `0x1400a4810`
- `0x1400aae90`
- `0x1400ac930`
- `0x1400acd90`
- `0x1400b00d0`

## callees

- `0x140012c80`
- `0x140012dc0`
- `0x140012df0`
- `0x140012fa0`
- `0x140013130`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140012d82`
- `ntoskrnl!KeBugCheckEx` at `0x140012d82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012d43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012d43`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012d9d`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140012d9d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140012cb8`
- `ntoskrnl!KeReleaseSemaphore` at `0x140012cb8`
- `ntoskrnl!ExReleaseFastResource` at `0x140012d37`
- `ntoskrnl!ExReleaseFastResource` at `0x140012d37`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012cd9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012cd9`
- `WIN32K!W32GetUserSessionState` at `0x140012c8f`
- `WIN32K!W32GetUserSessionState` at `0x140012cca`
- `WIN32K!W32GetUserSessionState` at `0x140012c8f`
- `WIN32K!W32GetUserSessionState` at `0x140012cca`

## pseudocode

```c
void __fastcall UserSessionSwitchLeaveCritWithNonPaged(__int64 a1)
{
  __int64 UserSessionState; // rax
  __int64 v2; // rcx
  __int64 v3; // rbx
  LONG v4; // r8d
  __int64 v5; // rdi
  __int64 v6; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  UserSessionState = W32GetUserSessionState(a1);
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

```

## disassembly

```asm
0x140012c80  mov     [rsp+arg_0], rbx; ReleaseUserCriticalSection
0x140012c85  mov     [rsp+arg_8], rsi
0x140012c8a  push    rdi
0x140012c8b  sub     rsp, 30h
0x140012c8f  call    cs:__imp_W32GetUserSessionState
0x140012c96  nop     dword ptr [rax+rax+00h]
0x140012c9b  xor     esi, esi
0x140012c9d  mov     rbx, rax
0x140012ca0  mov     r8d, [rax+10D00h]; Adjustment
0x140012ca7  test    r8d, r8d
0x140012caa  jz      short loc_140012CCA
0x140012cac  mov     rcx, [rax+10CF8h]; Semaphore
0x140012cb3  xor     r9d, r9d; Wait
0x140012cb6  xor     edx, edx; Increment
0x140012cb8  call    cs:__imp_KeReleaseSemaphore
0x140012cbf  nop     dword ptr [rax+rax+00h]
0x140012cc4  mov     [rbx+10D00h], esi
0x140012cca  call    cs:__imp_W32GetUserSessionState
0x140012cd1  nop     dword ptr [rax+rax+00h]
0x140012cd6  mov     rdi, rax
0x140012cd9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140012ce0  nop     dword ptr [rax+rax+00h]
0x140012ce5  mov     rbx, rax
0x140012ce8  mov     ecx, [rax+18h]
0x140012ceb  and     cl, 0Ch
0x140012cee  cmp     cl, 8
0x140012cf1  jnz     short loc_140012D0F
0x140012cf3  call    UpdateDirtyVisRgnTrackers
0x140012cf8  lea     rcx, [rdi+4C40h]
0x140012cff  mov     [rcx+64h], esi
0x140012d02  mov     [rcx+50h], rsi
0x140012d06  call    DestroyExclusiveUserCritDeferredUnlockList
0x140012d0b  mov     [rdi+10h], rsi
0x140012d0f  mov     rcx, [rbx]
0x140012d12  test    rcx, rcx
0x140012d15  jnz     short loc_140012D60
0x140012d17  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x140012d1c  test    eax, eax
0x140012d1e  jnz     short loc_140012D70
0x140012d20  call    EtwTraceReleaseUserCrit
0x140012d25  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x140012d29  mov     eax, [rbx+18h]
0x140012d2c  test    al, 10h
0x140012d2e  jnz     short loc_140012D8F
0x140012d30  mov     rcx, [rdi]
0x140012d33  lea     rdx, [rbx+20h]
0x140012d37  call    cs:__imp_ExReleaseFastResource
0x140012d3e  nop     dword ptr [rax+rax+00h]
0x140012d43  call    cs:__imp_KeLeaveCriticalRegion
0x140012d4a  nop     dword ptr [rax+rax+00h]
0x140012d4f  mov     rbx, [rsp+38h+arg_0]
0x140012d54  mov     rsi, [rsp+38h+arg_8]
0x140012d59  add     rsp, 30h
0x140012d5d  pop     rdi
0x140012d5e  retn
0x140012d60  mov     eax, [rbx+18h]
0x140012d63  test    al, 2
0x140012d65  jnz     short loc_140012D17
0x140012d67  mov     [rcx+6ACh], sil
0x140012d6e  jmp     short loc_140012D17
0x140012d70  mov     edx, eax; BugCheckParameter1
0x140012d72  xor     r9d, r9d; BugCheckParameter3
0x140012d75  xor     r8d, r8d; BugCheckParameter2
0x140012d78  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140012d7d  mov     ecx, 160h; BugCheckCode
0x140012d82  call    cs:__imp_KeBugCheckEx
0x140012d8f  mov     rcx, gs:188h
0x140012d98  mov     r8, rbx
0x140012d9b  xor     edx, edx
0x140012d9d  call    cs:__imp_PsSetThreadWin32Thread
0x140012da4  nop     dword ptr [rax+rax+00h]
0x140012da9  jmp     short loc_140012D30
```
