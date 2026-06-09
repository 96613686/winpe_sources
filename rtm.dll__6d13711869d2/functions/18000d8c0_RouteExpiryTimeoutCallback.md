# RouteExpiryTimeoutCallback

- ea: `0x18000d8c0`
- end: `0x18000d9bc`
- name: `RouteExpiryTimeoutCallback`
- size: `252`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a298`
- `0x18000c560`
- `0x18000d8c0`
- `0x180014d2c`
- `0x180015178`
- `0x180020010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000d97d`
- `KERNEL32!GetProcessHeap` at `0x18000d97d`
- `KERNEL32!HeapFree` at `0x18000d98b`
- `KERNEL32!HeapFree` at `0x18000d98b`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000d977`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000d977`

## pseudocode

```c
void __fastcall RouteExpiryTimeoutCallback(HANDLE *a1)
{
  unsigned __int64 v1; // rbx
  __int64 v3; // rdi
  unsigned __int64 v4; // rbp
  __int64 v5; // r15
  unsigned int (__fastcall *v6)(unsigned __int64, __int64, unsigned __int64, unsigned __int64); // rax
  HANDLE ProcessHeap; // rax
  DWORD ChangeFlags; // [rsp+60h] [rbp+8h] BYREF

  v1 = (unsigned __int64)a1[1];
  ChangeFlags = 0;
  v3 = (*(_QWORD *)(v1 + 48) ^ 0x7754DF32LL) + 32;
  AcquireWriteLock(v3);
  if ( *(HANDLE **)(v1 + 40) == a1 )
  {
    *(_QWORD *)(v1 + 40) = 0;
    ReleaseWriteLock(v3);
    v4 = *(_QWORD *)(v1 + 56);
    v5 = *(_QWORD *)((v4 ^ 0x7754DF32) + 0x10);
    _InterlockedIncrement((volatile signed __int32 *)v1);
    v6 = *(unsigned int (__fastcall **)(unsigned __int64, __int64, unsigned __int64, unsigned __int64))((v4 ^ 0x7754DF32) + 0x1C0);
    if ( !v6 || v6(v4, 2, v1 ^ 0x7754DF32, v1 + 48) == 50 )
      RtmDeleteRouteToDest((RTM_ENTITY_HANDLE)v4, (RTM_ROUTE_HANDLE)(v1 ^ 0x7754DF32), &ChangeFlags);
    DeleteTimerQueueTimer(*(HANDLE *)(v5 + 728), *a1, 0);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
      DestroyRoute((LPVOID)v1);
  }
  else
  {
    ReleaseWriteLock(v3);
  }
}

```

## disassembly

```asm
0x18000d8c0  mov     [rsp+arg_8], rbx
0x18000d8c5  mov     [rsp+arg_18], rbp
0x18000d8ca  push    rsi
0x18000d8cb  push    rdi
0x18000d8cc  push    r12
0x18000d8ce  push    r14
0x18000d8d0  push    r15
0x18000d8d2  sub     rsp, 30h
0x18000d8d6  mov     rbx, [rcx+8]
0x18000d8da  mov     rsi, rcx
0x18000d8dd  mov     [rsp+58h+ChangeFlags], 0
0x18000d8e5  mov     r12d, 7754DF32h
0x18000d8eb  mov     rdi, [rbx+30h]
0x18000d8ef  xor     rdi, r12
0x18000d8f2  add     rdi, 20h ; ' '
0x18000d8f6  mov     rcx, rdi
0x18000d8f9  call    AcquireWriteLock
0x18000d8fe  mov     rcx, rdi
0x18000d901  cmp     [rbx+28h], rsi
0x18000d905  jz      short loc_18000D911
0x18000d907  call    ReleaseWriteLock
0x18000d90c  jmp     loc_18000D9A5
0x18000d911  mov     qword ptr [rbx+28h], 0
0x18000d919  call    ReleaseWriteLock
0x18000d91e  mov     rbp, [rbx+38h]
0x18000d922  mov     rdi, rbx
0x18000d925  mov     rax, rbp
0x18000d928  xor     rax, r12
0x18000d92b  xor     rdi, r12
0x18000d92e  mov     r15, [rax+10h]
0x18000d932  lock inc dword ptr [rbx]
0x18000d935  mov     rax, [rax+1C0h]
0x18000d93c  test    rax, rax
0x18000d93f  jz      short loc_18000D95A
0x18000d941  lea     r9, [rbx+30h]
0x18000d945  mov     r8, rdi
0x18000d948  mov     edx, 2
0x18000d94d  mov     rcx, rbp
0x18000d950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d955  cmp     eax, 32h ; '2'
0x18000d958  jnz     short loc_18000D96A
0x18000d95a  lea     r8, [rsp+58h+ChangeFlags]; ChangeFlags
0x18000d95f  mov     rdx, rdi; RouteHandle
0x18000d962  mov     rcx, rbp; RtmRegHandle
0x18000d965  call    RtmDeleteRouteToDest
0x18000d96a  mov     rdx, [rsi]; Timer
0x18000d96d  xor     r8d, r8d; CompletionEvent
0x18000d970  mov     rcx, [r15+2D8h]; TimerQueue
0x18000d977  call    cs:__imp_DeleteTimerQueueTimer
0x18000d97d  call    cs:__imp_GetProcessHeap
0x18000d983  mov     r8, rsi; lpMem
0x18000d986  xor     edx, edx; dwFlags
0x18000d988  mov     rcx, rax; hHeap
0x18000d98b  call    cs:__imp_HeapFree
0x18000d991  or      eax, 0FFFFFFFFh
0x18000d994  lock xadd [rbx], eax
0x18000d998  cmp     eax, 1
0x18000d99b  jnz     short loc_18000D9A5
0x18000d99d  mov     rcx, rbx; lpMem
0x18000d9a0  call    DestroyRoute
0x18000d9a5  mov     rbx, [rsp+58h+arg_8]
0x18000d9aa  mov     rbp, [rsp+58h+arg_18]
0x18000d9af  add     rsp, 30h
0x18000d9b3  pop     r15
0x18000d9b5  pop     r14
0x18000d9b7  pop     r12
0x18000d9b9  pop     rdi
0x18000d9ba  pop     rsi
0x18000d9bb  retn
```
