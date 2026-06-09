# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18000a00c`
- end: `0x18000a05f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009ec0`
- `0x180009ef4`

## callees

- `0x18000a00c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a048`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a048`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a03b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a03b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a029`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a029`

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
0x18000a00c  push    rbx
0x18000a00e  sub     rsp, 20h
0x18000a012  mov     rbx, rcx
0x18000a015  mov     rcx, [rcx+158h]; pti
0x18000a01c  test    rcx, rcx
0x18000a01f  jz      short loc_18000A059
0x18000a021  xor     r9d, r9d; msWindowLength
0x18000a024  xor     r8d, r8d; msPeriod
0x18000a027  xor     edx, edx; pftDueTime
0x18000a029  call    cs:__imp_SetThreadpoolTimer
0x18000a02f  mov     rcx, [rbx+158h]; pti
0x18000a036  mov     edx, 1; fCancelPendingCallbacks
0x18000a03b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a041  mov     rcx, [rbx+158h]; pti
0x18000a048  call    cs:__imp_CloseThreadpoolTimer
0x18000a04e  mov     qword ptr [rbx+158h], 0
0x18000a059  add     rsp, 20h
0x18000a05d  pop     rbx
0x18000a05e  retn
```
