# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003d300`
- end: `0x18003d334`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003cb60`
- `0x180040c94`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d31f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d31f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003d32d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d311`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d311`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18003d300  push    rbx
0x18003d302  sub     rsp, 20h
0x18003d306  xor     r9d, r9d; msWindowLength
0x18003d309  xor     r8d, r8d; msPeriod
0x18003d30c  xor     edx, edx; pftDueTime
0x18003d30e  mov     rbx, rcx
0x18003d311  call    cs:__imp_SetThreadpoolTimer
0x18003d317  mov     edx, 1; fCancelPendingCallbacks
0x18003d31c  mov     rcx, rbx; pti
0x18003d31f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003d325  mov     rcx, rbx
0x18003d328  add     rsp, 20h
0x18003d32c  pop     rbx
0x18003d32d  jmp     cs:__imp_CloseThreadpoolTimer
```
