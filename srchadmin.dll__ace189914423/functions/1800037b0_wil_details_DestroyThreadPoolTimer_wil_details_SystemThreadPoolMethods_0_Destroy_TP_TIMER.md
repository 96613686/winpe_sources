# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800037b0`
- end: `0x1800037e4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800031c0`
- `0x180031360`
- `0x1800315a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037c1`

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
0x1800037b0  push    rbx
0x1800037b2  sub     rsp, 20h
0x1800037b6  xor     r9d, r9d; msWindowLength
0x1800037b9  xor     r8d, r8d; msPeriod
0x1800037bc  xor     edx, edx; pftDueTime
0x1800037be  mov     rbx, rcx
0x1800037c1  call    cs:__imp_SetThreadpoolTimer
0x1800037c7  mov     edx, 1; fCancelPendingCallbacks
0x1800037cc  mov     rcx, rbx; pti
0x1800037cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800037d5  mov     rcx, rbx
0x1800037d8  add     rsp, 20h
0x1800037dc  pop     rbx
0x1800037dd  jmp     cs:__imp_CloseThreadpoolTimer
```
