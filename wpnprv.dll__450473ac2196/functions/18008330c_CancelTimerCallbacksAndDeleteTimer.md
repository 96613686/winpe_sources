# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18008330c`
- end: `0x18008335f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18008363c`
- `0x180084260`

## callees

- `0x18008330c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180083348`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180083348`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008333b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008333b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180083329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180083329`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
void __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *(struct _TP_TIMER **)(a1 + 344);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 344), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 344));
    *(_QWORD *)(a1 + 344) = 0;
  }
}

```

## disassembly

```asm
0x18008330c  push    rbx
0x18008330e  sub     rsp, 20h
0x180083312  mov     rbx, rcx
0x180083315  mov     rcx, [rcx+158h]; pti
0x18008331c  test    rcx, rcx
0x18008331f  jz      short loc_180083359
0x180083321  xor     r9d, r9d; msWindowLength
0x180083324  xor     r8d, r8d; msPeriod
0x180083327  xor     edx, edx; pftDueTime
0x180083329  call    cs:__imp_SetThreadpoolTimer
0x18008332f  mov     rcx, [rbx+158h]; pti
0x180083336  mov     edx, 1; fCancelPendingCallbacks
0x18008333b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180083341  mov     rcx, [rbx+158h]; pti
0x180083348  call    cs:__imp_CloseThreadpoolTimer
0x18008334e  mov     qword ptr [rbx+158h], 0
0x180083359  add     rsp, 20h
0x18008335d  pop     rbx
0x18008335e  retn
```
