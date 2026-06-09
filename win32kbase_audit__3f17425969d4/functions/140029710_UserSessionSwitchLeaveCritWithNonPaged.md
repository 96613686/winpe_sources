# UserSessionSwitchLeaveCritWithNonPaged

- ea: `0x140029710`
- end: `0x14002983b`
- name: `UserSessionSwitchLeaveCritWithNonPaged`
- size: `299`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `201`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000e520`
- `0x140016c1c`
- `0x140018870`
- `0x1400198d0`
- `0x140024a10`
- `0x1400278a0`
- `0x140027afc`
- `0x14002a440`
- `0x14002a870`
- `0x140036f70`
- `0x140039b30`
- `0x1400415b0`
- `0x1400467c0`
- `0x140047b80`
- `0x14004ebd8`
- `0x140062230`
- `0x1400624f0`
- `0x140063ef0`
- `0x140064560`
- `0x140064b00`
- `0x14006538c`
- `0x140065cf0`
- `0x140067b74`
- `0x14006eb00`
- `0x14006ebf0`
- `0x14006f3d0`
- `0x14006f890`
- `0x14006fe9c`
- `0x1400709b0`
- `0x140070d90`
- `0x14008e8cc`
- `0x14009ed0c`
- `0x1400a0a00`
- `0x1400a2178`
- `0x1400a3b28`
- `0x1400b68d0`
- `0x1400b9be0`
- `0x1400bb350`
- `0x1400bd178`
- `0x1400bd4a4`
- `0x1400be9c0`
- `0x1400c1e10`
- `0x1400c3e10`
- `0x1400c51a4`
- `0x1400c9c70`
- `0x1400caf00`
- `0x1400cbe70`
- `0x1400cf0ec`
- `0x1400cf1d8`
- `0x1400cff38`

## callees

- `0x140029710`
- `0x140029850`
- `0x140029880`
- `0x140029a30`
- `0x140029bc0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140029812`
- `ntoskrnl!KeBugCheckEx` at `0x140029812`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400297d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400297d3`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14002982d`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14002982d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140029748`
- `ntoskrnl!KeReleaseSemaphore` at `0x140029748`
- `ntoskrnl!ExReleaseFastResource` at `0x1400297c7`
- `ntoskrnl!ExReleaseFastResource` at `0x1400297c7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140029769`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140029769`
- `WIN32K!W32GetUserSessionState` at `0x14002971f`
- `WIN32K!W32GetUserSessionState` at `0x14002975a`
- `WIN32K!W32GetUserSessionState` at `0x14002971f`
- `WIN32K!W32GetUserSessionState` at `0x14002975a`

## pseudocode

```c
void __fastcall UserSessionSwitchLeaveCritWithNonPaged(__int64 a1, __int64 a2)
{
  __int64 UserSessionState; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rbx
  LONG v6; // r8d
  __int64 v7; // rdi
  __int64 v8; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  UserSessionState = W32GetUserSessionState(a1, a2);
  v5 = UserSessionState;
  v6 = *(_DWORD *)(UserSessionState + 68864);
  if ( v6 )
  {
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(UserSessionState + 68856), 0, v6, 0);
    *(_DWORD *)(v5 + 68864) = 0;
  }
  v7 = W32GetUserSessionState(v4, v3);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v8);
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(v7 + 19620) = 0;
    *(_QWORD *)(v7 + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(v7 + 16) = 0;
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
  ExReleaseFastResource(*(_QWORD *)v7, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140029710  mov     [rsp+arg_0], rbx; ReleaseUserCriticalSection
0x140029715  mov     [rsp+arg_8], rsi
0x14002971a  push    rdi
0x14002971b  sub     rsp, 30h
0x14002971f  call    cs:__imp_W32GetUserSessionState
0x140029726  nop     dword ptr [rax+rax+00h]
0x14002972b  xor     esi, esi
0x14002972d  mov     rbx, rax
0x140029730  mov     r8d, [rax+10D00h]; Adjustment
0x140029737  test    r8d, r8d
0x14002973a  jz      short loc_14002975A
0x14002973c  mov     rcx, [rax+10CF8h]; Semaphore
0x140029743  xor     r9d, r9d; Wait
0x140029746  xor     edx, edx; Increment
0x140029748  call    cs:__imp_KeReleaseSemaphore
0x14002974f  nop     dword ptr [rax+rax+00h]
0x140029754  mov     [rbx+10D00h], esi
0x14002975a  call    cs:__imp_W32GetUserSessionState
0x140029761  nop     dword ptr [rax+rax+00h]
0x140029766  mov     rdi, rax
0x140029769  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140029770  nop     dword ptr [rax+rax+00h]
0x140029775  mov     rbx, rax
0x140029778  mov     ecx, [rax+18h]
0x14002977b  and     cl, 0Ch
0x14002977e  cmp     cl, 8
0x140029781  jnz     short loc_14002979F
0x140029783  call    UpdateDirtyVisRgnTrackers
0x140029788  lea     rcx, [rdi+4C40h]
0x14002978f  mov     [rcx+64h], esi
0x140029792  mov     [rcx+50h], rsi
0x140029796  call    DestroyExclusiveUserCritDeferredUnlockList
0x14002979b  mov     [rdi+10h], rsi
0x14002979f  mov     rcx, [rbx]
0x1400297a2  test    rcx, rcx
0x1400297a5  jnz     short loc_1400297F0
0x1400297a7  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1400297ac  test    eax, eax
0x1400297ae  jnz     short loc_140029800
0x1400297b0  call    EtwTraceReleaseUserCrit
0x1400297b5  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x1400297b9  mov     eax, [rbx+18h]
0x1400297bc  test    al, 10h
0x1400297be  jnz     short loc_14002981F
0x1400297c0  mov     rcx, [rdi]
0x1400297c3  lea     rdx, [rbx+20h]
0x1400297c7  call    cs:__imp_ExReleaseFastResource
0x1400297ce  nop     dword ptr [rax+rax+00h]
0x1400297d3  call    cs:__imp_KeLeaveCriticalRegion
0x1400297da  nop     dword ptr [rax+rax+00h]
0x1400297df  mov     rbx, [rsp+38h+arg_0]
0x1400297e4  mov     rsi, [rsp+38h+arg_8]
0x1400297e9  add     rsp, 30h
0x1400297ed  pop     rdi
0x1400297ee  retn
0x1400297f0  mov     eax, [rbx+18h]
0x1400297f3  test    al, 2
0x1400297f5  jnz     short loc_1400297A7
0x1400297f7  mov     [rcx+6ACh], sil
0x1400297fe  jmp     short loc_1400297A7
0x140029800  mov     edx, eax; BugCheckParameter1
0x140029802  xor     r9d, r9d; BugCheckParameter3
0x140029805  xor     r8d, r8d; BugCheckParameter2
0x140029808  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x14002980d  mov     ecx, 160h; BugCheckCode
0x140029812  call    cs:__imp_KeBugCheckEx
0x14002981f  mov     rcx, gs:188h
0x140029828  mov     r8, rbx
0x14002982b  xor     edx, edx
0x14002982d  call    cs:__imp_PsSetThreadWin32Thread
0x140029834  nop     dword ptr [rax+rax+00h]
0x140029839  jmp     short loc_1400297C0
```
