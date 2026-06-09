# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800a24e0`
- end: `0x1800a2514`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18008376c`
- `0x180083788`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a24f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a24f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a250d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a24ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a24ff`

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
0x1800a24e0  push    rbx
0x1800a24e2  sub     rsp, 20h
0x1800a24e6  xor     r9d, r9d; msWindowLength
0x1800a24e9  xor     r8d, r8d; msPeriod
0x1800a24ec  xor     edx, edx; pftDueTime
0x1800a24ee  mov     rbx, rcx
0x1800a24f1  call    cs:__imp_SetThreadpoolTimer
0x1800a24f7  mov     edx, 1; fCancelPendingCallbacks
0x1800a24fc  mov     rcx, rbx; pti
0x1800a24ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800a2505  mov     rcx, rbx
0x1800a2508  add     rsp, 20h
0x1800a250c  pop     rbx
0x1800a250d  jmp     cs:__imp_CloseThreadpoolTimer
```
