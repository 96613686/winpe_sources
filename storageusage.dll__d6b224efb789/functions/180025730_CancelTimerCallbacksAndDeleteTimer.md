# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180025730`
- end: `0x180025783`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180025af4`
- `0x180026720`

## callees

- `0x180025730`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002576c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002576c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002575f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002575f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002574d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002574d`

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
0x180025730  push    rbx
0x180025732  sub     rsp, 20h
0x180025736  mov     rbx, rcx
0x180025739  mov     rcx, [rcx+158h]; pti
0x180025740  test    rcx, rcx
0x180025743  jz      short loc_18002577D
0x180025745  xor     r9d, r9d; msWindowLength
0x180025748  xor     r8d, r8d; msPeriod
0x18002574b  xor     edx, edx; pftDueTime
0x18002574d  call    cs:__imp_SetThreadpoolTimer
0x180025753  mov     rcx, [rbx+158h]; pti
0x18002575a  mov     edx, 1; fCancelPendingCallbacks
0x18002575f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025765  mov     rcx, [rbx+158h]; pti
0x18002576c  call    cs:__imp_CloseThreadpoolTimer
0x180025772  mov     qword ptr [rbx+158h], 0
0x18002577d  add     rsp, 20h
0x180025781  pop     rbx
0x180025782  retn
```
