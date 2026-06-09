# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180095270`
- end: `0x1800952c3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18009550c`
- `0x180096038`
- `0x180096160`

## callees

- `0x180095270`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009529f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009529f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800952ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800952ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009528d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009528d`

## pseudocode

```c
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
0x180095270  push    rbx
0x180095272  sub     rsp, 20h
0x180095276  mov     rbx, rcx
0x180095279  mov     rcx, [rcx+158h]; pti
0x180095280  test    rcx, rcx
0x180095283  jz      short loc_1800952BD
0x180095285  xor     r9d, r9d; msWindowLength
0x180095288  xor     r8d, r8d; msPeriod
0x18009528b  xor     edx, edx; pftDueTime
0x18009528d  call    cs:__imp_SetThreadpoolTimer
0x180095293  mov     rcx, [rbx+158h]; pti
0x18009529a  mov     edx, 1; fCancelPendingCallbacks
0x18009529f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800952a5  mov     rcx, [rbx+158h]; pti
0x1800952ac  call    cs:__imp_CloseThreadpoolTimer
0x1800952b2  mov     qword ptr [rbx+158h], 0
0x1800952bd  add     rsp, 20h
0x1800952c1  pop     rbx
0x1800952c2  retn
```
