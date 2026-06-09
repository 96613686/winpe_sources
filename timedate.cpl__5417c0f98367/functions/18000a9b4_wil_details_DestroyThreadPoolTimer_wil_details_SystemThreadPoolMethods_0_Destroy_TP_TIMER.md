# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000a9b4`
- end: `0x18000a9e8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a088`
- `0x18000d6ac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a9d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a9d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9e1`

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
0x18000a9b4  push    rbx
0x18000a9b6  sub     rsp, 20h
0x18000a9ba  xor     r9d, r9d; msWindowLength
0x18000a9bd  xor     r8d, r8d; msPeriod
0x18000a9c0  xor     edx, edx; pftDueTime
0x18000a9c2  mov     rbx, rcx
0x18000a9c5  call    cs:__imp_SetThreadpoolTimer
0x18000a9cb  mov     edx, 1; fCancelPendingCallbacks
0x18000a9d0  mov     rcx, rbx; pti
0x18000a9d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a9d9  mov     rcx, rbx
0x18000a9dc  add     rsp, 20h
0x18000a9e0  pop     rbx
0x18000a9e1  jmp     cs:__imp_CloseThreadpoolTimer
```
