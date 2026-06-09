# MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)

- ea: `0x140012794`
- end: `0x1400128d0`
- name: `??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ`
- size: `316`
- prototype: `void __fastcall(MaybeEnterLeaveCritSharedOnly *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002a520`
- `0x14002b850`
- `0x1400ed9a0`
- `0x140178100`

## callees

- `0x140012794`
- `0x140012dc0`
- `0x140012df0`
- `0x140012fa0`
- `0x140013130`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400128a7`
- `ntoskrnl!KeBugCheckEx` at `0x1400128a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012869`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012869`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400128c2`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400128c2`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400127ce`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400127ce`
- `ntoskrnl!ExReleaseFastResource` at `0x14001285d`
- `ntoskrnl!ExReleaseFastResource` at `0x14001285d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400127f3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400127f3`
- `WIN32K!W32GetUserSessionState` at `0x1400127a7`
- `WIN32K!W32GetUserSessionState` at `0x1400127e4`
- `WIN32K!W32GetUserSessionState` at `0x1400127a7`
- `WIN32K!W32GetUserSessionState` at `0x1400127e4`

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
0x140012794  mov     [rsp+arg_0], rbx
0x140012799  push    rdi
0x14001279a  sub     rsp, 30h
0x14001279e  cmp     byte ptr [rcx], 0
0x1400127a1  jz      loc_140012875
0x1400127a7  call    cs:__imp_W32GetUserSessionState
0x1400127ae  nop     dword ptr [rax+rax+00h]
0x1400127b3  mov     rbx, rax
0x1400127b6  mov     r8d, [rax+10D00h]; Adjustment
0x1400127bd  test    r8d, r8d
0x1400127c0  jz      short loc_1400127E4
0x1400127c2  mov     rcx, [rax+10CF8h]; Semaphore
0x1400127c9  xor     r9d, r9d; Wait
0x1400127cc  xor     edx, edx; Increment
0x1400127ce  call    cs:__imp_KeReleaseSemaphore
0x1400127d5  nop     dword ptr [rax+rax+00h]
0x1400127da  mov     dword ptr [rbx+10D00h], 0
0x1400127e4  call    cs:__imp_W32GetUserSessionState
0x1400127eb  nop     dword ptr [rax+rax+00h]
0x1400127f0  mov     rdi, rax
0x1400127f3  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400127fa  nop     dword ptr [rax+rax+00h]
0x1400127ff  mov     rbx, rax
0x140012802  mov     ecx, [rax+18h]
0x140012805  and     cl, 0Ch
0x140012808  cmp     cl, 8
0x14001280b  jnz     short loc_140012835
0x14001280d  call    UpdateDirtyVisRgnTrackers
0x140012812  lea     rcx, [rdi+4C40h]
0x140012819  mov     dword ptr [rcx+64h], 0
0x140012820  mov     qword ptr [rcx+50h], 0
0x140012828  call    DestroyExclusiveUserCritDeferredUnlockList
0x14001282d  mov     qword ptr [rdi+10h], 0
0x140012835  mov     rcx, [rbx]
0x140012838  test    rcx, rcx
0x14001283b  jnz     short loc_140012881
0x14001283d  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x140012842  test    eax, eax
0x140012844  jnz     short loc_140012891
0x140012846  call    EtwTraceReleaseUserCrit
0x14001284b  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14001284f  mov     eax, [rbx+18h]
0x140012852  test    al, 10h
0x140012854  jnz     short loc_1400128B4
0x140012856  mov     rcx, [rdi]
0x140012859  lea     rdx, [rbx+20h]
0x14001285d  call    cs:__imp_ExReleaseFastResource
0x140012864  nop     dword ptr [rax+rax+00h]
0x140012869  call    cs:__imp_KeLeaveCriticalRegion
0x140012870  nop     dword ptr [rax+rax+00h]
0x140012875  mov     rbx, [rsp+38h+arg_0]
0x14001287a  add     rsp, 30h
0x14001287e  pop     rdi
0x14001287f  retn
0x140012881  mov     eax, [rbx+18h]
0x140012884  test    al, 2
0x140012886  jnz     short loc_14001283D
0x140012888  mov     byte ptr [rcx+6ACh], 0
0x14001288f  jmp     short loc_14001283D
0x140012891  mov     edx, eax; BugCheckParameter1
0x140012893  xor     r9d, r9d; BugCheckParameter3
0x140012896  xor     r8d, r8d; BugCheckParameter2
0x140012899  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x1400128a2  mov     ecx, 160h; BugCheckCode
0x1400128a7  call    cs:__imp_KeBugCheckEx
0x1400128b4  mov     rcx, gs:188h
0x1400128bd  mov     r8, rbx
0x1400128c0  xor     edx, edx
0x1400128c2  call    cs:__imp_PsSetThreadWin32Thread
0x1400128c9  nop     dword ptr [rax+rax+00h]
0x1400128ce  jmp     short loc_140012856
```
