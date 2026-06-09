# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180017c70`
- end: `0x180017ca4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800174e8`
- `0x18001b4f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017c8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017c8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017c9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017c81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017c81`

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
0x180017c70  push    rbx
0x180017c72  sub     rsp, 20h
0x180017c76  xor     r9d, r9d; msWindowLength
0x180017c79  xor     r8d, r8d; msPeriod
0x180017c7c  xor     edx, edx; pftDueTime
0x180017c7e  mov     rbx, rcx
0x180017c81  call    cs:__imp_SetThreadpoolTimer
0x180017c87  mov     edx, 1; fCancelPendingCallbacks
0x180017c8c  mov     rcx, rbx; pti
0x180017c8f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017c95  mov     rcx, rbx
0x180017c98  add     rsp, 20h
0x180017c9c  pop     rbx
0x180017c9d  jmp     cs:__imp_CloseThreadpoolTimer
```
