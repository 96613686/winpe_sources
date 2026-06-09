# CRemoteConnectionManager::CancelRemoteDisplayAdapterTimer(CTimerContext *)

- ea: `0x1800402f0`
- end: `0x180040365`
- name: `?CancelRemoteDisplayAdapterTimer@CRemoteConnectionManager@@UEAAXPEAVCTimerContext@@@Z`
- size: `117`
- prototype: `void __fastcall(CRemoteConnectionManager *__hidden this, struct CTimerContext *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800402f0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004032d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004032d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040317`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040317`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180040323`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180040323`

## pseudocode

```c
void __fastcall CRemoteConnectionManager::CancelRemoteDisplayAdapterTimer(
        CRemoteConnectionManager *this,
        struct CTimerContext *a2)
{
  PTP_TIMER v3; // rax

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 12, 1, 0) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)a2 + 5), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)a2 + 5), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)a2 + 5));
    v3 = *(PTP_TIMER *)a2;
    *((_QWORD *)a2 + 5) = 0;
    (*((void (__fastcall **)(struct CTimerContext *))v3 + 4))(a2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 1) + 8LL))(*((_QWORD *)a2 + 1));
  }
}

```

## disassembly

```asm
0x1800402f0  mov     [rsp+arg_8], rbx
0x1800402f5  push    rdi
0x1800402f6  sub     rsp, 20h
0x1800402fa  mov     rbx, rdx
0x1800402fd  mov     edi, 1
0x180040302  xor     eax, eax
0x180040304  lock cmpxchg [rdx+30h], edi
0x180040309  jnz     short loc_18004035A
0x18004030b  mov     rcx, [rbx+28h]; pti
0x18004030f  xor     r9d, r9d; msWindowLength
0x180040312  xor     r8d, r8d; msPeriod
0x180040315  xor     edx, edx; pftDueTime
0x180040317  call    cs:__imp_SetThreadpoolTimer
0x18004031d  mov     rcx, [rbx+28h]; pti
0x180040321  mov     edx, edi; fCancelPendingCallbacks
0x180040323  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180040329  mov     rcx, [rbx+28h]; pti
0x18004032d  call    cs:__imp_CloseThreadpoolTimer
0x180040333  mov     rax, [rbx]
0x180040336  mov     rcx, rbx
0x180040339  mov     qword ptr [rbx+28h], 0
0x180040341  mov     rax, [rax+20h]
0x180040345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004034a  mov     rcx, [rbx+8]
0x18004034e  mov     rax, [rcx]
0x180040351  mov     rax, [rax+8]
0x180040355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004035a  mov     rbx, [rsp+28h+arg_8]
0x18004035f  add     rsp, 20h
0x180040363  pop     rdi
0x180040364  retn
```
