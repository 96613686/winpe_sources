# PAL_System_WinCommon_StopThreadpoolTimer

- ea: `0x18001b5ac`
- end: `0x18001b5d7`
- name: `PAL_System_WinCommon_StopThreadpoolTimer`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003ea60`
- `0x18003eab0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b5d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b5bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b5bd`

## pseudocode

```c
void __fastcall PAL_System_WinCommon_StopThreadpoolTimer(struct _TP_TIMER *a1)
{
  SetThreadpoolTimer(a1, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(a1, 1);
}

```

## disassembly

```asm
0x18001b5ac  push    rbx
0x18001b5ae  sub     rsp, 20h
0x18001b5b2  xor     r9d, r9d; msWindowLength
0x18001b5b5  xor     r8d, r8d; msPeriod
0x18001b5b8  xor     edx, edx; pftDueTime
0x18001b5ba  mov     rbx, rcx
0x18001b5bd  call    cs:__imp_SetThreadpoolTimer
0x18001b5c3  mov     edx, 1
0x18001b5c8  mov     rcx, rbx
0x18001b5cb  add     rsp, 20h
0x18001b5cf  pop     rbx
0x18001b5d0  jmp     cs:__imp_WaitForThreadpoolTimerCallbacks
```
