# MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)

- ea: `0x140029224`
- end: `0x140029360`
- name: `??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ`
- size: `316`
- prototype: `void __fastcall(MaybeEnterLeaveCritSharedOnly *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006e420`
- `0x140071180`
- `0x1400f01b0`
- `0x14017ac50`

## callees

- `0x140029224`
- `0x140029850`
- `0x140029880`
- `0x140029a30`
- `0x140029bc0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140029337`
- `ntoskrnl!KeBugCheckEx` at `0x140029337`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400292f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400292f9`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140029352`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140029352`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002925e`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002925e`
- `ntoskrnl!ExReleaseFastResource` at `0x1400292ed`
- `ntoskrnl!ExReleaseFastResource` at `0x1400292ed`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140029283`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140029283`
- `WIN32K!W32GetUserSessionState` at `0x140029237`
- `WIN32K!W32GetUserSessionState` at `0x140029274`
- `WIN32K!W32GetUserSessionState` at `0x140029237`
- `WIN32K!W32GetUserSessionState` at `0x140029274`

## pseudocode

```c
void __fastcall MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(
        MaybeEnterLeaveCritSharedOnly *this,
        __int64 a2,
        __int64 a3)
{
  __int64 UserSessionState; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  if ( *(_BYTE *)this )
  {
    UserSessionState = W32GetUserSessionState(this, a2, a3);
    v6 = UserSessionState;
    v7 = *(unsigned int *)(UserSessionState + 68864);
    if ( (_DWORD)v7 )
    {
      KeReleaseSemaphore(*(PRKSEMAPHORE *)(UserSessionState + 68856), 0, v7, 0);
      *(_DWORD *)(v6 + 68864) = 0;
    }
    v8 = W32GetUserSessionState(v5, v4, v7);
    CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v10, v9, v11, v12);
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
}

```

## disassembly

```asm
0x140029224  mov     [rsp+arg_0], rbx
0x140029229  push    rdi
0x14002922a  sub     rsp, 30h
0x14002922e  cmp     byte ptr [rcx], 0
0x140029231  jz      loc_140029305
0x140029237  call    cs:__imp_W32GetUserSessionState
0x14002923e  nop     dword ptr [rax+rax+00h]
0x140029243  mov     rbx, rax
0x140029246  mov     r8d, [rax+10D00h]; Adjustment
0x14002924d  test    r8d, r8d
0x140029250  jz      short loc_140029274
0x140029252  mov     rcx, [rax+10CF8h]; Semaphore
0x140029259  xor     r9d, r9d; Wait
0x14002925c  xor     edx, edx; Increment
0x14002925e  call    cs:__imp_KeReleaseSemaphore
0x140029265  nop     dword ptr [rax+rax+00h]
0x14002926a  mov     dword ptr [rbx+10D00h], 0
0x140029274  call    cs:__imp_W32GetUserSessionState
0x14002927b  nop     dword ptr [rax+rax+00h]
0x140029280  mov     rdi, rax
0x140029283  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002928a  nop     dword ptr [rax+rax+00h]
0x14002928f  mov     rbx, rax
0x140029292  mov     ecx, [rax+18h]
0x140029295  and     cl, 0Ch
0x140029298  cmp     cl, 8
0x14002929b  jnz     short loc_1400292C5
0x14002929d  call    UpdateDirtyVisRgnTrackers
0x1400292a2  lea     rcx, [rdi+4C40h]
0x1400292a9  mov     dword ptr [rcx+64h], 0
0x1400292b0  mov     qword ptr [rcx+50h], 0
0x1400292b8  call    DestroyExclusiveUserCritDeferredUnlockList
0x1400292bd  mov     qword ptr [rdi+10h], 0
0x1400292c5  mov     rcx, [rbx]
0x1400292c8  test    rcx, rcx
0x1400292cb  jnz     short loc_140029311
0x1400292cd  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1400292d2  test    eax, eax
0x1400292d4  jnz     short loc_140029321
0x1400292d6  call    EtwTraceReleaseUserCrit
0x1400292db  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x1400292df  mov     eax, [rbx+18h]
0x1400292e2  test    al, 10h
0x1400292e4  jnz     short loc_140029344
0x1400292e6  mov     rcx, [rdi]
0x1400292e9  lea     rdx, [rbx+20h]
0x1400292ed  call    cs:__imp_ExReleaseFastResource
0x1400292f4  nop     dword ptr [rax+rax+00h]
0x1400292f9  call    cs:__imp_KeLeaveCriticalRegion
0x140029300  nop     dword ptr [rax+rax+00h]
0x140029305  mov     rbx, [rsp+38h+arg_0]
0x14002930a  add     rsp, 30h
0x14002930e  pop     rdi
0x14002930f  retn
0x140029311  mov     eax, [rbx+18h]
0x140029314  test    al, 2
0x140029316  jnz     short loc_1400292CD
0x140029318  mov     byte ptr [rcx+6ACh], 0
0x14002931f  jmp     short loc_1400292CD
0x140029321  mov     edx, eax; BugCheckParameter1
0x140029323  xor     r9d, r9d; BugCheckParameter3
0x140029326  xor     r8d, r8d; BugCheckParameter2
0x140029329  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140029332  mov     ecx, 160h; BugCheckCode
0x140029337  call    cs:__imp_KeBugCheckEx
0x140029344  mov     rcx, gs:188h
0x14002934d  mov     r8, rbx
0x140029350  xor     edx, edx
0x140029352  call    cs:__imp_PsSetThreadWin32Thread
0x140029359  nop     dword ptr [rax+rax+00h]
0x14002935e  jmp     short loc_1400292E6
```
