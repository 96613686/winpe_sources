# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003b51c`
- end: `0x18003b550`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180025790`
- `0x180034f8c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003b549`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b53b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b53b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b52d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b52d`

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
0x18003b51c  push    rbx
0x18003b51e  sub     rsp, 20h
0x18003b522  xor     r9d, r9d; msWindowLength
0x18003b525  xor     r8d, r8d; msPeriod
0x18003b528  xor     edx, edx; pftDueTime
0x18003b52a  mov     rbx, rcx
0x18003b52d  call    cs:__imp_SetThreadpoolTimer
0x18003b533  mov     edx, 1; fCancelPendingCallbacks
0x18003b538  mov     rcx, rbx; pti
0x18003b53b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003b541  mov     rcx, rbx
0x18003b544  add     rsp, 20h
0x18003b548  pop     rbx
0x18003b549  jmp     cs:__imp_CloseThreadpoolTimer
```
