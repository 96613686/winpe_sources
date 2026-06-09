# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800428b4`
- end: `0x180042907`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180042a68`
- `0x18004334c`

## callees

- `0x1800428b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800428e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800428e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800428f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800428f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800428d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800428d1`

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
0x1800428b4  push    rbx
0x1800428b6  sub     rsp, 20h
0x1800428ba  mov     rbx, rcx
0x1800428bd  mov     rcx, [rcx+158h]; pti
0x1800428c4  test    rcx, rcx
0x1800428c7  jz      short loc_180042901
0x1800428c9  xor     r9d, r9d; msWindowLength
0x1800428cc  xor     r8d, r8d; msPeriod
0x1800428cf  xor     edx, edx; pftDueTime
0x1800428d1  call    cs:__imp_SetThreadpoolTimer
0x1800428d7  mov     rcx, [rbx+158h]; pti
0x1800428de  mov     edx, 1; fCancelPendingCallbacks
0x1800428e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800428e9  mov     rcx, [rbx+158h]; pti
0x1800428f0  call    cs:__imp_CloseThreadpoolTimer
0x1800428f6  mov     qword ptr [rbx+158h], 0
0x180042901  add     rsp, 20h
0x180042905  pop     rbx
0x180042906  retn
```
