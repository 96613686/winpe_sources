# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180017730`
- end: `0x180017764`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016220`
- `0x180020608`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017741`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017741`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001775d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001774f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001774f`

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
0x180017730  push    rbx
0x180017732  sub     rsp, 20h
0x180017736  xor     r9d, r9d; msWindowLength
0x180017739  xor     r8d, r8d; msPeriod
0x18001773c  xor     edx, edx; pftDueTime
0x18001773e  mov     rbx, rcx
0x180017741  call    cs:__imp_SetThreadpoolTimer
0x180017747  mov     edx, 1; fCancelPendingCallbacks
0x18001774c  mov     rcx, rbx; pti
0x18001774f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017755  mov     rcx, rbx
0x180017758  add     rsp, 20h
0x18001775c  pop     rbx
0x18001775d  jmp     cs:__imp_CloseThreadpoolTimer
```
