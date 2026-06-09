# WJCloseThreadPoolTimer

- ea: `0x18002b444`
- end: `0x18002b47c`
- name: `WJCloseThreadPoolTimer`
- size: `56`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b344`
- `0x18002b39c`

## callees

- `0x18002b444`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002b467`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002b467`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002b470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002b470`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b459`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b459`

## pseudocode

```c
void __fastcall WJCloseThreadPoolTimer(PTP_TIMER pti)
{
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
  }
}

```

## disassembly

```asm
0x18002b444  test    rcx, rcx
0x18002b447  jz      short locret_18002B47B
0x18002b449  push    rbx
0x18002b44a  sub     rsp, 20h
0x18002b44e  xor     r9d, r9d; msWindowLength
0x18002b451  xor     r8d, r8d; msPeriod
0x18002b454  xor     edx, edx; pftDueTime
0x18002b456  mov     rbx, rcx
0x18002b459  call    cs:__imp_SetThreadpoolTimer
0x18002b45f  mov     edx, 1; fCancelPendingCallbacks
0x18002b464  mov     rcx, rbx; pti
0x18002b467  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002b46d  mov     rcx, rbx; pti
0x18002b470  call    cs:__imp_CloseThreadpoolTimer
0x18002b476  add     rsp, 20h
0x18002b47a  pop     rbx
0x18002b47b  retn
```
