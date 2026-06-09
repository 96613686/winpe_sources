# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800cdc64`
- end: `0x1800cdcca`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a5534`
- `0x1800a5a04`

## callees

- `0x1800cdc64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800cdcac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800cdcac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cdc99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cdc99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cdc81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cdc81`

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
0x1800cdc64  push    rbx
0x1800cdc66  sub     rsp, 20h
0x1800cdc6a  mov     rbx, rcx
0x1800cdc6d  mov     rcx, [rcx+158h]; pti
0x1800cdc74  test    rcx, rcx
0x1800cdc77  jz      short loc_1800CDCC3
0x1800cdc79  xor     r9d, r9d; msWindowLength
0x1800cdc7c  xor     r8d, r8d; msPeriod
0x1800cdc7f  xor     edx, edx; pftDueTime
0x1800cdc81  call    cs:__imp_SetThreadpoolTimer
0x1800cdc88  nop     dword ptr [rax+rax+00h]
0x1800cdc8d  mov     rcx, [rbx+158h]; pti
0x1800cdc94  mov     edx, 1; fCancelPendingCallbacks
0x1800cdc99  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800cdca0  nop     dword ptr [rax+rax+00h]
0x1800cdca5  mov     rcx, [rbx+158h]; pti
0x1800cdcac  call    cs:__imp_CloseThreadpoolTimer
0x1800cdcb3  nop     dword ptr [rax+rax+00h]
0x1800cdcb8  mov     qword ptr [rbx+158h], 0
0x1800cdcc3  add     rsp, 20h
0x1800cdcc7  pop     rbx
0x1800cdcc8  retn
```
