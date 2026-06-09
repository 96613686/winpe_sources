# WaDeleteTimer

- ea: `0x1800201dc`
- end: `0x18002022f`
- name: `WaDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ff40`
- `0x180022064`
- `0x180070134`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800201f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800201f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020216`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020216`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020206`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020206`

## pseudocode

```c
void __fastcall WaDeleteTimer(__int64 a1)
{
  SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 8), 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 8), 1);
  CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 8));
  *(_DWORD *)a1 = 1919773044;
}

```

## disassembly

```asm
0x1800201dc  push    rbx
0x1800201de  sub     rsp, 20h
0x1800201e2  mov     rbx, rcx
0x1800201e5  xor     r9d, r9d; msWindowLength
0x1800201e8  mov     rcx, [rcx+8]; pti
0x1800201ec  xor     r8d, r8d; msPeriod
0x1800201ef  xor     edx, edx; pftDueTime
0x1800201f1  call    cs:__imp_SetThreadpoolTimer
0x1800201f8  nop     dword ptr [rax+rax+00h]
0x1800201fd  mov     rcx, [rbx+8]; pti
0x180020201  mov     edx, 1; fCancelPendingCallbacks
0x180020206  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002020d  nop     dword ptr [rax+rax+00h]
0x180020212  mov     rcx, [rbx+8]; pti
0x180020216  call    cs:__imp_CloseThreadpoolTimer
0x18002021d  nop     dword ptr [rax+rax+00h]
0x180020222  mov     dword ptr [rbx], 726D6974h
0x180020228  add     rsp, 20h
0x18002022c  pop     rbx
0x18002022d  retn
```
