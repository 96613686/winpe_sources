# WJCloseThreadPoolTimer

- ea: `0x18002da9c`
- end: `0x18002dae7`
- name: `WJCloseThreadPoolTimer`
- size: `75`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d974`
- `0x18002d9dc`

## callees

- `0x18002da9c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002dac5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002dac5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002dad4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002dad4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002dab1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002dab1`

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
0x18002da9c  test    rcx, rcx
0x18002da9f  jz      short locret_18002DAE5
0x18002daa1  push    rbx
0x18002daa2  sub     rsp, 20h
0x18002daa6  xor     r9d, r9d; msWindowLength
0x18002daa9  xor     r8d, r8d; msPeriod
0x18002daac  xor     edx, edx; pftDueTime
0x18002daae  mov     rbx, rcx
0x18002dab1  call    cs:__imp_SetThreadpoolTimer
0x18002dab8  nop     dword ptr [rax+rax+00h]
0x18002dabd  mov     edx, 1; fCancelPendingCallbacks
0x18002dac2  mov     rcx, rbx; pti
0x18002dac5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002dacc  nop     dword ptr [rax+rax+00h]
0x18002dad1  mov     rcx, rbx; pti
0x18002dad4  call    cs:__imp_CloseThreadpoolTimer
0x18002dadb  nop     dword ptr [rax+rax+00h]
0x18002dae0  add     rsp, 20h
0x18002dae4  pop     rbx
0x18002dae5  retn
```
