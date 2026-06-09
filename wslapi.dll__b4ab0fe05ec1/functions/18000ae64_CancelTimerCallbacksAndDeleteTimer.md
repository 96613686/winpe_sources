# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18000ae64`
- end: `0x18000aeb7`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b018`
- `0x18000b8dc`

## callees

- `0x18000ae64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aea0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aea0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae81`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ae93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ae93`

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
0x18000ae64  push    rbx
0x18000ae66  sub     rsp, 20h
0x18000ae6a  mov     rbx, rcx
0x18000ae6d  mov     rcx, [rcx+158h]; pti
0x18000ae74  test    rcx, rcx
0x18000ae77  jz      short loc_18000AEB1
0x18000ae79  xor     r9d, r9d; msWindowLength
0x18000ae7c  xor     r8d, r8d; msPeriod
0x18000ae7f  xor     edx, edx; pftDueTime
0x18000ae81  call    cs:__imp_SetThreadpoolTimer
0x18000ae87  mov     rcx, [rbx+158h]; pti
0x18000ae8e  mov     edx, 1; fCancelPendingCallbacks
0x18000ae93  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ae99  mov     rcx, [rbx+158h]; pti
0x18000aea0  call    cs:__imp_CloseThreadpoolTimer
0x18000aea6  mov     qword ptr [rbx+158h], 0
0x18000aeb1  add     rsp, 20h
0x18000aeb5  pop     rbx
0x18000aeb6  retn
```
