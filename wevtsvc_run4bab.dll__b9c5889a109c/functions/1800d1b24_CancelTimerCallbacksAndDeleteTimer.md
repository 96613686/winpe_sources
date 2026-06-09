# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800d1b24`
- end: `0x1800d1b77`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800d1e24`
- `0x1800d2530`

## callees

- `0x1800d1b24`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d1b41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d1b41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d1b60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d1b60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d1b53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d1b53`

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
0x1800d1b24  push    rbx
0x1800d1b26  sub     rsp, 20h
0x1800d1b2a  mov     rbx, rcx
0x1800d1b2d  mov     rcx, [rcx+158h]; pti
0x1800d1b34  test    rcx, rcx
0x1800d1b37  jz      short loc_1800D1B71
0x1800d1b39  xor     r9d, r9d; msWindowLength
0x1800d1b3c  xor     r8d, r8d; msPeriod
0x1800d1b3f  xor     edx, edx; pftDueTime
0x1800d1b41  call    cs:__imp_SetThreadpoolTimer
0x1800d1b47  mov     rcx, [rbx+158h]; pti
0x1800d1b4e  mov     edx, 1; fCancelPendingCallbacks
0x1800d1b53  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800d1b59  mov     rcx, [rbx+158h]; pti
0x1800d1b60  call    cs:__imp_CloseThreadpoolTimer
0x1800d1b66  mov     qword ptr [rbx+158h], 0
0x1800d1b71  add     rsp, 20h
0x1800d1b75  pop     rbx
0x1800d1b76  retn
```
