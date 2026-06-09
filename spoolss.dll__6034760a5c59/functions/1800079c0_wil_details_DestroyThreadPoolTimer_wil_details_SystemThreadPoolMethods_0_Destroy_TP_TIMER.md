# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800079c0`
- end: `0x1800079f4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004658`
- `0x180004840`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079ed`

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
0x1800079c0  push    rbx
0x1800079c2  sub     rsp, 20h
0x1800079c6  xor     r9d, r9d; msWindowLength
0x1800079c9  xor     r8d, r8d; msPeriod
0x1800079cc  xor     edx, edx; pftDueTime
0x1800079ce  mov     rbx, rcx
0x1800079d1  call    cs:__imp_SetThreadpoolTimer
0x1800079d7  mov     edx, 1; fCancelPendingCallbacks
0x1800079dc  mov     rcx, rbx; pti
0x1800079df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800079e5  mov     rcx, rbx
0x1800079e8  add     rsp, 20h
0x1800079ec  pop     rbx
0x1800079ed  jmp     cs:__imp_CloseThreadpoolTimer
```
