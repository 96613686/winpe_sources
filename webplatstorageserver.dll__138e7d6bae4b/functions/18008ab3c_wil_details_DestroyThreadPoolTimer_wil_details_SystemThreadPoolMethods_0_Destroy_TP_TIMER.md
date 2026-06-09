# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18008ab3c`
- end: `0x18008ab70`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18006a7cc`
- `0x18006a8fc`
- `0x18006a94c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008ab4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008ab4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008ab69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008ab5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008ab5b`

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
0x18008ab3c  push    rbx
0x18008ab3e  sub     rsp, 20h
0x18008ab42  xor     r9d, r9d; msWindowLength
0x18008ab45  xor     r8d, r8d; msPeriod
0x18008ab48  xor     edx, edx; pftDueTime
0x18008ab4a  mov     rbx, rcx
0x18008ab4d  call    cs:__imp_SetThreadpoolTimer
0x18008ab53  mov     edx, 1; fCancelPendingCallbacks
0x18008ab58  mov     rcx, rbx; pti
0x18008ab5b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18008ab61  mov     rcx, rbx
0x18008ab64  add     rsp, 20h
0x18008ab68  pop     rbx
0x18008ab69  jmp     cs:__imp_CloseThreadpoolTimer
```
