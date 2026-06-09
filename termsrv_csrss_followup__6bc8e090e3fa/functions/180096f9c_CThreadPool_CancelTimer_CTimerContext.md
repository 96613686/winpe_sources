# CThreadPool::CancelTimer(CTimerContext *)

- ea: `0x180096f9c`
- end: `0x180097024`
- name: `?CancelTimer@CThreadPool@@QEAAJPEAVCTimerContext@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(CThreadPool *__hidden this, struct CTimerContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800424d0`

## callees

- `0x180096f9c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180096fe5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180096fe5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180096fc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180096fc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180096fd5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180096fd5`

## pseudocode

```c
__int64 __fastcall CThreadPool::CancelTimer(CThreadPool *this, struct CTimerContext *a2)
{
  unsigned int v3; // edi
  PTP_TIMER v4; // rax

  v3 = 1;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 12, 1, 0) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)a2 + 5), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)a2 + 5), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)a2 + 5));
    v4 = *(PTP_TIMER *)a2;
    v3 = 0;
    *((_QWORD *)a2 + 5) = 0;
    (*((void (__fastcall **)(struct CTimerContext *))v4 + 4))(a2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 1) + 8LL))(*((_QWORD *)a2 + 1));
  }
  return v3;
}

```

## disassembly

```asm
0x180096f9c  mov     [rsp+arg_8], rbx
0x180096fa1  push    rdi
0x180096fa2  sub     rsp, 20h
0x180096fa6  mov     rbx, rdx
0x180096fa9  mov     edi, 1
0x180096fae  xor     eax, eax
0x180096fb0  lock cmpxchg [rdx+30h], edi
0x180096fb5  jnz     short loc_180097016
0x180096fb7  mov     rcx, [rbx+28h]; pti
0x180096fbb  xor     r9d, r9d; msWindowLength
0x180096fbe  xor     r8d, r8d; msPeriod
0x180096fc1  xor     edx, edx; pftDueTime
0x180096fc3  call    cs:__imp_SetThreadpoolTimer
0x180096fca  nop     dword ptr [rax+rax+00h]
0x180096fcf  mov     rcx, [rbx+28h]; pti
0x180096fd3  mov     edx, edi; fCancelPendingCallbacks
0x180096fd5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180096fdc  nop     dword ptr [rax+rax+00h]
0x180096fe1  mov     rcx, [rbx+28h]; pti
0x180096fe5  call    cs:__imp_CloseThreadpoolTimer
0x180096fec  nop     dword ptr [rax+rax+00h]
0x180096ff1  mov     rax, [rbx]
0x180096ff4  xor     edi, edi
0x180096ff6  mov     rcx, rbx
0x180096ff9  mov     [rbx+28h], rdi
0x180096ffd  mov     rax, [rax+20h]
0x180097001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097006  mov     rcx, [rbx+8]
0x18009700a  mov     rax, [rcx]
0x18009700d  mov     rax, [rax+8]
0x180097011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097016  mov     rbx, [rsp+28h+arg_8]
0x18009701b  mov     eax, edi
0x18009701d  add     rsp, 20h
0x180097021  pop     rdi
0x180097022  retn
```
