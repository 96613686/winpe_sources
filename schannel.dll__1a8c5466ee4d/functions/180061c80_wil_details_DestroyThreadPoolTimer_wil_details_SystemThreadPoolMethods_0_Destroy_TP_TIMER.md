# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180061c80`
- end: `0x180061cb4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800463bc`
- `0x1800463d8`
- `0x1800542e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180061c91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180061c91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180061c9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180061c9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180061cad`

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
0x180061c80  push    rbx
0x180061c82  sub     rsp, 20h
0x180061c86  xor     r9d, r9d; msWindowLength
0x180061c89  xor     r8d, r8d; msPeriod
0x180061c8c  xor     edx, edx; pftDueTime
0x180061c8e  mov     rbx, rcx
0x180061c91  call    cs:__imp_SetThreadpoolTimer
0x180061c97  mov     edx, 1; fCancelPendingCallbacks
0x180061c9c  mov     rcx, rbx; pti
0x180061c9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180061ca5  mov     rcx, rbx
0x180061ca8  add     rsp, 20h
0x180061cac  pop     rbx
0x180061cad  jmp     cs:__imp_CloseThreadpoolTimer
```
