# CQuietHoursManager::_CancelTimers(void)

- ea: `0x180070f8c`
- end: `0x180071037`
- name: `?_CancelTimers@CQuietHoursManager@@AEAAXXZ`
- size: `171`
- prototype: `void __fastcall(CQuietHoursManager *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180070704`
- `0x1802c46b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070fa4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070fcb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070ff2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180071019`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070fa4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070fcb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070ff2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180071019`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070fb6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070fdd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180071004`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070fb6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070fdd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180071004`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180071030`

## pseudocode

```c
void __fastcall CQuietHoursManager::_CancelTimers(PTP_TIMER *this)
{
  SetThreadpoolTimer(this[25], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[25], 1);
  SetThreadpoolTimer(this[26], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[26], 1);
  SetThreadpoolTimer(this[27], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[27], 1);
  SetThreadpoolTimer(this[28], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[28], 1);
}

```

## disassembly

```asm
0x180070f8c  push    rbx
0x180070f8e  sub     rsp, 20h
0x180070f92  mov     rbx, rcx
0x180070f95  xor     r9d, r9d; msWindowLength
0x180070f98  mov     rcx, [rcx+0C8h]; pti
0x180070f9f  xor     r8d, r8d; msPeriod
0x180070fa2  xor     edx, edx; pftDueTime
0x180070fa4  call    cs:__imp_SetThreadpoolTimer
0x180070faa  mov     rcx, [rbx+0C8h]; pti
0x180070fb1  mov     edx, 1; fCancelPendingCallbacks
0x180070fb6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180070fbc  mov     rcx, [rbx+0D0h]; pti
0x180070fc3  xor     r9d, r9d; msWindowLength
0x180070fc6  xor     r8d, r8d; msPeriod
0x180070fc9  xor     edx, edx; pftDueTime
0x180070fcb  call    cs:__imp_SetThreadpoolTimer
0x180070fd1  mov     rcx, [rbx+0D0h]; pti
0x180070fd8  mov     edx, 1; fCancelPendingCallbacks
0x180070fdd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180070fe3  mov     rcx, [rbx+0D8h]; pti
0x180070fea  xor     r9d, r9d; msWindowLength
0x180070fed  xor     r8d, r8d; msPeriod
0x180070ff0  xor     edx, edx; pftDueTime
0x180070ff2  call    cs:__imp_SetThreadpoolTimer
0x180070ff8  mov     rcx, [rbx+0D8h]; pti
0x180070fff  mov     edx, 1; fCancelPendingCallbacks
0x180071004  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007100a  mov     rcx, [rbx+0E0h]; pti
0x180071011  xor     r9d, r9d; msWindowLength
0x180071014  xor     r8d, r8d; msPeriod
0x180071017  xor     edx, edx; pftDueTime
0x180071019  call    cs:__imp_SetThreadpoolTimer
0x18007101f  mov     rcx, [rbx+0E0h]
0x180071026  mov     edx, 1
0x18007102b  add     rsp, 20h
0x18007102f  pop     rbx
0x180071030  jmp     cs:__imp_WaitForThreadpoolTimerCallbacks
```
