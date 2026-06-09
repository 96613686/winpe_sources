# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180034fc8`
- end: `0x18003501b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011f9c`
- `0x18003550c`

## callees

- `0x180034fc8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035004`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035004`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034ff7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034ff7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034fe5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034fe5`

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
0x180034fc8  push    rbx
0x180034fca  sub     rsp, 20h
0x180034fce  mov     rbx, rcx
0x180034fd1  mov     rcx, [rcx+158h]; pti
0x180034fd8  test    rcx, rcx
0x180034fdb  jz      short loc_180035015
0x180034fdd  xor     r9d, r9d; msWindowLength
0x180034fe0  xor     r8d, r8d; msPeriod
0x180034fe3  xor     edx, edx; pftDueTime
0x180034fe5  call    cs:__imp_SetThreadpoolTimer
0x180034feb  mov     rcx, [rbx+158h]; pti
0x180034ff2  mov     edx, 1; fCancelPendingCallbacks
0x180034ff7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180034ffd  mov     rcx, [rbx+158h]; pti
0x180035004  call    cs:__imp_CloseThreadpoolTimer
0x18003500a  mov     qword ptr [rbx+158h], 0
0x180035015  add     rsp, 20h
0x180035019  pop     rbx
0x18003501a  retn
```
