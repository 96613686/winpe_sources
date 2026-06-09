# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180088798`
- end: `0x1800887eb`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800559a4`
- `0x1800887f4`

## callees

- `0x180088798`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800887b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800887b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800887c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800887c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800887d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800887d4`

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
0x180088798  push    rbx
0x18008879a  sub     rsp, 20h
0x18008879e  mov     rbx, rcx
0x1800887a1  mov     rcx, [rcx+158h]; pti
0x1800887a8  test    rcx, rcx
0x1800887ab  jz      short loc_1800887E5
0x1800887ad  xor     r9d, r9d; msWindowLength
0x1800887b0  xor     r8d, r8d; msPeriod
0x1800887b3  xor     edx, edx; pftDueTime
0x1800887b5  call    cs:__imp_SetThreadpoolTimer
0x1800887bb  mov     rcx, [rbx+158h]; pti
0x1800887c2  mov     edx, 1; fCancelPendingCallbacks
0x1800887c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800887cd  mov     rcx, [rbx+158h]; pti
0x1800887d4  call    cs:__imp_CloseThreadpoolTimer
0x1800887da  mov     qword ptr [rbx+158h], 0
0x1800887e5  add     rsp, 20h
0x1800887e9  pop     rbx
0x1800887ea  retn
```
